# Pinia Snippet (Visual Studio Code)

用于快捷编写 [Pinia](https://pinia.vuejs.org/)。

Quickly write Pinia code.

另外按需安装:

Also need to install :

- [Vue Basic Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue-basic-snippets)，包含 Vue 2 和 3 中共用的 `v-*` 系列指令、`import` 组件、指令、服务之类的代码。
    Contains code for the `v-*` family of directives, `import` components, directives, and services common to Vue 2 and 3.
- [Vue 2 Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue2-snippets)，参考 Vue 2 官方文档示例及测试用例源码。
    Uses official Vue 2 examples and test cases.
- [Vue 3 Snippets](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-vue3-snippets)，参考 Vue 3 官方文档示例及测试用例源码。
    Uses official Vue 3 examples and test cases.
- [JavaScript Code Snippet](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-javascript-snippet)，参考 MDN 文档。
    Using MDN documentation.
- [JavaScript Comment Snippet](https://marketplace.visualstudio.com/items?itemName=NicholasHsiang.vscode-javascript-comment)，参考 JSDOC、ESDOC 文档，用于便捷编写 JavaScript 注释。
    Reference JSDOC, ESDOC documentation for easy writing of JavaScript comments.

因为 Vue 不同版本 API 的差异，将 2 和 3 的 Code Snippets 各自分开了。在项目中根据实际情况，在扩展中可以选择 `Disable (Workspace)`；如果觉得这样操作麻烦，可以在 “[VS Code](https://code.visualstudio.com/#alt-downloads)” 中安装 2 版本扩展，在 “[VS Code - Insiders](https://code.visualstudio.com/insiders/)” 中安装 3 版本扩展。

Because of the difference in APIs between different versions of Vue, the Code Snippets for 2 and 3 are separated from each other. You can choose `Disable (Workspace)` in the extensions in your project; if you find it troublesome, you can install version 2 extensions in [VS Code](https://code.visualstudio.com/#alt-downloads) and version 3 extensions in ["VS Code - Insiders"](https://code.visualstudio.com/insiders/).

---

## Snippets

| prefix                     | body                                                                                                                                                                                                                                               | description                                                                   |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| `pinia`, `cp`              | `import { createPinia } from 'pinia';`<br> `const pinia = createPinia();`<br> `app.use(pinia);`                                                                                                                                                    | **C**reate a **pinia** instance                                               |
| `pinia4vue2`, `cp4vue2`    | `import { createPinia, PiniaVuePlugin } from 'pinia';`<br> `Vue.use(PiniaVuePlugin);`<br> `const pinia = createPinia();`                                                                                                                           | **C**reate a **pinia** instance for Vue 2                                     |
| `defineStore`, `ds`        | `import { defineStore } from 'pinia';`<br> `export const useFileNameStore = defineStore('file-name', () => {`<br> `  return {`<br> `    `<br> `  }`<br> `});`                                                                                      | **D**efining **S**tores - Composing                                           |
| `defineStore`, `dso`       | `import { defineStore } from 'pinia';`<br> `export const useFileNameStore = defineStore('file-name', {`<br> `  state: () => ({`<br> `    `<br> `  }),`<br> `  getters: {`<br> `    `<br> `  },`<br> `  actions: {`<br> `    `<br> `  },`<br> `});` | **D**efining **S**tores - **O**ption                                          |
| `ims`                      | `import { useFeatureStore } from '@/stores/feature';`<br> `const featureStore = useFeatureStore();`S                                                                                                                                               | **Im**port **S**tore                                                          |
| `imstr`                    | `import { storeToRefs } from 'pinia';`<br> `const { properties } = storeToRefs(store);`                                                                                                                                                            | **Im**port **s**tore**T**o**R**efs()                                          |
| `imms`                     | `import { mapState } from 'pinia';`<br> `...mapState(useFeatureStore, ['state/getter']),`                                                                                                                                                          | **Im**port **m**ap**S**tate                                                   |
| `imma`                     | `import { mapActions } from 'pinia';`<br> `...mapActions(useFeatureStore, ['actions']),`                                                                                                                                                           | **Im**port **m**ap**A**ctions                                                 |
| `immws`                    | `import { mapWritableState } from 'pinia';`<br>`...mapWritableState(useFeatureStore, ['state/getter']),`                                                                                                                                           | **Im**port **m**ap**W**ritable**S**tate                                       |
| `ms`                       | `...mapState(useFeatureStore, ['state/getter']),`                                                                                                                                                                                                  | Usage with the Options API - Without setup() - **m**ap**S**tate()             |
| `ma`                       | `...mapActions(useFeatureStore, ['actions']),`                                                                                                                                                                                                     | Usage with the Options API - Without setup() - **m**ap**A**ctions()           |
| `mws`                      | `...mapWritableState(useFeatureStore, ['state/getter']),`                                                                                                                                                                                          | Usage with the Options API - Without setup() - **m**ap**W**ritable**S**tate() |
| `store.$patch`, `sp`       | `featureStore.$patch((state) => {`<br> `  `<br> `});`                                                                                                                                                                                              | Mutating the state: **s**tore.$**p**atch                                      |
| `store.$subscribe`, `ss`   | `featureStore.$subscribe((mutation, state) => {`<br> `  `<br> `});`                                                                                                                                                                                | Subscribing to state: **s**tore.$**s**ubscribe                                |
| `store.$onAction`, `sa`    | `const unsubscribe = featureStore.$onAction(`<br> `  ({ name, store, args, after, onError }) => {`<br> `    `<br> `    after((result) => { });`<br> `    onError((error) => { });`<br> `  }`<br> `);`                                              | Subscribing to actions: **s**tore.$**o**nAction                               |
| `store2composition `, `us` | `const featureStore = useFeatureStore();`                                                                                                                                                                                                          | Store @ Composition API, **u**seFeature**S**tore                              |
| `store2option`, `uso`      | `setup() {`<br> `  const featureStore = useFeatureStore()`<br> `  return { featureStore }`<br> `},`                                                                                                                                                | Store @ Options API, **u**seFeature**S**tore                                  |

## License 📃

MIT License

**Donate**

![xianghongai@gmail.com](https://raw.githubusercontent.com/caringrun/assets/master/donate.png)
