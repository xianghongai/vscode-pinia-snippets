# Pinia Snippet (Visual Studio Code)

用于快捷编写 [Pinia](https://pinia.vuejs.org/)。

另外按需安装:

- [Vue Basic Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue-basic-snippets)，包含 Vue 2 和 3 中共用的 `v-*` 系列指令、`import` 组件、指令、服务之类的代码。
- [Vue 2 Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue2-snippets)，参考 Vue 2 官方文档示例及测试用例源码。
- [Vue 3 Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue3-snippets)，参考 Vue 3 官方文档示例及测试用例源码。
- [JavaScript Code Snippet - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-javascript-snippet)，用于便捷编写 JavaScript，参考 MDN 文档。
- [JavaScript Comment Snippet - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-javascript-comment)，用于便捷编写 JavaScript 注释，参考 JSDOC、ESDOC 文档。

将 Vue 2 和 3 的 Code Snippets 各自分开，在项目中根据实际情况，在扩展中选择 `Disable (Workspace)`，如果觉得这样比较繁琐，可以在 “VS Code” 中安装 2 版本支持的扩展，在 “VS Code - Insiders” 中安装 3 版本支持的扩展。

---

## Snippets

| prefix                     | body                                                                                                                                                                                                                                            | description                                                                   |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| `pinia`                    | `import { createPinia } from 'pinia';`<br> `const pinia = createPinia();`<br> `app.use(pinia);`                                                                                                                                                 | Create a **pinia** instance                                                   |
| `pinia4vue2`               | `import { createPinia, PiniaVuePlugin } from 'pinia';`<br> `Vue.use(PiniaVuePlugin);`<br> `const pinia = createPinia();`                                                                                                                        | Create a **pinia** instance for Vue 2                                         |
| `defineStore`, `ds`        | `import { defineStore } from 'pinia';`<br> `export const useFeatureStore = defineStore('feature', () => {`<br> `  return {`<br> `    `<br> `  }`<br> `});`                                                                                      | **D**efining Composing **S**tores                                             |
| `defineStore`, `dos`       | `import { defineStore } from 'pinia';`<br> `export const useFeatureStore = defineStore('feature', {`<br> `  state: () => ({`<br> `    `<br> `  }),`<br> `  getters: {`<br> `    `<br> `  },`<br> `  actions: {`<br> `    `<br> `  },`<br> `});` | **D**efining **O**ption **S**tores                                            |
| `ims`                      | `import { useFeatureStore } from '@/stores/feature';`<br> `const featureStore = useFeatureStore();`S                                                                                                                                            | **Im**port **S**tore                                                          |
| `imstr`                    | `import { storeToRefs } from 'pinia';`<br> `const { properties } = storeToRefs(store);`                                                                                                                                                         | **Im**port **s**tore**T**o**R**efs()                                          |
| `imms`                     | `import { mapState } from 'pinia';`<br> `...mapState(useFeatureStore, ['state/getter']),`                                                                                                                                                       | **Im**port **m**ap**S**tate                                                   |
| `imma`                     | `import { mapActions } from 'pinia';`<br> `...mapActions(useFeatureStore, ['actions']),`                                                                                                                                                        | **Im**port **m**ap**A**ctions                                                 |
| `immws`                    | `import { mapWritableState } from 'pinia';`<br>`...mapWritableState(useFeatureStore, ['state/getter']),`                                                                                                                                        | **Im**port **m**ap**W**ritable**S**tate                                       |
| `ms`                       | `...mapState(useFeatureStore, ['state/getter']),`                                                                                                                                                                                               | Usage with the Options API - Without setup() - **m**ap**S**tate()             |
| `ma`                       | `...mapActions(useFeatureStore, ['actions']),`                                                                                                                                                                                                  | Usage with the Options API - Without setup() - **m**ap**A**ctions()           |
| `mws`                      | `...mapWritableState(useFeatureStore, ['state/getter']),`                                                                                                                                                                                       | Usage with the Options API - Without setup() - **m**ap**W**ritable**S**tate() |
| `store.$patch`, `sp`       | `featureStore.$patch((state) => {`<br> `  `<br> `});`                                                                                                                                                                                           | Mutating the state: **s**tore.$**p**atch                                      |
| `store.$subscribe`, `ss`   | `featureStore.$subscribe((mutation, state) => {`<br> `  `<br> `});`                                                                                                                                                                             | Subscribing to state: **s**tore.$**s**ubscribe                                |
| `store.$onAction`, `sa`    | `const unsubscribe = featureStore.$onAction(`<br> `  ({ name, store, args, after, onError }) => {`<br> `    `<br> `    after((result) => { });`<br> `    onError((error) => { });`<br> `  }`<br> `);`                                           | Subscribing to actions: **s**tore.$**o**nAction                               |
| `store2composition `, `us` | `const featureStore = useFeatureStore();`                                                                                                                                                                                                       | Store @ Composition API, **u**seFeature**S**tore                              |
| `store2option`, `uso`      | `setup() {`<br> `  const featureStore = useFeatureStore()`<br> `  return { featureStore }`<br> `},`                                                                                                                                             | Store @ Options API, **u**seFeature**S**tore                                  |

## License 📃

MIT License

**Donate**

![xianghongai@gmail.com](https://raw.githubusercontent.com/caringrun/assets/master/donate.png)
