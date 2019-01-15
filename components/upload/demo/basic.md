---
order: 0
title:
  zh-CN: 点击上传
  en-US: Upload by clicking
---

## zh-CN

经典款式，用户点击按钮弹出文件选择框。

## en-US

Classic mode. File selection dialog pops up when upload button is clicked.

````jsx
import {
  Upload, message, Button, Icon,
} from 'antd';

const props = {
  name: 'file',
  action: '//jsonplaceholder.typicode.com/posts/',
  headers: {
    authorization: 'authorization-text',
  },
  onChange(info) {
    if (info.file.status !== 'uploading') {
      console.log(info.file, info.fileList);
      alert(2)
    }
    if (info.file.status === 'done') {
    alert(2)
      message.success(`${info.file.name} file uploaded successfully`);
    } else if (info.file.status === 'error') {
    alert(3)
      message.error(`${info.file.name} file upload failed.`);
    }
  },
};

ReactDOM.render(
  <Upload {...props}>
    <Button>
      <Icon type="upload" /> Click to Upload
    </Button>
  </Upload>,
  mountNode
);
````
