# Analyzing CSV files

- Read a csv file, parse the data, do some analysis and then return a report.

### first Attempt

- Goal is to refactor the code below to a reusable or a good code for other engineers to understand.

```js
import fs from "fs";

// This is a BAD CODE!
/*
  TODO: Make this file to accept any csv file with any type of data.
*/
const matches = fs
  .readFileSync("football.csv", {
    encoding: "utf-8",
  })
  .split("\n")
  .map((row: string): string => {
    return row.split(",");
  });

let manUnitedWon = 0;
for (let match of matches) {
  if (match[1] === "Man United" && match[5] === "H") {
    manUnitedWon++;
  } else if (match[2] === "Man United" && match[5] === "A") {
    manUnitedWon++;
  }
}

console.log(`Man United won ${manUnitedWon} games`);

>>> `Man United won 18 games`
```
