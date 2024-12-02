# kqUi

## 动画

### 折叠组件

#### 使用方式

```
import React, { useState } from 'react';
import { Shadow, Space, Fold, Button, PartTitle } from '@kqinfo/ui';

export default () => {
  const [folded, setFolded] = useState(false);
  return (
    <Space vertical size={'10px'} alignItems={'flex-start'}>
      <PartTitle>一般用法</PartTitle>
      <Button type={'primary'} onTap={() => setFolded(!folded)}>
        切换
      </Button>
      <Fold folded={folded}>
        我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容
      </Fold>
    </Space>
  );
};
```

#### API

| 属性名    | 描述         | 类型            | 默认值  |
| :-------- | :----------- | :-------------- | :------ |
| folded    | 是否折叠     | `boolean`       | `false` |
| maxHeight | 手动设置高度 | `string`        | `-`     |
| animation | -            | `boolean`       | `-`     |
| className | -            | `string`        | `-`     |
| style     | -            | `CSSProperties` | `-`     |

### Rotate 旋转

#### 使用方式

```
import React, { useState } from 'react';
import { Rotate, Icon, Space, PartTitle, Button } from '@kqinfo/ui';

export default () => {
  const [run, setRun] = useState(false);
  return (
    <Space vertical size={'10px'} alignItems={'flex-start'}>
      <PartTitle>一般用法</PartTitle>
      <Rotate>
        <Icon name={'kq-loading'} />
      </Rotate>
      <PartTitle>手动触发</PartTitle>
      <Rotate run={run} angle={180}>
        <Icon name={'kq-down'} />
      </Rotate>
      <Button onTap={() => setRun(!run)} type={'primary'}>
        切换
      </Button>
    </Space>
  );
};
```

#### API

| 属性名    | 描述     | 类型            | 默认值 |
| :-------- | :------- | :-------------- | :----- |
| angle     | 旋转角度 | `number`        | `-`    |
| run       | 是否旋转 | `boolean`       | `-`    |
| className | -        | `string`        | `-`    |
| style     | -        | `CSSProperties` | `-`    |

## 业务组件

### FaceVerify 人脸识别

#### 使用方式

```
import React from 'react';
import { FaceVerify } from '@kqinfo/ui';

export default () => {
  return <FaceVerify name={'小明'} no={'32132132131'} />;
};
```

#### API

| 属性名                  | 描述                    | 类型         | 默认值 |
| :---------------------- | :---------------------- | :----------- | :----- |
| onSuccess               | 成功事件                | `() => void` | `-`    |
| name                    | 姓名，小程序需要        | `string`     | `-`    |
| no                      | 身份证号，小程序需要    | `string`     | `-`    |
| request_verify_pre_info | web端需要，用户身份信息 | `string`     | `-`    |
| appid                   | web端需要，公众id       | `string`     | `-`    |

### HealthCard 患者健康卡

#### 使用说明

```
import React from 'react';
import { HealthCard } from '@kqinfo/ui';

export default () => {
  return <HealthCard patientName={'小明'} patCardNo={'32132132131'} />;
};
```

#### API

| 属性名      | 描述     | 类型     | 默认值 |
| :---------- | :------- | :------- | :----- |
| patientName | 患者姓名 | `string` | `-`    |
| patCardNo   | 健康卡号 | `string` | `-`    |

### PatientCard 患者就诊卡

#### 使用说明

```
import React from 'react';
import { PatientCard } from '@kqinfo/ui';

export default () => {
  return (
    <PatientCard
      patientName={'小明'}
      patCardNo={'32132132131'}
      hisName={'凯桥医院'}
    />
  );
};
```

#### API

| 属性名      | 描述     | 类型     | 默认值 |
| :---------- | :------- | :------- | :----- |
| patientName | 患者姓名 | `string` | `-`    |
| patCardNo   | 就诊号   | `string` | `-`    |
| className   | -        | `string` | `-`    |
| hisName     | 医院名称 | `string` | `-`    |

### UserAuthorization 用户授权

#### 使用说明

```
import React from 'react';
import { UserAuthorization } from '@kqinfo/ui';

export default () => {
  return <UserAuthorization hisName={'北部宽仁医院'} />;
};
```

#### API

| 属性名          | 描述                               | 类型                                                  | 默认值   |
| :-------------- | :--------------------------------- | :---------------------------------------------------- | :------- |
| hisName         | 授权医院                           | `ReactNode`                                           | `(必选)` |
| hisCode         | 医院code，web端授权会用到          | `string`                                              | `-`      |
| aliScopes       | 支付宝小程序需要授权的权限         | `string[]`                                            | `-`      |
| onAuthorization | 授权事件                           | `(data: LoginData & GetUserInfoData) => Promise<any>` | `(必选)` |
| logo            | 医院logo，设置后将不会显示用户头像 | `string`                                              | `-`      |
| agreementUrl    | 用户协议链接                       | `string`                                              | `-`      |
| homeUrl         | 首页链接，点击暂不授权将会跳到首页 | `string`                                              | `-`      |

#### 展示

![image-20241108111034596](https://ylxgs-oss.oss-cn-beijing.aliyuncs.com/typora/202411081110717.png)