## 实现
由于ES6转ES5中需要用到babel，所以要用到一下插件

`npm install @babel/core @babel/parser @babel/traverse @babel/preset-env --save-dev`

```
// entry.js

import message from './message.js';
console.log(message);
```
```
// message.js

import {name} from './name.js';
export default `hello ${name}!`;
```
```
// name.js

export const name = 'world';
```
``` 
//bundler.js 
// 读取文件信息，并获得当前js文件的依赖关系
function createAsset(filename) {//代码略}
// 从入口开始分析所有依赖项，形成依赖图，采用广度遍历
function createGraph(entry) {//代码略}
// 根据生成的依赖关系图，生成浏览器可执行文件
function bundle(graph) {//代码略}
```


目录结构
```
- example
    - entry.js
    - message.js
    - name.js
    - childFold
      - name2.js
      - name3.js
      - name4.js
- bundler.js
```
