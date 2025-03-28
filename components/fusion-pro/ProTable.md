# ProTable 组件文档

ProTable 是一个高级表格组件，集成了搜索、筛选、分页等常用的表格功能。

## API

### 基础配置

| 参数 | 说明 | 类型 | 默认值 | 必填 |
| --- | --- | --- | --- | --- |
| table | 表格配置 | TableProps | - | 是 |
| searchFn | 获取数据的方法 | (params) => Promise<{ list: any[], total: number }> | - | 是 |

### 分页配置

| 参数 | 说明 | 类型 | 默认值 | 必填 |
| --- | --- | --- | --- | --- |
| initSize | 初始分页大小 | number | 10 | 否 |
| hasPagination | 是否显示分页 | boolean | true | 否 |
| paginationParamsName | 分页参数名称 | { current: string, size: string } | { current: 'current', size: 'size' } | 否 |

### 筛选配置

| 参数 | 说明 | 类型 | 默认值 | 必填 |
| --- | --- | --- | --- | --- |
| filter | 筛选项配置 | FilterItem[] | - | 否 |
| initParams | 初始筛选参数 | object | {} | 否 |
| urlSync | 是否同步URL参数 | boolean | false | 否 |

### 展示配置

| 参数 | 说明 | 类型 | 默认值 | 必填 |
| --- | --- | --- | --- | --- |
| customList | 自定义列表展示 | (data: any[]) => ReactNode | - | 否 |
| filterCollapsible | 筛选区域是否可折叠 | boolean | false | 否 |
| headerExtra | 表格头部额外内容 | ReactNode | - | 否 |
| filterExtra | 筛选区域额外内容 | ReactNode | - | 否 |

### FilterItem 配置

```typescript
interface FilterItem {
  label: string;                 // 筛选项标签
  name: string;                  // 筛选项字段名
  type: 'input' | 'select' | 'datePicker' | 'custom';  // 筛选项类型
  required?: boolean;            // 是否必填
  placeholder?: string;         // 占位文本
  options?: Array<{             // 选择项（type=select时有效）
    label: string;
    value: any;
  }>;
  rules?: Rule[];               // 校验规则
  component?: ReactNode;        // 自定义组件（type=custom时有效）
}
```

## 使用示例

```tsx
import { ProTable } from '@alifd/fusion-pro';

function MyTable() {
  return (
    <ProTable
      table={{
        columns: [
          { title: '姓名', dataIndex: 'name' },
          { title: '年龄', dataIndex: 'age' }
        ]
      }}
      searchFn={async (params) => {
        // 调用接口获取数据
        const { list, total } = await fetchData(params);
        return { list, total };
      }}
      filter={[
        {
          label: '姓名',
          name: 'name',
          type: 'input'
        },
        {
          label: '状态',
          name: 'status',
          type: 'select',
          options: [
            { label: '启用', value: 1 },
            { label: '禁用', value: 0 }
          ]
        }
      ]}
      initParams={{ status: 1 }}
      urlSync
    />
  );
}
```

## 注意事项

1. `searchFn` 必须返回一个包含 `list` 和 `total` 的对象
2. 使用 `urlSync` 时，筛选参数会同步到 URL，刷新页面会保留筛选条件
3. 自定义筛选项组件需要通过 `component` 属性传入