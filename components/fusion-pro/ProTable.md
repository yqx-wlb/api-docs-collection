## 场景: 地址选择器

## 示例

### Demo1: 常规使用

```tsx
import React, { useState } from 'react';
import { Form, Field } from '@alifd/next';
import { ProAddressSelect } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const field = Field.useField({
    values: {
      fullarea: ['北京市', '北京市', '朝阳区'],
      area: [],
    },
  });

  return (
    <Form field={field}>
      <Form.Item>
        <ProAddressSelect name="fullarea" style={{ width: 300 }} />
        <div> {field.values.fullarea.join(',')} </div>
      </Form.Item>
      <Form.Item>
        <ProAddressSelect
          valueKey="adCode"
          name="area"
          style={{ width: 300 }}
        />
        <div> {field.values.area.join(',')} </div>
      </Form.Item>
    </Form>
  );
};
```

## API

### ProAddressSelect

| 参数                                   | 说明         | 类型                        | 必填 | 默认值 |
| :------------------------------------- | :----------- | :-------------------------- | :--- | :----- |
| name                                   | 表单项名称   | `String`                    | 否   | --     |
| value                                  | 地址值       | `String[]`                  | 否   | --     |
| onChange                               | 地址改变回调 | `(value: String[]) => void` | 否   | --     |
| valueKey ｜选项的 value 值 ｜ `String` | 否           | name                        |

