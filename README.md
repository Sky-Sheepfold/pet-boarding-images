# pet-boarding-images

宠物寄养管理系统的图片存储仓库，由系统后端通过 GitHub Contents API 自动写入，请勿手动修改。

## 目录结构

```
images/
├── care-records/    日常护理记录照片
├── pets/            宠物档案照片
├── avatars/         用户头像
└── temp/            临时上传
```

各分类下按 `YYYY/MM/<uuid>.jpg` 存放。

## 访问方式

图片通过 jsDelivr CDN 访问：

```
https://cdn.jsdelivr.net/gh/Sky-Sheepfold/pet-boarding-images@<commit-sha>/images/<分类>/<年>/<月>/<uuid>.jpg
```

URL 中使用 commit sha 而非分支名，以保证内容永久有效、上传后立即可访问。
