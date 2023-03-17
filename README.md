# ![Version](https://img.shields.io/badge/version-1.1.0-green.svg)

## 安装

```
npm install lite-ts-qiniu
```

## 使用

```typescript
import { QiniuFileFactory } from 'lite-ts-qiniu';
//七牛云配置
const cfg = {
    bucket:xxx
    ...
}

const factory = new QiniuFileFactory(async ()=>{
    return new Promise((s,f)=>{
        try{
            // 七牛云配置
            s(cfg);
        }catch(e){
            f(e);
        }
    })
});

const tempFile:IFile;
const file = qiniuFactory.buildFile(qiniuCfg.bucket, tempFile.name);
// 上传文件
await file.write(tempFile);
```