其它参数参考 [fusion CascaderSelect 组件](https://fusion.design/pc/component/cascader-select?themeid=2#Cascader%20Select)

## 场景: 数据展示

## 示例

### Demo1: 常规使用

```tsx
import React, { useState } from 'react';
import { NumberPicker } from '@alifd/next';
import { ProDescription } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const [curCol, setCurCol] = useState(3);
  const data = new Array(20).fill(0).map((v, i) => ({
    label: `label-${i + 1}`,
    value: `展示内容-${i + 1}`,
  }));

  const handleChange = (col: number) => {
    setCurCol(col);
  };

  return (
    <>
      <ProDescription
        data={[
          {
            label: '每行列数',
            value: (
              <NumberPicker
                value={curCol}
                min={1}
                max={24}
                onChange={handleChange}
              />
            ),
          },
        ]}
        col={1}
      />
      <ProDescription title="标题" data={data} col={curCol} />
    </>
  );
};
```

## API

### ProDescription

| 参数      | 说明         | 类型                                            | 必填 | 默认值 |
| :-------- | :----------- | :---------------------------------------------- | :--- | :----- |
| title     | 标题         | `String`                                        | 否   | --     |
| data      | 展示内容     | `{label: String; value: String \| ReactNode}[]` | `是` | `true` |
| col       | 一行展示几列 | `Number`                                        | 否   | `3`    |
| className | class 名     | `String`                                        | 否   | --     |

## 场景: 创建、编辑 keyfrom

## 示例

### Demo1:创建 keyfrom 弹窗

```tsx
import React, { useRef } from 'react';
import { Button, Dialog } from '@alifd/next';
import { ProKeyfrom } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const showCreateActivityKeyfromModal = () => {
    const dialog = Dialog.show({
      title: '新建投放方案',
      content: (
        <ProKeyfrom onOk={() => dialog.hide()} onCancel={() => dialog.hide()} />
      ),
      footer: false,
    });
  };
  return (
    <Button onClick={showCreateActivityKeyfromModal} type="primary">
      新建keyfrom
    </Button>
  );
};
```

### Demo2:编辑 keyfrom，示例使用测试 keyfromId=284993

```tsx
import React, { useRef } from 'react';
import { Button, Dialog } from '@alifd/next';
import { ProKeyfrom } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const showKeyfromModal = () => {
    const dialog = Dialog.show({
      title: '编辑投放方案',
      content: (
        <ProKeyfrom
          type="edit"
          id={284993}
          cancelText="取消"
          onOk={() => dialog.hide()}
          onCancel={() => dialog.hide()}
        />
      ),
      footer: false,
    });
  };
  return (
    <Button onClick={showKeyfromModal} type="primary">
      编辑keyfrom(id=284993)
    </Button>
  );
};
```

## API

组件的其他参数可以透传

### ProSelectChannel

| 参数           | 说明                    | 类型       | 必填                | 默认值   |
| :------------- | :---------------------- | :--------- | :------------------ | :------- |
| type           | 编辑'edit'/新建'create' | `String`   | 否                  | 'create' |
| id             | 关联的旧版落地页 id     | `Number`   | 否                  | --       |
| activityId     | 关联的新版落地页 id     | `Number`   | 否                  | --       |
| id             | 编辑的 keyfromId        | `Number`   | type==='edit'时必填 | --       |
| cancelText     | 取消按钮文案            | `String`   | 否                  | 取消     |
| onCancel       | 取消后的回调            | `function` | 否                  | --       |
| onOk           | 保存成功后的回调        | `function` | 否                  | --       |
| channelNameMap | 渠道 map                | `object`   | 否                  |          |

#### ref 方法

| 参数        | 说明         | 类型       | 默认值 |
| :---------- | :----------- | :--------- | :----- |
| refreshData | 刷新渠道数据 | `Function` | --     |

## 场景：级别选择器

## 示例

### Demo1

```tsx
import React from 'react';
import { Button, Icon, Field, Form, Radio } from '@alifd/next';
import { ProLevelSelect } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const field = Field.useField({
    values: {
      // level: '3-100',
      // levels: ['3-100', '3-101', '3-102'],
    },
  });

  const submit = () => {
    field.validate((errs, vals) => {
      console.log(errs);
      console.log(vals);
    });
  };

  return (
    <Form field={field} labelCol={{ span: 4 }} wrapperCol={{ span: 16 }} colon>
      <Form.Item label="级别">
        <ProLevelSelect name="level" />
      </Form.Item>
      <Form.Item label="多级别">
        <ProLevelSelect name="levels" multiple allLevel={false} />
      </Form.Item>
      <Form.Item label="是否有级别">
        <Radio.Group name="hasLevel">
          <Radio value>是</Radio>
          <Radio value={false}>否</Radio>
        </Radio.Group>
      </Form.Item>
      {!!field.getValue('hasLevel') && (
        <Form.Item label="隐藏级别" required requiredMessage="不能为空">
          <ProLevelSelect name="hiddenLevel" />
        </Form.Item>
      )}
      <Button onClick={submit}>提交</Button>
    </Form>
  );
};
```

## API

组件的其他参数可以透传

### ProLevelSelect

| 参数         | 说明                                         | 类型      | 必填 | 默认值  |
| :----------- | :------------------------------------------- | :-------- | :--- | :------ |
| name         | name                                         | `String`  | 否   | --      |
| allLevel     | 是否展示全部级别，`false`只展示 3.0 版本级别 | `Boolean` | 否   | `true`  |
| hasClear     | 是否展示清除按钮                             | `Boolean` | 否   | `true`  |
| disabled     | 是否置灰                                     | `Boolean` | 否   | `false` |
| multiple     | 是否多选                                     | `Boolean` | 否   | `false` |
| dataSource   | 指定选项                                     | `Array`   | 否   | --      |
| style        | 选择框样式                                   | `Object`  | 否   | --      |
| otherOptions | 其他透传属性                                 | `Object`  | 否   | --      |

## 场景: 操作日志展示

## 示例

### Demo1: 常规使用

```tsx
import React, { useState } from 'react';
import { ProOperatorLog } from '@yuanfudao/ada-fusion-pro';

export default () => {
  return (
    <ProOperatorLog
      idType="ada_coupon_template_id"
      id={1}
      changeUrlSearch={false}
    />
  );
};
```

## API

### ProOperatorLog

| 参数                  | 说明                                       | 类型            | 必填 | 默认值  |
| :-------------------- | :----------------------------------------- | :-------------- | :--- | :------ |
| idType                | 辅导操作日志接口参数                       | `String`        | `否` | --      |
| bizKey                | 电商操作日志接口参数，不传则默认为辅导接口 | `String`        | `否` | --      |
| id                    | 操作日志接口参数                           | `Number/String` | `是` | --      |
| changeUrlSearch       | 是否修改 url                               | `Boolean`       | 否   | `false` |
| pageSize              | 分页大小                                   | `Number`        | 否   | `20`    |
| refresh               | 改变参数刷新数据                           | `Boolean`       | 否   | `true`  |
| tableWidth            | 表格宽度                                   | `Number`        | 否   | --      |
| showLink              | 是否可下载操作日志中的 xsl、csv            | `Boolean`       | 否   | `false` |
| changePageIsScrollTop | 翻页是否自动滚动到页面部                   | `Boolean`       | 否   | `false` |

## 场景: 展示加密手机号，点击解密

## 示例

### Demo1: 常规使用

```tsx
import React from 'react';
import { Form, Field } from '@alifd/next';
import { ProPhone } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const field = Field.useField({
    values: {
      phone: '178****4238',
    },
  });

  return (
    <Form
      field={field}
      labelCol={{ fixedSpan: 10 }}
      wrapperCol={{ fixedSpan: 20 }}
    >
      <Form.Item label="显示解密手机号【类型0】：">
        <div style={{ lineHeight: '32px' }}>
          <ProPhone
            type={0}
            phone="178****4238"
            userId={200822938}
            logType={384}
            logId={1}
            tooltipOptions={{ align: 't' }}
          />
        </div>
      </Form.Item>
      <Form.Item label="显示解密手机号【类型1】：">
        <div style={{ lineHeight: '32px' }}>
          <ProPhone
            type={1}
            phone="177****3931"
            v2
            id={62021}
            decryptType={8}
            logType={392}
            logId={2066}
          />
        </div>
      </Form.Item>
      <Form.Item label="显示解密手机号【类型2】：">
        <ProPhone
          name="phone"
          phone={field.getValue('phone')}
          type={2}
          showPhoneBtnVisible
          userId={200822938}
          logType={384}
          logId={1}
          inputProps={{ disabled: true }}
        />
      </Form.Item>
      <Form.Item label="解密接口v3：">
        <div style={{ lineHeight: '32px' }}>
          <ProPhone
            phone="155****3320"
            v3
            id={18828535}
            decryptType={2}
            logId={394270417}
            logKey="ada_commerce_ybc_order"
          />
        </div>
      </Form.Item>
      <Form.Item label="显示解密手机号【自定义请求】：">
        <ProPhone
          phone="155****3320"
          customRequest={() => {
            return Promise.resolve({
              phone: '15523423320',
              userId: 200822938,
            }).then(res => {
              console.log(res);
              return res.phone;
            });
          }}
          v2
        />
      </Form.Item>
    </Form>
  );
};
```

## API

### ProPhone

| 参数                                  | 说明                                       | 类型                  | 必填 | 默认值  |
| :------------------------------------ | :----------------------------------------- | :-------------------- | :--- | :------ |
| phone                                 | 手机号                                     | `String \| Number`    | 否   | --      |
| type                                  | 展示类型，具体样式见示例                   | `Number: 0 \| 1 \| 2` | 否   | `0`     |
| showPhoneBtnVisible                   | 是否展示解密按钮，在 type=2 时增加解密按钮 | `Boolean`             | 否   | `false` |
| v2                                    | 手机号解密用的接口版本是否为 v2            | `Boolean`             | 否   | `false` |
| v3                                    | 手机号解密接口版本是否为 v3                | `Boolean`             | 否   | `false` |
| userId, shipmentId, receiptId, taskId | 解密所需 id，v1 接口必传几个参数之一       | `String \| Number`    | 否   | --      |
| id                                    | 解密所需 id，v2 和 v3 接口必传             | `Number`              | 否   | --      |
| decryptType                           | 解密类型，v2 和 v3 接口必传                | `Number`              | 否   | --      |
| logId                                 | 加操作日志的主体 id，三个接口都要传        | `Number`              | 否   | --      |
| logType                               | 操作日志的记录类型，v1 和 v2 必传          | `Number`              | 否   | --      |
| logKey                                | v3 接口操作日志的记录类型                  | `String`              | 否   | --      |
| name                                  | 手机号字段                                 | `String`              | 否   | --      |
| tooltipOptions                        | 配置弹层属性                               | Fusion `Tooltip`      | 否   | --      |
| inputProps                            | 配置输入框属性                             | Fusion `Input`        | 否   | --      |
| url                                   | 已解密手机号点击是否跳转新页面             | `String`              | 否   | --      |

## 场景: 图片预览

## 示例

### Demo1: 单张图片预览

```tsx
import React from 'react';
import { ProPreviewImage } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const testImages = [
    'https://img-pub.fbcontent.cn/ybcweapp/images/1ekoczt35.png',
  ];
  return (
    <>
      <div style={{ marginBottom: '12px' }}>图片触发预览弹窗</div>
      <ProPreviewImage
        urls={testImages}
        maxWidth={600}
        hintText="这是弹窗内的一条提示文案"
        style={{ width: 200, cursor: 'pointer' }}
      />
      <div style={{ margin: '36px 0 12px 0' }}>按钮触发预览弹窗</div>
      <ProPreviewImage
        useButton
        urls={testImages}
        maxWidth={600}
        hintText="这是弹窗内的一条提示文案"
        style={{ width: 200, cursor: 'pointer' }}
      />
    </>
  );
};
```

### Demo2: 多张图片预览

```tsx
import React from 'react';
import { ProPreviewImage } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const testImages = [
    'https://img-pub.fbcontent.cn/ybcweapp/images/5zlul4rpp.jpg',
    'https://img-pub.fbcontent.cn/ybcweapp/images/zaodspbob.jpeg',
    'https://img-pub.fbcontent.cn/ybcweapp/images/1ekoczt35.png',
  ];
  return (
    <ProPreviewImage
      urls={testImages}
      maxWidth={600}
      initIdx={1}
      buttonText="点击查看多张图片"
      buttonProps={{ size: 'large', type: 'normal' }}
    />
  );
};
```

## API

### ProPreviewImage

| 参数           | 说明                                                                             | 类型                  | 必填 | 默认值     |
| :------------- | :------------------------------------------------------------------------------- | :-------------------- | :--- | :--------- |
| urls           | 图片 url 数组，单张图片传一个即可                                                | `String[]`            | 是   | []         |
| style          | 触发预览弹窗的外部图片样式                                                       | `React.CSSProperties` | 否   | --         |
| className      | 触发预览弹窗的外部图片的类名                                                     | `String`              | 否   | --         |
| innerClassName | 预览弹窗内图片的类名                                                             | `String`              | 否   | --         |
| maxWidth       | 预览弹窗内图片的最大宽度（px）                                                   | `Number`              | 否   | 1000       |
| title          | 预览弹窗标题                                                                     | `String`              | 否   | '图片预览' |
| hintText       | 预览弹窗提示文案，在图片上方展示                                                 | `String`              | 否   | --         |
| useButton      | 单张图片是否使用按钮打开预览弹窗（多张图片只能为按钮，单张图片默认优先展示图片） | `Boolean`             | 否   | false      |
| buttonText     | 按钮文案                                                                         | `String`              | 否   | '查看图片' |
| buttonProps    | 按钮属性                                                                         | `ButtonProps`         | 否   | --         |
| initIdx        | 预览弹窗内多图片默认显示的图片索引                                               | `Number`              | 否   | 0          |

## 场景: 选择渠道

## 示例

### Demo1: 常规使用

```tsx
import React, { useState } from 'react';
import { ProSelectChannel } from '@yuanfudao/ada-fusion-pro';
import { Form, Field, Button } from '@alifd/next';

export default () => {
  const field = Field.useField({
    values: {
      selectedChannels: [],
    },
  });

  // 递归遍历
  const loop = (data, chosen: string[] = []) => {
    // console.log('chosen', chosen);
    return data.map(item => {
      return {
        ...item,
        value: `${item.value}`,
        disabled: chosen.includes(`${item.value}`), // 过滤掉已经选择的
        children: item.children ? loop(item.children, chosen) : null,
      };
    });
  };

  return (
    <div>
      <Button
        onClick={() => {
          alert(JSON.stringify(field.getValues()));
        }}
      >
        value
      </Button>
      <Form
        field={field}
        labelCol={{ fixedSpan: 10 }}
        wrapperCol={{ fixedSpan: 20 }}
      >
        <Form.Item label="渠道（三级，多选）">
          <ProSelectChannel name="selectedChannels" disabledItems={['48']} />
        </Form.Item>
        <Form.Item label="渠道（一级，多选）">
          <ProSelectChannel name="selectedChannels1" level={1} />
        </Form.Item>
        <Form.Item label="渠道（三级，多选，过滤）">
          <ProSelectChannel
            name="selectedChannels3"
            level={3}
            filterFn={(item: any, level: number) => {
              return (level === 1 && item.value === 75) || level > 1;
            }}
          />
        </Form.Item>
        <Form.Item label="渠道（三级，单选）">
          <ProSelectChannel
            name="selectedChannels2"
            strictLevel
            multiple={false}
          />
        </Form.Item>
        <Form.Item label="渠道（三级，自定义数据）">
          <ProSelectChannel
            name="selectedChannels4"
            strictLevel
            customDataSource={data => {
              return loop(data, ['48', '65']);
            }}
          />
        </Form.Item>
      </Form>
    </div>
  );
};
```

### Demo2: 刷新数据

```tsx
import React, { useState, useRef, useEffect } from 'react';
import { ProSelectChannel, getChannelData } from '@yuanfudao/ada-fusion-pro';
import { Button } from '@alifd/next';

export default () => {
  const ref = useRef(null);
  useEffect(() => {
    getChannelData().then(data => {
      console.log(data);
    });
  }, []);

  return (
    <div>
      <Button
        onClick={() => {
          ref.current?.refreshData();
        }}
      >
        刷新数据
      </Button>
      <ProSelectChannel ref={ref} name="selectedChannels" />
    </div>
  );
};
```

## API

组件的其他参数可以透传

### ProSelectChannel

| 参数             | 说明                                                                                                 | 类型                                                  | 必填 | 默认值                          |
| :--------------- | :--------------------------------------------------------------------------------------------------- | :---------------------------------------------------- | :--- | :------------------------------ |
| name             | name                                                                                                 | `String`                                              | 否   | --                              |
| level            | 层级                                                                                                 | `Number`                                              | 否   | `3`                             |
| multiple         | 多选                                                                                                 | `Boolean`                                             | 否   | `true`                          |
| disabled         | disabled                                                                                             | `Boolean`                                             | 否   | `false`                         |
| disabledItems    | 禁用选项                                                                                             | `Array`                                               | 否   | `false`                         |
| strictLevel      | 如果当前层级小于指定层级，且没有子节点，则禁用，多选模式只能勾选子节点用`canOnlyCheckLeaf`再加上这个 | `Boolean`                                             | 否   | `false`                         |
| filterFn         | 过滤节点                                                                                             | `(item: ChannelItem, currentLevel:number) => Boolean` | 否   | `()=>true`                      |
| customDataSource | 自定义数据源                                                                                         | `(data: ChannelItem[]) => data`                       | 否   | `(data: ChannelItem[]) => data` |

#### ref 方法

| 参数        | 说明         | 类型       | 默认值 |
| :---------- | :----------- | :--------- | :----- |
| refreshData | 刷新渠道数据 | `Function` | --     |

#### 其他方法

| 参数           | 说明         | 类型       | 定义                                                                |
| :------------- | :----------- | :--------- | :------------------------------------------------------------------ |
| getChannelData | 获取渠道数据 | `Function` | `(force?: boolean)=>data` force 为 true 从接口取，否则从 session 取 |

## 场景: 选择用户群组

## 示例

### Demo1: 常规使用

> 配合 Form 表单使用

```tsx
import React, { useState } from 'react';
import { ProSelectGroup } from '@yuanfudao/ada-fusion-pro';
import { Form, Field, Button } from '@alifd/next';

export default () => {
  const field = Field.useField({
    values: {
      visibleUserGroup: [],
    },
  });

  return (
    <div>
      <Button
        onClick={() => {
          alert(JSON.stringify(field.getValues()));
        }}
      >
        value
      </Button>
      <Form
        field={field}
        labelCol={{ fixedSpan: 10 }}
        wrapperCol={{ fixedSpan: 20 }}
      >
        <Form.Item label="用户群组">
          <ProSelectGroup name="visibleUserGroup" />
        </Form.Item>
        <Form.Item label="猿辅导用户群组">
          <ProSelectGroup name="visibleYfdUserGroup" isYFD />
        </Form.Item>
      </Form>
    </div>
  );
};
```

## API

### ProSelectGroup

| 参数      | 说明                 | 类型                                      | 必填 | 默认值     |
| :-------- | :------------------- | :---------------------------------------- | :--- | :--------- |
| name      | 表单 name            | `String`                                  | `是` | --         |
| value     | 组件 value           | `Number[]`                                | `否` | --         |
| onChange  | onChange             | `Function`                                | `否` | --         |
| disabled  | 是否禁用             | `Boolean`                                 | `否` | `false`    |
| mode      | 组件 mode            | `'multiple' /'single' / 'tag' /undefined` | `否` | `multiple` |
| isYFD     | 是否是猿辅导群组     | `Boolean`                                 | `否` | `false`    |
| filterCsv | 是否只支持自定义群组 | `Boolean`                                 | `否` | `false`    |

## 场景: 根据组织架构选择员工弹窗

## 示例

### Demo1: 常规使用

```tsx
import React, { useState, useRef } from 'react';
import { Button, Table } from '@alifd/next';
import { ProStaffSelect } from '@yuanfudao/ada-fusion-pro';
import moment from 'moment';

export default () => {
  const addStaffDialogRef = useRef(null);
  const [personList, setPersonList] = useState([]);

  return (
    <>
      <Button
        type="primary"
        onClick={() => {
          addStaffDialogRef.current?.open(personList);
        }}
        name="personList"
      >
        选择员工
        <span style={{ marginLeft: 4 }}>
          {personList?.length ? `(${personList.length})` : ''}
        </span>
      </Button>
      <Table
        style={{ marginTop: 20 }}
        primaryKey="ldap"
        dataSource={personList}
        hasBorder={false}
      >
        <Table.Column width={90} title="姓名" dataIndex="name" />
        <Table.Column width={90} title="地区" dataIndex="workCity" />
        <Table.Column width={110} title="ldap" dataIndex="ldap" />
        <Table.Column
          width={130}
          title="入职时间"
          dataIndex="entryDate"
          cell={v => (v ? moment(v).format('YYYY.MM.DD') : '-')}
        />
      </Table>
      <ProStaffSelect
        handleStaff={data => {
          setPersonList(data);
          addStaffDialogRef.current?.close();
        }}
        ref={addStaffDialogRef}
      />
    </>
  );
};
```

## API

### ProStaffSelect

| 参数        | 说明         | 类型       | 必填 | 默认值 |
| :---------- | :----------- | :--------- | :--- | :----- |
| handleStaff | 数据回传方法 | `Function` | `是` | --     |

### ProStaffSelect Ref 说明

| current 属性 | 说明                                                   | 类型         |
| :----------- | :----------------------------------------------------- | :----------- |
| open         | 打开弹窗方法                                           | `() => void` |
| close        | 关闭弹窗方法(为满足交互，弹窗不会自动关闭，需手动调用) | `() => void` |

## 场景: 状态展示

## 示例

### Demo1: 常规使用

```tsx
import React, { useState } from 'react';
import { ProStatusRender } from '@yuanfudao/ada-fusion-pro';
export default () => {


  return (
    <>
      <ProStatusRender><div >default</div></ProStatusRender>
      <ProStatusRender type="primary">primary</ProStatusRender>
      <ProStatusRender type="success">success</ProStatusRender>
      <ProStatusRender type="error">error</ProStatusRender>
      <ProStatusRender type="warning">warning</ProStatusRender>
    </>
  );
};
```

## API

### ProStatusRender

| 参数      | 说明         | 类型                                            | 必填 | 默认值 |
| :-------- | :----------- | :---------------------------------------------- | :--- | :----- |
| type     | 类型         | `String`                                        | 否   | default    |

---
title: ProTable - 表格搜索
---

## 描述

#### 基于 Fusion Table 二次封装, 满足大部分日常表格类需求

---

## TIPS

```
1. table: { columns: Table.Column[] } 与 <Table.Column />效果相同， 后者优先级最高

2. <ProTable table={{}}/> table无内容时也需传入，当前存在循环render问题

3. url参数区分为搜索表单参数、额外拼接参数，initParams不会拼入url
```

## 业务开发常用示例

### Demo1: 常规使用

#### columns JSON 写法

```tsx
import React from 'react';
import Moment from 'moment';
import { Button, Table, Icon, Balloon } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = (params, isSort) => {
    console.log('是否重置', isSort, params);
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demo',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 20,
            totalItem: 100,
            totalPage: 1,
          },
        });
      }, 20);
    });
  };

  const organizations = [
    {
      label: '1级结构1',
      value: '1级结构1',
      children: [
        {
          label: '2级结构2',
          value: '2级结构2',
          children: [
            {
              label: '3级结构3',
              value: '3级结构3',
              children: [
                {
                  label: '4级结构4',
                  value: '4级结构4',
                  children: [
                    { label: '5级结构5', value: '5级结构5' },
                    { label: '5级结构6', value: '5级结构6' },
                    { label: '5级结构7', value: '5级结构7' },
                  ],
                },
                {
                  label: '4级结构8',
                  value: '4级结构8',
                  children: [
                    { label: '5级结构9', value: '5级结构9' },
                    { label: '5级结构10', value: '5级结构10' },
                    { label: '5级结构11', value: '5级结构11' },
                  ],
                },
                {
                  label: '4级结构12',
                  value: '4级结构12',
                  children: [{ label: '5级结构13', value: '5级结构13' }],
                },
              ],
            },
            {
              label: '3级结构14',
              value: '3级结构14',

              children: [
                {
                  label: '3级结构14',
                  value: '3级结构14',

                  children: [
                    { label: '5级结构16', value: '5级结构16' },
                    { label: '5级结构17', value: '5级结构17' },
                    { label: '5级结构18', value: '5级结构18' },
                  ],
                },
              ],
            },
          ],
        },
        {
          label: '2级结构19',
          value: '2级结构19',

          children: [
            {
              label: '3级结构20',
              value: '3级结构20',

              children: [
                {
                  label: '4级结构21',
                  value: '4级结构21',

                  children: [
                    { label: '5级结构22', value: '5级结构22' },
                    { label: '5级结构23', value: '5级结构23' },
                  ],
                },
                {
                  label: '4级结构24',
                  value: '4级结构24',

                  children: [{ label: '5级结构25', value: '5级结构25' }],
                },
              ],
            },
          ],
        },
        {
          label: '2级结构26',
          value: '2级结构26',

          children: [
            {
              label: '3级结构27',
              value: '3级结构27',

              children: [
                {
                  label: '4级结构28',
                  value: '4级结构28',

                  children: [{ label: '5级结构29', value: '5级结构29' }],
                },
              ],
            },
          ],
        },
      ],
    },
  ];

  const table = {
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
        selectUnchecked: true,
      },
      {
        title: '年龄',
        dataIndex: 'age',
        cell: (value: string) => <>{value + '岁'}</>,
        expand: {
          name: 'ages',
          type: 'numberPicker',
        },
      },
      {
        title: '兴趣',
        align: 'center',
        children: [
          {
            title: (
              <span>
                兴趣1
                <Balloon
                  align="t"
                  autoAdjust={false}
                  trigger={
                    <Icon
                      type="help"
                      size="small"
                      style={{ marginLeft: '2px' }}
                    />
                  }
                >
                  兴趣1-ballon
                </Balloon>
              </span>
            ),
            dataIndex: 'interest_1',
          },
          {
            title: '兴趣2',
            dataIndex: 'interest_2',
          },
          {
            title: '兴趣3',
            dataIndex: 'interest_3',
          },
          {
            title: '兴趣4',
            dataIndex: 'interest_4',
          },
        ],
      },
    ],
  };

  const filter = [
    {
      label: '级别',
      name: 'programmingLevel',
      span: 8,
      type: 'selectLevel',
      initValue: '3,801',
    },
    {
      label: '分布',
      name: 'part',
      span: 8,
      type: 'selectPart',
    },
    {
      label: '输入框',
      name: 'inputDemo',
      span: 8,
      autoFormat: true,
      // type: 'input',
      options: {
        hasClear: true,
        placeholder: '请输入内容',
        autoComplete: 'on',
      },
    },
    {
      label: '数字输入框',
      name: 'numberPickerDemo',
      span: 8,
      type: 'numberPicker',
      options: {
        placeholder: '请输入数字',
      },
    },
    {
      label: '数字范围',
      name: 'numberRangeDemo',
      span: 8,
      type: 'numberRange',
      options: {
        hasTrigger: false,
        min: 0,
        max: 1e9,
        precision: 2,
        innerAfter: '元',
      },
    },
    {
      label: '选择框',
      name: 'selectDemo',
      span: 8,
      type: 'select',
      initValue: '',
      formItemProps: {
        extra: <p>我是附加内容</p>,
      },
      options: {
        enum: [
          {
            label: 'demo0',
            value: 0,
          },
          {
            label: 'demo1',
            value: 1,
          },
          {
            label: 'demo2',
            value: 2,
          },
        ],
        placeholder: '请选择内容',
      },
    },
    {
      label: '开关',
      name: 'switch',
      span: 8,
      type: 'switch',
      initValue: true,
      options: {
        autoWidth: true,
        checkedChildren: '已启用',
        unCheckedChildren: '已关闭',
        onChange: (v: any) => {
          console.log(123, v);
        },
      },
    },
    {
      label: '单选框',
      name: 'radioDemo',
      span: 8,
      type: 'radio',
      initValue: 2,
      options: {
        enum: [
          {
            label: 'demo1',
            value: 1,
          },
          {
            label: 'demo2',
            value: 2,
          },
          {
            label: 'demo3',
            value: 3,
          },
        ],
      },
    },
    {
      label: '特殊时间段',
      name: 'timeSpecial',
      span: 16,
      // initValue: [Moment().subtract(7, 'd'), Moment().subtract(0, 'd')],
      type: 'rangePicker',
      specialRange: true,
      defaultHidden: true,
      unit: 'minute',
      options: {
        hasClear: true,
        showTime: { format: 'HH:mm' },
        enum: [
          {
            label: '前天',
            value: '2',
          },
          {
            label: '昨天',
            value: '1',
          },
          {
            label: '今天',
            value: '0',
          },
          {
            label: '明天',
            value: '-1',
          },
          {
            label: '最近三天',
            value: '3',
          },
          {
            label: '最近七天',
            value: '7',
            // default: true,
          },
          {
            label: '最近一个月',
            value: '1/M',
          },
          {
            label: '最近三个月',
            value: '3/M',
          },
          {
            label: '最近一年',
            value: '1/Y',
          },
          {
            label: '未来三天',
            value: '-3',
          },
          {
            label: '未来一周',
            value: '-7',
          },
          {
            label: '未来一个月',
            value: '-1/M',
          },
          {
            label: '未来三个月',
            value: '-3/M',
          },
          {
            label: '未来一年',
            value: '-1/Y',
          },
        ],
      },
    },
    {
      label: '时间段',
      name: 'time',
      span: 16,
      initValue: [Moment().subtract(7, 'd'), Moment().subtract(0, 'd')],
      type: 'rangePicker',
      defaultHidden: true,
      options: {
        hasClear: true,
        showTime: { format: 'HH:mm:ss' },
        enum: [
          {
            label: '昨天',
            value: '1',
          },
          {
            label: '今天',
            value: '0',
          },
          {
            label: '最近七天',
            value: '7',
            default: true,
          },
          {
            label: '最近一个月',
            value: '1/M',
          },
          {
            label: '最近一年',
            value: '1/Y',
          },
        ],
      },
    },
    {
      label: '时间段2',
      name: 'time2',
      span: 16,
      type: 'rangePicker2',
      unit: 'minute',
      defaultHidden: true,
      options: {
        showTime: true,
        format: 'YYYY-MM-DD HH:mm',
        timePanelProps: { format: 'HH:mm' },
      },
    },
    {
      label: '树形选择',
      name: 'treeSelect',
      span: 8,
      type: 'treeSelect',

      options: {
        treeDefaultExpandAll: true,
        onChange: (_v, data, field) => {
          let formatStr = '';
          let organizationsArr: any = organizations.slice(0);
          const result = data.pos.split('-').slice(1);
          const len = result.length;
          result.forEach((idx, index) => {
            formatStr += `${organizationsArr[idx].value}${
              organizationsArr[idx].children && index < len - 1 ? '-' : ''
            }`;
            if (organizationsArr[idx].children) {
              organizationsArr = organizationsArr[idx].children;
            }
          });
          field.setValue('treeSelect', formatStr);
        },
        enum: organizations,
      },
    },
    {
      label: '选择渠道(多选)',
      name: 'selectChannelDemo',
      span: 8,
      type: 'selectChannel',
      options: {
        multiple: true,
        placeholder: '请输入内容',
      },
    },
    {
      label: '选择渠道(单选)',
      name: 'selectChannelDemo2',
      span: 8,
      type: 'selectChannel',
      options: {
        placeholder: '请输入内容',
      },
    },
    {
      label: '日期选择',
      name: 'datePickerDemo',
      span: 8,
      type: 'datePicker',
      options: {
        hasClear: true,
        showTime: false,
      },
    },
  ];
  return (
    <ProTable
      filter={filter}
      searchFn={getList}
      selectColumn
      selectColumnStorageKey="tableListDemo"
      selectColumnTitle={<Icon type="set" />}
      selectColumnInSession={false}
      filtersFoldable
      selectFilter
      selectFilterStorageKey="tableListDemoFilters"
      actionShow={<Button type="secondary">action区域自定义内容</Button>}
      leftShow={<Button type="secondary">table左上方区域自定义内容</Button>}
      rightShow={<Button type="secondary">table右上方区域自定义内容</Button>}
      changeUrlSearch
      clearParamsOnSearch={false}
      versionParamName="version"
      table={table}
    ></ProTable>
  );
};
```

#### Table.Column 组件写法

```tsx
import React from 'react';
import Moment from 'moment';
import { Button, Table } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = params => {
    console.log('getList', params);
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demo',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const filter = [
    {
      label: '输入框',
      name: 'inputDemo',
      span: 8,
      // type: 'input',
      options: {
        placeholder: '请输入内容',
      },
    },
    {
      label: '数字输入框',
      name: 'numberPickerDemo',
      span: 8,
      type: 'numberPicker',
      options: {
        placeholder: '请输入数字',
      },
    },
    {
      label: '选择框',
      name: 'selectDemo',
      span: 8,
      type: 'select',
      initValue: 1,
      options: {
        enum: [
          {
            label: 'demo1',
            value: 1,
          },
          {
            label: 'demo2',
            value: 2,
          },
          {
            label: 'demo3',
            value: 3,
          },
        ],
        placeholder: '请选择内容',
      },
    },

    {
      label: '单选框',
      name: 'radioDemo',
      span: 8,
      type: 'radio',
      initValue: 2,
      options: {
        enum: [
          {
            label: 'demo1',
            value: 1,
          },
          {
            label: 'demo2',
            value: 2,
          },
          {
            label: 'demo3',
            value: 3,
          },
        ],
      },
    },
    {
      label: '时间段',
      name: 'time',
      span: 16,
      initValue: [Moment().subtract(7, 'd'), Moment().subtract(7, 'd')],

      type: 'rangePicker',
      options: {
        enum: [
          {
            label: '昨天',
            value: '1',
          },
          {
            label: '今天',
            value: '0',
          },
          {
            label: '最近七天',
            value: '7',
            default: true,
          },
          {
            label: '最近一个月',
            value: '31',
          },
          {
            label: '最近一年',
            value: '365',
          },
        ],
      },
    },
  ];
  return (
    <ProTable
      filter={filter}
      searchFn={getList}
      selectColumn
      selectColumnStorageKey="tableListDemo"
      actionShow={<Button type="secondary">action区域自定义内容</Button>}
      leftShow={<Button type="secondary">table左上方区域自定义内容</Button>}
      rightShow={<Button type="secondary">table右上方区域自定义内容</Button>}
      changeUrlSearch={false}
      table={{}}
    >
      <Table.Column
        title="姓名"
        dataIndex="name"
        expand={{
          name: 'ages',
          type: 'numberPicker',
        }}
      />
      <Table.Column
        title="年龄"
        dataIndex="age"
        cell={(value: string) => <>{value + '岁'}</>}
      />
      <Table.ColumnGroup title="兴趣" align="center">
        <Table.Column title="兴趣1" dataIndex="interest_1" />
        <Table.Column title="兴趣2" dataIndex="interest_2" />
        <Table.Column title="兴趣3" dataIndex="interest_3" />
        <Table.Column title="兴趣4" dataIndex="interest_4" />
      </Table.ColumnGroup>
    </ProTable>
  );
};
```

### Demo2: 表格存在弹窗表单, 表单提交后触发更新

```tsx
import React, { useRef } from 'react';
import { Button, Divider } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const tableRef = useRef(null);
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demoName',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const table = {
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
      },
      {
        title: '年龄',
        dataIndex: 'age',
        cell: (value: string) => <>{value + '岁'}</>,
      },
      {
        title: '兴趣',
        align: 'center',
        children: [
          {
            title: '兴趣1',
            dataIndex: 'interest_1',
          },
          {
            title: '兴趣2',
            dataIndex: 'interest_2',
          },
          {
            title: '兴趣3',
            dataIndex: 'interest_3',
          },
          {
            title: '兴趣4',
            dataIndex: 'interest_4',
          },
        ],
      },
    ],
  };

  return (
    <ProTable
      leftShow={
        <>
          <Button type="primary" onClick={() => tableRef?.current?.refresh()}>
            刷新&第一页
          </Button>
          <Divider direction="ver" />
          <Button
            type="primary"
            onClick={() => tableRef?.current?.currentRefresh()}
          >
            刷新&当前页
          </Button>
        </>
      }
      ref={tableRef}
      searchFn={getList}
      changeUrlSearch={false}
      table={table}
    />
  );
};
```

### Demo3: 拖拽表格

```tsx
import React from 'react';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demoName',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const table = {
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
      },
      {
        title: '年龄',
        dataIndex: 'age',
        cell: (value: string) => <>{value + '岁'}</>,
      },
      {
        title: '兴趣',
        align: 'center',
        children: [
          {
            title: '兴趣1',
            dataIndex: 'interest_1',
          },
          {
            title: '兴趣2',
            dataIndex: 'interest_2',
          },
          {
            title: '兴趣3',
            dataIndex: 'interest_3',
          },
          {
            title: '兴趣4',
            dataIndex: 'interest_4',
          },
        ],
      },
    ],
  };

  const onDragEnd = (result: any) => {
    console.log(result);
  };

  return (
    <ProTable
      searchFn={getList}
      changeUrlSearch={false}
      drag={true}
      onDragEnd={onDragEnd}
      table={table}
    />
  );
};
```

### Demo4: 宽度动态计算

#### 1. 未设置 width 默认 140

#### 2. 如所有 width 相加所得 tableWidth < 可视容器宽度则为可视容器宽度，未设置 width 项自动分份，全部设置则按比例分份

#### 3. 如所有 width 相加所得 tableWidth >= 可视容器宽度则为 tableWidth，未设置 width 项自动分份，width 为绝对宽度

<br />

```tsx
import React from 'react';
import { Table } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demoName',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const table = {
    columns: [
      {
        title: '固定宽度200&左锁列',
        dataIndex: 'name',
        width: 200,
        lock: true,
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '自适应宽度',
        dataIndex: 'interest_1',
      },
      {
        title: '自适应宽度',
        dataIndex: 'interest_1',
      },
      {
        title: '自适应宽度',
        dataIndex: 'interest_1',
      },
      {
        title: '自适应宽度',
        dataIndex: 'interest_1',
      },
      {
        title: '自适应宽度',
        dataIndex: 'interest_1',
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '固定宽度500',
        dataIndex: 'interest_1',
        width: 500,
      },
      {
        title: '固定宽度200&右锁列',
        width: 200,
        dataIndex: 'interest_2',
        lock: 'right',
      },
    ],
  };

  return (
    <ProTable
      searchFn={getList}
      changeUrlSearch={false}
      table={table}
    ></ProTable>
  );
};
```

### Demo5: 排序表格 (ProTable 无此 case 处理, 延用 Fusion Table Api)

```js
// ProTable 排序参数处理
const handleSort = (dataIndex: string, order: string) => {
  const sortType = `${dataIndex} ${order.toUpperCase()}`;
  if (order === 'default') {
    setSortParams({});
  } else {
    setSortParams({ sortType });
  }
};
```

```tsx
import React from 'react';
import Moment from 'moment';
import { Button, Table } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              name: 'demo',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const table = {
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
      },
      {
        title: '年龄',
        dataIndex: 'age',
        sortable: true,
        sortDirections: ['desc', 'asc', 'default'],
        cell: (value: string) => <>{value + '岁'}</>,
      },
      {
        title: '兴趣1',
        dataIndex: 'interest_1',
        sortable: true,
        sortDirections: ['desc', 'asc', 'default'],
      },
      {
        title: '兴趣2',
        dataIndex: 'interest_2',
      },
      {
        title: '兴趣3',
        dataIndex: 'interest_3',
      },
      {
        title: '兴趣4',
        dataIndex: 'interest_4',
      },
    ],
  };

  return (
    <ProTable
      searchFn={getList}
      changeUrlSearch={false}
      table={table}
    ></ProTable>
  );
};
```

### Demo6: 选择表格 (ProTable 无此 case 处理, 延用 Fusion Table Api)

```tsx
import React, { useState } from 'react';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const [rowsKeys, setRowsKeys] = useState([]);
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map((_v, i) => ({
              custom_id: i + 1,
              name: 'demo',
              age: Math.floor(Math.random() * 50 + 10),
              interest_1: Math.floor(Math.random() * 1000),
              interest_2: Math.floor(Math.random() * 1000),
              interest_3: Math.floor(Math.random() * 1000),
              interest_4: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const handleChange = e => {
    console.log(e);
    setRowsKeys(e);
  };

  const table = {
    primaryKey: 'custom_id',
    selectedrowskeys: rowsKeys,
    rowSelection: {
      onChange: e => handleChange(e),
    },
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
      },
      {
        title: '年龄',
        dataIndex: 'age',
        cell: (value: string) => <>{value + '岁'}</>,
      },
      {
        title: '兴趣1',
        dataIndex: 'interest_1',
      },
      {
        title: '兴趣2',
        dataIndex: 'interest_2',
      },
      {
        title: '兴趣3',
        dataIndex: 'interest_3',
      },
      {
        title: '兴趣4',
        dataIndex: 'interest_4',
      },
    ],
  };

  return (
    <ProTable
      searchFn={getList}
      changeUrlSearch={false}
      table={table}
    ></ProTable>
  );
};
```

### Demo7: 表头筛选

#### Table.Column 组件写法

```tsx
import React from 'react';
import Moment from 'moment';
import { Button, Table, DatePicker, TreeSelect } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const getList = () => {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve({
          list: Array(10)
            .fill('')
            .map(() => ({
              a: Math.floor(Math.random() * 1000),
              b: Math.floor(Math.random() * 1000),
              c: Math.floor(Math.random() * 1000),
              d: Math.floor(Math.random() * 1000),
              e: Math.floor(Math.random() * 1000),
              f: Math.floor(Math.random() * 1000),
            })),
          pageInfo: {
            currentPage: 0,
            pageSize: 100,
            totalItem: 10,
            totalPage: 1,
          },
        });
      }, 2000);
    });
  };

  const filter = [
    {
      label: '输入框',
      name: 'inputDemo',
      span: 8,
      options: {
        placeholder: '请输入内容',
      },
    },
  ];

  const treeData = [
    {
      label: '1.0',
      value: 1,
      children: [
        { label: '2.0', value: 2 },
        { label: '2.1', value: 3 },
        { label: '2.2', value: 4, disabled: true },
      ],
    },
  ];
  return (
    <ProTable
      filter={filter}
      searchFn={getList}
      changeUrlSearch={false}
      table={{}}
    >
      <Table.Column
        title="input"
        expand={{
          name: 'input',
          type: 'input',
        }}
        dataIndex="a"
      />
      <Table.Column
        title="numberPicker"
        expand={{
          name: 'numberPicker',
          type: 'numberPicker',
        }}
        dataIndex="b"
      />
      <Table.Column
        title="radio"
        expand={{
          name: 'radio',
          type: 'radio',
          enum: [
            {
              label: '选项A',
              value: 'A',
            },
            {
              label: '选项B',
              value: 'B',
            },
            {
              label: '选项C',
              value: 'C',
            },
          ],
        }}
        dataIndex="c"
      />
      <Table.Column
        title="checkBox"
        expand={{
          name: 'checkBox',
          type: 'checkBox',
          enum: [
            {
              label: '选项A',
              value: 'A',
            },
            {
              label: '选项B',
              value: 'B',
            },
            {
              label: '选项C',
              value: 'C',
            },
          ],
        }}
        dataIndex="d"
      />
      <Table.Column
        title="customDate"
        dataIndex="e"
        expand={{
          name: 'customDate',
          type: 'customComponent',
          icon: 'clock',
          cell: (
            <DatePicker
              name="customDate"
              popupProps={{ v2: true }}
              style={{ width: '200px' }}
            />
          ),
        }}
      />
      <Table.Column
        title="customTree"
        dataIndex="f"
        expand={{
          name: 'customTree',
          type: 'customComponent',
          icon: 'list',
          align: 'br',
          cell: (
            <TreeSelect
              name="customTree"
              dataSource={treeData}
              popupProps={{ v2: true }}
              treeDefaultExpandAll
              multiple
              style={{ width: '200px' }}
            />
          ),
        }}
      />
    </ProTable>
  );
};
```

### Demo8: 筛选表单校验(只支持 Input)

```tsx
import React, { useRef } from 'react';
import { Button, Divider, Field } from '@alifd/next';
import { ProTable } from '@yuanfudao/ada-fusion-pro';
export default () => {
  const tableRef = useRef(null);
  const field = Field.useField();
  const getList = () => {
    return new Promise((resolve, reject) => {
      field.validate(error => {
        // console.log(error);

        if (!error) {
          setTimeout(() => {
            resolve({
              list: Array(10)
                .fill('')
                .map(() => ({
                  name: 'demoName',
                  age: Math.floor(Math.random() * 50 + 10),
                  interest_1: Math.floor(Math.random() * 1000),
                  interest_2: Math.floor(Math.random() * 1000),
                  interest_3: Math.floor(Math.random() * 1000),
                  interest_4: Math.floor(Math.random() * 1000),
                })),
              pageInfo: {
                currentPage: 0,
                pageSize: 100,
                totalItem: 10,
                totalPage: 1,
              },
            });
          }, 2000);
        } else {
          resolve([]);
        }
      });
    });
  };

  const filter = [
    {
      label: '输入框',
      name: 'inputDemo',
      span: 8,
      // type: 'input',
      formItemProps: {
        validator: (_r, v, _cb) => {
          if (v && v.length < 5) {
            _cb('最少输入5个字符');
          } else {
            _cb();
          }
        },
      },
      options: {
        placeholder: '请输入内容',
      },
    },
  ];

  const table = {
    columns: [
      {
        title: '姓名',
        dataIndex: 'name',
      },
      {
        title: '年龄',
        dataIndex: 'age',
        cell: (value: string) => <>{value + '岁'}</>,
      },
      {
        title: '兴趣',
        align: 'center',
        children: [
          {
            title: '兴趣1',
            dataIndex: 'interest_1',
          },
          {
            title: '兴趣2',
            dataIndex: 'interest_2',
          },
          {
            title: '兴趣3',
            dataIndex: 'interest_3',
          },
          {
            title: '兴趣4',
            dataIndex: 'interest_4',
          },
        ],
      },
    ],
  };

  return (
    <ProTable
      field={field}
      filter={filter}
      ref={tableRef}
      searchFn={getList}
      changeUrlSearch={false}
      table={table}
    />
  );
};
```

## API

### ProTable

| 参数                   | 说明                                                                                                                                                      | 类型                                                                                | 必填 | 默认值               |
| :--------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------- | :--- | :------------------- |
| table                  | Fusion 的 Table API `无配置时也需传入{}`                                                                                                                  | [传送门](https://fusion.design/35963/component/table?themeid=19252#Table)           | `是` | --                   |
| pagination             | Fusion 的 Pagination API                                                                                                                                  | [传送门](https://fusion.design/35963/component/pagination?themeid=19252#Pagination) | 否   | ``                   |
| initSize               | 初始化 size [10,20,30,40,50]其中任一                                                                                                                      | `Number`                                                                            | 否   | 20                   |
| hasPagination          | 是否展示分页器                                                                                                                                            | `Boolean`                                                                           | 否   | `true`               |
| paginationParamsName   | 分页参数字段名称 [页码名称 默认`page`, 每页展示数量名称 默认`size`]                                                                                       | `[String, String]`                                                                  | 否   | `['page', 'size']`   |
| versionParamName       | 班课版本查询字段名称，默认为`programmingVersion`                                                                                                          | `String`                                                                            | 否   | 'programmingVersion' |
| searchFn               | 列表搜索方法, 分页参数默认为`page` `size`组合, 为其他分页参数时, 在 http 请求定义出处兼容处理，参数为 params（查询请求参数）, isReset（是否点击重置按钮） | `Promise<ListResult>`                                                               | 否   | --                   |
| filter                 | 表单搜索项配置                                                                                                                                            | `FilterItem[]`                                                                      | 否   | --                   |
| initParams             | 其他默认参数                                                                                                                                              | `Object`                                                                            | 否   | `{}`                 |
| changeUrlSearch        | 是否将搜索条件同步至 url                                                                                                                                  | `Boolean`                                                                           | 否   | `true`               |
| clearParamsOnSearch    | 检索时是否清空 url 中其他查询参数                                                                                                                         | `Boolean`                                                                           | 否   | `true`               |
| selectColumn           | 是否开启自定义列表展示（为 true 时要设置 selectColumnStorageKey，且 columns 最多有一列不设 dataIndex，且 dataIndex 不能重复）                             | `Boolean`                                                                           | 否   | `false`              |
| selectColumnStorageKey | 自定义列表展示在本地的存储标识                                                                                                                            | `String`                                                                            | 否   | --                   |
| selectColumnTitle      | 自定义列表按钮文案                                                                                                                                        | `String \| ReactNode`                                                               | 否   | --                   |
| selectColumnInSession  | 自定义列表配置信息是否存入 sessionStorage（为 false 时存入 localStorage）                                                                                 | `Boolean`                                                                           | 否   | `true`               |
| filtersFoldable        | 筛选项是否可折叠                                                                                                                                          | `Boolean`                                                                           | 否   | `false`              |
| selectFilter           | 针对设置了 defaultHidden 的可隐藏筛选项，是否开启自定义筛选项配置，为 true 时要设置 selectFilterStorageKey                                                | `Boolean`                                                                           | 否   | `false`              |
| selectFilterStorageKey | 自定义筛选项在本地的存储标识                                                                                                                              | `String`                                                                            | 否   | --                   |
| actionShow             | 操作区域内容                                                                                                                                              | `ReactNode`                                                                         | 否   | --                   |
| leftShow               | 表格左上方区域内容                                                                                                                                        | `ReactNode`                                                                         | 否   | --                   |
| rightShow              | 表格右上方区域内容                                                                                                                                        | `ReactNode`                                                                         | 否   | --                   |
| drag                   | 是否为拖拽表格                                                                                                                                            | `Boolean`                                                                           | 否   | `false`              |
| onDragEnd              | 拖拽回调                                                                                                                                                  | `(newDataSource) => void \| any`                                                    | 否   | --                   |
| copy                   | 复制表格功能                                                                                                                                              | `Boolean`                                                                           | 否   | `false`              |
| field                  | 自定义筛选表单数据管理                                                                                                                                    | Fusion `Field`                                                                      | 否   | --                   |
| onDataChange           | 列表数据更新回调                                                                                                                                          | `({ list, total })=> vod\|any`                                                      | 否   | --                   |
| changePageIsScrollTop  | 翻页是否自动滚动到页面顶部                                                                                                                                | `Boolean`                                                                           | 否   | `true`               |
| showBtnIcon            | 显示搜索按钮 icon                                                                                                                                         | `Boolean`                                                                           | 否   | `false`              |

### Table.Column 拓展

| 拓展属性        | 说明                                   | 类型      |
| :-------------- | :------------------------------------- | :-------- |
| expand          | 表头自定义筛选                         | `Object`  |
| selectUnchecked | 自定义列表是否默认隐藏，手动勾选后可见 | `Boolean` |

#### expand 说明

| expand | 说明                                                                                                                                            | 类型                                                    |
| :----- | :---------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------ |
| name   | 表单 key 值                                                                                                                                     | 类型                                                    |
| type   | `input\|inputNumber\|radio\|checkBox\|customComponent`                                                                                          | 类型                                                    |
| enum   | 枚举类型                                                                                                                                        | `EnumType`                                              |
| icon   | 自定义表头筛选图标                                                                                                                              | Fusion `Icon`                                           |
| align  | 自定义弹层对齐方式                                                                                                                              | `String`, 默认为 `'bl'`，弹层左上角对齐筛选按钮的左下角 |
| cell   | customComponent 传入的自定义表头筛选组件，注意：`自定义组件点击会出现子弹层时，务必传入 popupProps={v2: true} ，否则点击子弹层，父弹层也会关闭` | `ReactElement`                                          |

### ProTable Ref 说明

| current 属性       | 说明                         | 类型                    |
| :----------------- | :--------------------------- | :---------------------- |
| refresh            | 跳转至第一页刷新             | `() => void`            |
| currentRefresh     | 当前页刷新                   | `() => void`            |
| showColumns        | 当前展示列信息               | Fusion `Table.Column[]` |
| originColumns      | 原始列信息                   | Fusion `Table.Column[]` |
| dataSource         | table 的 dataSource          | `Array<any>`            |
| total              | searchFn 接口返回的 total    | `Number`                |
| queryMap           | 当前所有请求参数（过滤空值） | `Object`                |
| resetFilter        | 手动重置表格筛选值           | `() => void`            |
| setFolded          | 设置筛选项展开/收起          | `(Boolean) => void`     |
| toggleFilterHidden | 设置某一筛选项常驻/取消常驻  | `(String) => void`      |

### FilterItem (表格搜索项配置)

| 参数          | 说明                                                                                                                                                                                                                                                                          | 类型               | 必填 | 默认值  |
| :------------ | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------- | :--- | :------ |
| label         | 展示 label 文案                                                                                                                                                                                                                                                               | `String`           | 否   | --      |
| name          | 搜索时 form 表单注册的 name 值                                                                                                                                                                                                                                                | `String`           | `是` | --      |
| type          | 分类:<br>`input`: 文本输入框<br>`numberPicker`: 数字输入框<br>`select`: 下拉框<br>`radio`: 单选框<br>`rangePicker`: 日期选择<br>`treeSelect`: 树形选择框<br>`customComponent`: 自定义组件<br>`selectLevel`: 级别单选<br>`selectPart`: 分布单选                                | `String`           | 否   | `input` |
| span          | 共 24 份,所占份数宽度                                                                                                                                                                                                                                                         | `Number \| String` | 否   | `6`     |
| initValue     | 初始默认值                                                                                                                                                                                                                                                                    | `Any`              | 否   | --      |
| options       | 同 Fusion 以下组件 API<br>`Input`组件<br>`NumberPicker`组件<br>`Select`组件 `需配置enum: EnumType[]`<br>`Radio`组件 `需配置enum EnumType[]`<br>`TreeSelect`组件 `需配置enum EnumType[]`<br>`DatePicker -> RangePicker`组件 `配置enum即代表日期选择框带有快捷选项功能`EnumType | `Any`              | 否   | --      |
| cell          | customComponent 传入的自定义筛选框组件                                                                                                                                                                                                                                        | `ReactElement`     | 否   | --      |
| unit          | 时间段筛选项的最小单位，在 `rangePicker2` 中使用                                                                                                                                                                                                                              | `String`           | 否   | `day`   |
| defaultHidden | 筛选项可折叠时默认隐藏                                                                                                                                                                                                                                                        | `Boolean`          | 否   | `false` |
| specialRange  | 特殊时间范围筛选，仅 type 为`rangePicker`时生效，用两个日期选择器实现，不存在时间范围校验                                                                                                                                                                                     | `Boolean`          | 否   | `false` |
| formItemProps | FormItem 的属性                                                                                                                                                                                                                                                               | Any                | 否   | --      |
| autoFormat    | 类型为 input 时，是否需要自动将分隔符转换为英文逗号                                                                                                                                                                                                                           | `Boolean`          | 否   | `false` |

#### ListResult

| 参数     | 说明     | 类型                                                                                 |
| :------- | :------- | :----------------------------------------------------------------------------------- |
| list     | 返回数组 | `{[key: any]: any}[]`                                                                |
| pageInfo | 分页信息 | `{`<br>`currentPage: 0`<br>`pageSize: 20`<br>`totalItem: 0`<br>`totalPage: 0`<br>`}` |

#### EnumType

| 参数    | 说明                               | 类型               | 必填 | 默认值 |
| :------ | :--------------------------------- | :----------------- | :--- | :----- |
| label   | 展示文案                           | `String`           | `是` | --     |
| value   | 数据交互 key 值                    | `String \| Number` | `是` | --     |
| default | 是否默认`(日期选择框额外配置使用)` | `Boolean`          | 否   | --     |

## 场景: OSS 上传

## 示例

### Demo

```tsx
import React from 'react';
import { Button, Icon } from '@alifd/next';
import { ProUpload } from '@yuanfudao/ada-fusion-pro';

export default () => {
  return (
    <>
      <h5>单张图片</h5>
      <ProUpload
        listType="dragCard"
        single={false}
        sizeLimit={1024}
        fileTypes={['.png', '.jpeg', '.jpg', '.gif']}
        mode={'test'}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传图片
        </Button>
      </ProUpload>
      <h5>多选图片限制两张</h5>
      <ProUpload
        listType="dragCard"
        single={false}
        sizeLimit={1024}
        fileTypes={['.png', '.jpeg', '.jpg', '.gif']}
        mode={'test'}
        limit={2}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传图片
        </Button>
      </ProUpload>
      <h5>video</h5>
      <ProUpload listType="video" single={false} mode={'test'}>
        <Button type="primary">
          <Icon type="upload" /> 上传视频
        </Button>
      </ProUpload>

      <h5>audio</h5>
      <ProUpload listType="audio" mode={'test'}>
        <Button type="primary">
          <Icon type="upload" /> 上传音频
        </Button>
      </ProUpload>

      <h5>通用接口上传</h5>
      <ProUpload
        listType="dragCard"
        single={false}
        sizeLimit={1024}
        fileTypes={['.png', '.jpeg', '.jpg', 'gif']}
        mode={'test'}
        uploadApiType={1}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传图片
        </Button>
      </ProUpload>

      <h5>video</h5>
      <ProUpload
        listType="video"
        single
        limit={1}
        mode={'test'}
        videoResolution={{ width: 1920, height: 1080 }}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传视频
        </Button>
      </ProUpload>

      <h5>上传文件夹</h5>
      <ProUpload
        listType="text"
        fileNameRender={file => (
          <span>
            {decodeURIComponent(
              file.name.substring(file.name.lastIndexOf('/') + 1),
            )}
          </span>
        )}
        uploadDir
        name="urls"
        mode={'test'}
        single={false}
        fileTypes={['.png', '.jpg', '.pdf', '.mp4']}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传文件夹
        </Button>
      </ProUpload>
      <h5>上传多种文件类型</h5>
      <ProUpload
        listType="dragCard"
        name="urls"
        mode={'test'}
        single={true}
        fileTypes={['.png', '.jpg', '.pdf', '.mp4']}
        fileNameRender={file => (
          <span>
            {decodeURIComponent(
              file.name.substring(file.name.lastIndexOf('/') + 1),
            )}
          </span>
        )}
      >
        <Button type="primary">
          <Icon type="upload" /> 上传文件
        </Button>
      </ProUpload>
    </>
  );
};
```

## API

### ProUpload

| 参数                                    | 说明                                                                                            | 类型                                                                         | 必填 | 默认值  |
| :-------------------------------------- | :---------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------- | :--- | :------ |
| mode                                    | 所处环境,ice 项目 config 文件配置定义环境变量，注入 config.xxx 即可                             | `dev\|development\|test\|prod\|production`                                   | 否   | --      |
| dragable                                | 是否可拖拽上传                                                                                  | `Boolean`                                                                    | 否   | `false` |
| name                                    | 文件名字段                                                                                      | `String`                                                                     | 否   | --      |
| limitFileNameLength                     | 文件名最大长度                                                                                  | `String`                                                                     | 否   | --      |
| value                                   | 文件列表                                                                                        | `Array`                                                                      | 否   | --      |
| sizeLimit                               | 上传文件大小限制，单位为 MB                                                                     | `Number`                                                                     | 否   | --      |
| limit                                   | 上传文件数量限制                                                                                | `Number`                                                                     | 否   | --      |
| fileTypes                               | 上传文件类型限制                                                                                | `文件扩展名数组，如 ['.png', '.jpeg']，详见 Upload 的 accept`                | 否   | --      |
| listType                                | 上传列表的样式                                                                                  | `上传列表的样式，可选 'text', 'image', 'card', 'video', 'audio', 'dragCard'` | 否   | --      |
| single                                  | 限制传入一个文件，且已传入时显示重新上传按钮                                                    | `Boolean`                                                                    | 否   | false   |
| singleReUpload                          | 自定义重新上传按钮                                                                              | `ReactElement`                                                               | 否   | --      |
| imageWidth, imageHeight                 | 上传图片宽高的尺寸，单位为 px                                                                   | `Number`                                                                     | 否   | --      |
| maxWidth, maxHeight                     | 上传图片宽高的最大尺寸                                                                          | `Number`                                                                     | 否   | --      |
| minWidth, minHeight                     | 上传图片宽高的最小尺寸                                                                          | `Number`                                                                     | 否   | --      |
| ratio                                   | 上传图片的宽高比                                                                                | `{ width: Number, height: Number }`                                          | 否   | --      |
| sameHeight                              | 限制上传图片的高度相同                                                                          | `Boolean`                                                                    | 否   | false   |
| uploadOss                               | 是否上传到 oss                                                                                  | `Boolean`                                                                    | 否   | true    |
| uploadApiType                           | 使用其他上传接口，目前支持枚举值 1 为接口 /ada-basic-tool-admin/api/oss/uploadFileWithDirectory | `Boolean`                                                                    | 否   | 0       |
| showSuccessToast                        | 是否展示上传成功的 message                                                                      | `Boolean`                                                                    | 否   | true    |
| replaceHost                             | 上传地址是否从 aliyuncs 改为 fbcontent                                                          | `Boolean`                                                                    | 否   | true    |
| tinyCompress                            | 上传图片时压缩文件大小                                                                          | `Boolean`                                                                    | 否   | false   |
| disabled                                | 上传按钮置灰                                                                                    | `Boolean`                                                                    | 否   | false   |
| getDuration                             | 音频时长处理函数                                                                                | `Function: (duration) => void`                                               | 否   | --      |
| actionRender                            | 操作区域额外渲染                                                                                | `Function，同 Fusion Upload`                                                 | 否   | --      |
| fileNameRender                          | list 的自定义文件名渲染                                                                         | `Function，同 Fusion Upload`                                                 | 否   | --      |
| beforeUpload, startUpload, finishUpload | 自定义上传动作相关函数                                                                          | `Function`                                                                   | 否   | --      |
| previewMaxSize                          | 预览弹窗的最大高度和最大宽度限制                                                                | `Number`                                                                     | 否   | --      |
| uploadDir                               | 上传文件夹                                                                                      | `Boolean`                                                                    | 否   | --      |

### ProUpload Ref 说明

| current 属性 | 说明                 | 类型      |
| :----------- | :------------------- | :-------- |
| uploading    | 是否有正在上传的文件 | `Boolean` |

## 场景: ldap|user 选择器

## 示例

### Demo1: 常规使用

```tsx
import React from 'react';
import { Form, Field } from '@alifd/next';
import { ProUserSelect } from '@yuanfudao/ada-fusion-pro';

export default () => {
  const field = Field.useField({
    values: { ldaps: ['jiangyangyangbj'] },
  });

  return (
    <Form
      field={field}
      labelCol={{ fixedSpan: 10 }}
      wrapperCol={{ fixedSpan: 20 }}
    >
      <Form.Item label="老师：">
        <ProUserSelect placeholder="请输入姓名/ldap" />
      </Form.Item>
      <Form.Item label="老师（多选）：">
        <ProUserSelect
          name="ldaps"
          single={false}
          placeholder="请输入姓名/ldap"
        />
      </Form.Item>
      <Form.Item label="大编程用户：">
        <ProUserSelect type="student" bizType={0} />
      </Form.Item>
      <Form.Item label="小编程用户：">
        <ProUserSelect type="student" bizType={1} />
      </Form.Item>
    </Form>
  );
};
```

## API

### ProUserSelect

| 参数         | 说明                                                 | 类型             | 必填 | 默认值                                           |
| :----------- | :--------------------------------------------------- | :--------------- | :--- | :----------------------------------------------- |
| type         | 选择器类型，`user\|student`                          | `String`         | 否   | --                                               |
| value        | 选择器值                                             | `Number\|String` | 否   | --                                               |
| defaultValue | 选择器值默认值                                       | `Number\|String` | 否   | --                                               |
| placeholder  | 输入提示                                             | `String`         | 否   | `'昵称/姓名/手机号/ID' \| '姓名/邮箱前缀关键字'` |
| onChange     | 发生改变的时候触发的回调                             | `Function`       | 否   | --                                               |
| bizType      | type 为 `student` 时有效，`0` 为大编程，`1` 为小编程 | `Number`         | 否   | --                                               |
| single       | 是否为单选，`false` 开启多选模式                     | Boolean          | 否   | `true`                                           |
