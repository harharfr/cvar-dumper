## 🔍 CVar Extractor from Unreal Engine Log

This Node.js script parses an `input.log` file to extract CVars set via `LogConfig: Set CVar` lines and writes them to `output.txt`.

### 📄 Input Format

Your `input.log` should contain lines like:
LogConfig: Set CVar [[r.ViewDistanceScale=4]] LogConfig: Set CVar [[sg.ShadowQuality=2]]

