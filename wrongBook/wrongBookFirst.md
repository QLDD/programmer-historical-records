##### 1、Illegal invocation：非法援引

``` js
//-- Vue --

import MD5Methods from '../../../utils/MD5Methods';
//获取文件的MD5值
getMD5OfFile (e) {                        
    let file = e.target.files[0];            
    MD5Methods.md5File(file).then(e => {
        this.addInfo.hash = e;
    });                                             
},

//-- js --
const SparkMD5 = require('spark-md5');
const blobSlice = File.prototype.slice || File.prototype.mozSlice || File.prototype.webkitSlice;
class MD5Methods {        
    static async md5File (file) {
        return new Promise((resolve, reject) => {            
            let chunkSize = 2097152;
            let chunks = Math.ceil(file.size / chunkSize);
            let currentChunk = 0;
            let spark = new SparkMD5.ArrayBuffer();            
            let fileReader = new FileReader(); 
            fileReader.onload = (e) => {                
                spark.append(e.target.result);
                currentChunk++;
                if (currentChunk < chunks) {
                    this.loadNext(currentChunk, chunkSize, file, fileReader);
                } else {
                    let result = spark.end();                                        
                    resolve(result);
                }
            };
            fileReader.onerror = () => {
                reject('fileReader异常');                
            };
            this.loadNext(currentChunk, chunkSize, file, fileReader);
        })
    }
    static loadNext (currentChunk, chunkSize, file, fileReader) {
        let start = currentChunk * chunkSize;
        let end = ((start + chunkSize) >= file.size) ? file.size : start + chunkSize;        	//blobSlice.call(file, start, end)为报错方法
        fileReader.readAsArrayBuffer(blobSlice.call(file, start, end));                
    }
}
module.exports = MD5Methods;        
```

- 我的一个 Vue 前端项目，准备在不涉及后端服务的情况下，对安装包文件进行MD5(信息摘要算法)。代码在执行到 blobSlice.call(file, start, end) 的时候，报错 Illegal invocation 。
- 多次排查代码，无果。然后，排查参数。
- 原来参数是 let file = e.target.files; 后来查资料改为 let file = e.target.files[0]; 代码不报错。
- 确定为 参数 问题。



