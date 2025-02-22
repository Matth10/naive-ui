# 尺寸

太小太大好像都不怎么好看。

```html
<n-space vertical>
  <n-transfer
    ref="transfer"
    v-model:value="value"
    :options="options"
    size="small"
  />
  <n-transfer
    ref="transfer"
    v-model:value="value"
    :options="options"
    size="large"
  />
</n-space>
```

```js
import { defineComponent, ref } from 'vue'

function createOptions () {
  return Array.apply(null, { length: 100 }).map((v, i) => ({
    label: 'Option' + i,
    value: i,
    disabled: i % 5 === 0
  }))
}

function createValues () {
  return Array.apply(null, { length: 50 }).map((v, i) => i)
}

export default defineComponent({
  setup () {
    return {
      options: createOptions(),
      value: ref(createValues())
    }
  }
})
```
