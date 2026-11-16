# pet-boarding-images

宠物店宠物寄养服务管理系统的图片存储仓库。

本仓库由系统后端通过 GitHub Contents API 自动写入，**请勿手动修改文件**，
否则系统里保存的图片地址会失效。

## 目录结构

图片按业务用途分类，按年月分层，文件名使用 UUID：

```
images/
├── care-records/    日常护理记录照片（喂食、换水、清洁、遛宠、健康观察）
│   └── YYYY/MM/<uuid>.jpg
├── pets/            宠物档案照片
│   └── YYYY/MM/<uuid>.jpg
├── avatars/         用户头像
│   └── YYYY/MM/<uuid>.jpg
└── temp/            临时上传，可定期清理
```

## 访问方式

图片通过 jsDelivr CDN 访问，URL 中带的是 commit sha 而非分支名：

```
https://cdn.jsdelivr.net/gh/Sky-Sheepfold/pet-boarding-images@<commit-sha>/images/<分类>/<年>/<月>/<uuid>.jpg
```

之所以用 commit sha：jsDelivr 对分支引用最多缓存 12 小时，刚上传的图片可能很久都看不到；
而 commit sha 是 immutable 的，内容永久有效、上传后立即可访问。

## 为什么不设私有

jsDelivr 只索引公开仓库，私有仓库无法通过 CDN 访问。
如果图片需要保密，应改用后端代理读取，而不是依赖本仓库的可见性控制。

## 注意

- 本仓库由脚本自动维护，垃圾文件会被清理
- 仓库体积增长会影响克隆速度，历史图片不需要时应删除而非保留
