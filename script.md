### 💻 Code

```js
const fs = require('fs');
const path = require('path');

const inputFile = path.resolve(__dirname, 'input.log');
const outputFile = path.resolve(__dirname, 'output.txt');

const logData = fs.readFileSync(inputFile, 'utf-8');

const lines = logData.split('\n');
const extractedCVars = [];

for (const line of lines) {
    if (line.includes('LogConfig: Set CVar')) {
        const match = line.match(/\[\[(.*?)\]\]/);
        if (match && match[1]) {
            extractedCVars.push(match[1]);
        }
    }
}

fs.writeFileSync(outputFile, extractedCVars.join('\n'), 'utf-8');

console.log(`✅ Extracted ${extractedCVars.length} CVar(s) to ${outputFile}`);
```
