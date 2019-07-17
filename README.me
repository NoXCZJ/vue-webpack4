### 一、建立项目
```
mkdir project
cd project
```

##### 1. 初始化项目
```
npm init
npm install webpack webpack-cli -D

mkdir src
cd src
touch main.js

cd ..

mkdir build
cd build
touch webpack.base.conf.js
```

### 二、配置webpack

`webpack.base.conf.js`
```js
const path = require('path');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // 配置入口文件
    main: path.resolve(__dirname, '../src/main.js')
  },
  output: {
    // 配置打包文件输出的目录
    path: path.resolve(__dirname, '../dist'),
    // 生成的js文件名称
    filename: 'js/[name].[hash:8].js',
    // 生成的chunk名称
    chunkFilename: 'js/[name].[hash:8].js',
    // 资源引用的路径
    publicPath: './'
  }
}
```

`package.json` 添加 "serve":

```
"serve": "webpack ./src/main.js --config ./build/webpack.config.js"
```

##### 2.1 配置 ES6/7/8 转 ES5 代码

```shell
npm install babel-loader @babel/core @babel/preset-env
```

修改 `webpack.base.conf.js`:
```js
const path = require('path');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // ...
  },
  output: {
    // ...
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        use: [{
          loader: 'babel-loader'
        }]
      }
    ]
  }
}
```

在根目录新增 `babel.config.js`:
```js
module.exports = {
  presets: [
    "@babel/preset-env"
  ]
}
```

##### 2.1.1 ES6/7/8 API 转 ES5 （可以跳到2.1.2）

> ==babel-loader== 只会将ES6/7/8语法转换为ES5语法，但是对新API并不会转换。

> 我们可通过babel-polyfill 对一些不支持新语法的客户端提供新语法的实现

```shell
npm install @babel/polyfill
```

修改 `webpack.base.conf.js` 配置

在 `entry` 中添加 `@babel-polyfill`

```js
entry: {
    // 配置入口文件
    main: ["@babel/polyfill", path.resolve(__dirname, '../src/main.js')]
}
```

##### 2.1.2 另外一种方案（参考别的github，大多数采用这个）

> 2.1.2 和 2.1.1 只需要配置一个就行


```shell
npm install core-js@2 @babel/runtime-corejs2 -S
# 或者
npm install core-js@3 @babel/runtime-corejs3 -S
```

`babel.config.js`:
```js
module.exports = {
  presets: [
    [
      "@babel/preset-env",
      {
        useBuiltIns: "usage",
        "corejs": "3.0.0",
      }
    ]
  ]
};

```

##### 2.3 配置 `scss` 转 `css`
```shell
npm install sass-loader dart-sass css-loader style-loader -D
```

> sass-loader, dart-sass主要是将 scss/sass 语法转为css

> css-loader主要是解析 css 文件

> style-loader 主要是将 css 解析到 html页面 的 style 上

修改 `webpack.base.conf.js` ：
```js
const path = require('path');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // ...
  },
  output: {
    // ...
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        use: [{
          loader: 'babel-loader'
        }]
      },
      {
        test: /\.(scss|sass)$/,
        use: [
          {
            loader: 'style-loader'
          },
          {
            loader: 'css-loader'
          },
          {
            loader: 'sass-loader',
            options: {
              implementation: require('dart-sass')
            }
          }
        ]
      }
    ]
  }
}
```

##### 2.3 配置 `postcss` 实现自动添加css3前缀

```shell
npm install postcss-loader autoprefixer -D
```

`webpack.base.conf.js`:
```js
const path = require('path');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // ...
  },
  output: {
    // ...
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        use: [{
          loader: 'babel-loader'
        }]
      },
      {
        test: /\.(scss|sass)$/,
        use: [
          {
            loader: 'style-loader'
          },
          {
            loader: 'css-loader',
            options: {
              importLoaders: 2
            }
          },
          {
            loader: 'sass-loader',
            options: {
              implementation: require('dart-sass')
            }
          },
          {
            loader: 'postcss-loader'
          }
        ]
      }
    ]
  }
}
```

在根目录下新建 `postcss.config.js`
```js
module.exports = {
  plugins: {
    autoprefixer: {}
  }
}
```
##### 2.3 使用 `html-webpack-plugin` 来创建html页面
```shell
npm install html-webpack-plugin -D
```

新建 `public/index.html`

`webpack.base.conf.js` : 
```js
plugins: [
    new HtmlWebpackPlugin({
      template: path.resolve(__dirname, '../public/index.html')
    })
  ]
```

##### 2.4 配置 devServer 热更新功能
```shell
npm install webpack-dev-server -D
```

通过配置 devServer 和 HotModuleReplacementPlugin 插件来实现热更新

`webpack.base.conf.js` :
```js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const webpack = require('webpack');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // ...
  },
  output: {
    // ...
  },
  module: {
    // ...
  },
  devServer: {
    hot: true,
    port: 3000,
    contentBase: './dist'
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: path.resolve(__dirname, '../public/index.html')
    }),
    new webpack.NamedModulesPlugin(),
    new webpack.HotModuleReplacementPlugin()
  ]
}
```

##### 2.5 配置webpack打包 图片、媒体、字体等文件
```shell
npm install file-loader url-loader -D
```
> file-loader 解析文件url，并将文件复制到输出的目录中

> url-loader 功能与 file-loader 类似，如果文件小于限制的大小。则会返回 base64 编码，否则使用 file-loader 将文件复制到输出的目录中

```js
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const webpack = require('webpack');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // ...
  },
  output: {
    // ...
  },
  module: {
    rules: [
      //...
      {
        test: /\.(jpe?g|png|gif)$/i,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: 'file-loader',
              options: {
                name: 'img/[name].[hash:8].[ext]'
              }
            }
          }
        ]
      },
      {
        test: /\.(mp4|webm|ogg|mp3|wav|flac|aac)(\?.*)?$/,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: {
                loader: 'file-loader',
                options: {
                  name: 'media/[name].[hash:8].[ext]'
                }
              }
            }
          }
        ]
      },
      {
        test: /\.(woff2|eot|ttf|otf)(\?.*)?$/i,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: {
                loader: 'file-loader',
                options: {
                  name: 'fonts/[name].[hash:8].[ext]'
                }
              }
            }
          }
        ]
      }
    ]
  },
  plugins: [
    // ...
  ]
}
```

### 三、让 `webpack` 识别 `.vue` 文件
```shell
npm install vue-loader vue-template-compiler cache-loader thread-loader -D
npm install vue -S
```
> vue-loader 用于解析.vue文件

> vue-template-compiler 用于编译模板

> cache-loader 用于缓存loader编译的结果
thread-loader 使用 worker 池来运行loader，每个 worker 都是一个 node.js 进程。

`webpack.base.conf.js`:
```js
const path = require('path');
const webpack = require('webpack');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const VueLoaderPlugin = require('vue-loader/lib/plugin');

module.exports = {
  // 指定打包模式
  mode: 'development',
  entry: {
    // 配置入口文件
    main: path.resolve(__dirname, '../src/main.js')
  },
  output: {
    // 配置打包文件输出的目录
    path: path.resolve(__dirname, '../dist'),
    // 生成的js文件名称
    filename: 'js/[name].[hash:8].js',
    // 生成的chunk名称
    chunkFilename: 'js/[name].[hash:8].js',
    // 资源引用的路径
    publicPath: './'
  },
  devServer: {
    hot: true,
    port: 3000,
    contentBase: './dist'
  },
  resolve: {
    alias: {
      vue$: 'vue/dist/vue.runtime.esm.js'
    },
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        use: [
          {
            loader: 'cache-loader'
          },
          {
            loader: 'thread-loader'
          },
          {
            loader: 'babel-loader'
          }
        ]
      },
      {
        test: /\.vue$/,
        exclude: /(node_modules|bower_components)/,
        use: [
          {
            loader: 'cache-loader'
          },
          {
            loader: 'thread-loader'
          },
          {
            loader: 'vue-loader',
            options: {
              compilerOptions: {
                preserveWhitespace: false
              }
            }
          }
        ]
      },
      // ...
    ]
  },
  plugins: [
    // ...
    new VueLoaderPlugin()
  ]
}
```

- 测试下
- 在 src 新建一个 `App.vue`
```html
// src/App.vue
<template>
  <div class="App">
    Hello World
  </div>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
.App {
  color: skyblue;
}
</style>
```
- 修改 `main.js`
```js
import Vue from 'vue'
import App from './App.vue'

new Vue({
  render: h => h(App)
}).$mount('#app')

```

- 运行 `npm run serve`


### 四、定义环境变量

通过 webpack提供的DefinePlugin插件，可以很方便的定义环境变量

```js
plugins: [
    new webpack.DefinePlugin({
      'process.env': {
        VUE_APP_BASE_URL: JSON.stringify('http://localhost:3000')
      }
    }),
]
```

新建两个文件

- webpack.dev.js 开发环境使用

- webpack.prod.js 生产环境使用

- webpack.config.js 公用配置

开发环境与生产环境的不同

5.1 开发环境

    1. 不需要压缩代码
    2. 需要热更新
    3. css不需要提取到css文件
    4. sourceMap
    5. ...

5.2 生产环境

    1. 压缩代码
    2. 不需要热更新
    3. 提取css，压缩css文件
    4. sourceMap
    5. 构建前清除上一次构建的内容
    6. ...
    
```shell
npm install @intervolga/optimize-cssnano-plugin mini-css-extract-plugin clean-webpack-plugin webpack-merge copy-webpack-plugin -D
```

    1. @intervolga/optimize-cssnano-plugin 用于压缩css代码
    2. mini-css-extract-plugin 用于提取css到文件中
    3. clean-webpack-plugin 用于删除上次构建的文件
    4. webpack-merge 合并 webpack配置
    5. copy-webpack-plugin 用户拷贝静态资源
    
5.3 开发环境配置

`build/webpack.dev.js`:
```js
// build/webpack.dev.js
const merge = require('webpack-merge')
const webpackConfig = require('./webpack.config')
const webpack = require('webpack')
module.exports = merge(webpackConfig, {
  mode: 'development',
  devtool: 'cheap-module-eval-source-map',
  module: {
    rules: [
      {
        test: /\.(scss|sass)$/,
        use: [
          {
            loader: 'style-loader'
          },
          {
            loader: 'css-loader',
            options: {
              importLoaders: 2
            }
          },
          {
            loader: 'sass-loader',
            options: {
              implementation: require('dart-sass')
            }
          },
          {
            loader: 'postcss-loader'
          }
        ]
      },
    ]
  },
  plugins: [
    new webpack.DefinePlugin({
      'process.env': {
        NODE_ENV: JSON.stringify('development')
      }
    }),
  ]
})

```

`webpack.base.conf.js`:
```js
const path = require('path');
const webpack = require('webpack');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const VueLoaderPlugin = require('vue-loader/lib/plugin');

module.exports = {
  entry: {
    // 配置入口文件
    main: path.resolve(__dirname, '../src/main.js')
  },
  output: {
    // 配置打包文件输出的目录
    path: path.resolve(__dirname, '../dist'),
    // 生成的js文件名称
    filename: 'js/[name].[hash:8].js',
    // 生成的chunk名称
    chunkFilename: 'js/[name].[hash:8].js',
    // 资源引用的路径
    publicPath: './'
  },
  devServer: {
    hot: true,
    port: 3000,
    contentBase: './dist'
  },
  resolve: {
    alias: {
      vue$: 'vue/dist/vue.runtime.esm.js'
    },
    extensions: [
      '.js',
      '.vue'
    ]
  },
  module: {
    rules: [
      {
        test: /\.jsx?$/,
        exclude: /(node_modules|bower_components)/,
        use: [
          {
            loader: 'cache-loader'
          },
          {
            loader: 'thread-loader'
          },
          {
            loader: 'babel-loader'
          }
        ]
      },
      {
        test: /\.vue$/,
        exclude: /(node_modules|bower_components)/,
        use: [
          {
            loader: 'cache-loader'
          },
          {
            loader: 'thread-loader'
          },
          {
            loader: 'vue-loader',
            options: {
              compilerOptions: {
                preserveWhitespace: false
              }
            }
          }
        ]
      },
      {
        test: /\.(jpe?g|png|gif)$/i,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: 'file-loader',
              options: {
                name: 'img/[name].[hash:8].[ext]'
              }
            }
          }
        ]
      },
      {
        test: /\.(mp4|webm|ogg|mp3|wav|flac|aac)(\?.*)?$/,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: {
                loader: 'file-loader',
                options: {
                  name: 'media/[name].[hash:8].[ext]'
                }
              }
            }
          }
        ]
      },
      {
        test: /\.(woff2|eot|ttf|otf)(\?.*)?$/i,
        use: [
          {
            loader: 'url-loader',
            options: {
              limit: 4096,
              fallback: {
                loader: 'file-loader',
                options: {
                  name: 'fonts/[name].[hash:8].[ext]'
                }
              }
            }
          }
        ]
      }
    ]
  },
  plugins: [
    new VueLoaderPlugin(),
    new HtmlWebpackPlugin({
      template: path.resolve(__dirname, '../public/index.html')
    }),
    new webpack.NamedModulesPlugin(),
    new webpack.HotModuleReplacementPlugin(),
  ]
}
```

5.4 生产环境配置

```js
const path = require('path')
const merge = require('webpack-merge')
const webpack = require('webpack')
const webpackConfig = require('./webpack.config')
const MiniCssExtractPlugin = require('mini-css-extract-plugin')
const OptimizeCssnanoPlugin = require('@intervolga/optimize-cssnano-plugin');
const { CleanWebpackPlugin } = require('clean-webpack-plugin')
const CopyWebpackPlugin = require('copy-webpack-plugin')
module.exports = merge(webpackConfig, {
  mode: 'production',
  devtool: '#source-map',
  optimization: {
    splitChunks: {
      cacheGroups: {
        vendors: {
          name: 'chunk-vendors',
          test: /[\\\/]node_modules[\\\/]/,
          priority: -10,
          chunks: 'initial'
        },
        common: {
          name: 'chunk-common',
          minChunks: 2,
          priority: -20,
          chunks: 'initial',
          reuseExistingChunk: true
        }
      }
    }
  },
  module: {
    rules: [
      {
        test: /\.(scss|sass)$/,
        use: [
          {
            loader: MiniCssExtractPlugin.loader
          },
          {
            loader: 'css-loader',
            options: {
              importLoaders: 2
            }
          },
          {
            loader: 'sass-loader',
            options: {
              implementation: require('dart-sass')
            }
          },
          {
            loader: 'postcss-loader'
          }
        ]
      },
    ]
  },
  plugins: [
    new webpack.DefinePlugin({
      'process.env': {
        NODE_ENV: 'production'
      }
    }),
    new MiniCssExtractPlugin({
      filename: 'css/[name].[contenthash:8].css',
      chunkFilename: 'css/[name].[contenthash:8].css'
    }),
    new OptimizeCssnanoPlugin({
      sourceMap: true,
      cssnanoOptions: {
        preset: [
          'default',
          {
            mergeLonghand: false,
            cssDeclarationSorter: false
          }
        ]
      }
    }),
    new CopyWebpackPlugin([
      {
        from: path.resolve(__dirname, '../public'),
        to: path.resolve(__dirname, '../dist')
      }
    ]),
    new CleanWebpackPlugin()
  ]
})
```

5.5 修改 `package.json`
```json
"scripts": {
    "serve": "webpack-dev-server --config ./build/webpack.dev.js",
    "build": "webpack --config ./build/webpack.prod.js"
},
```

### 六、打包分析
> 有的时候，我们需要看一下webpack打包完成后，到底打包了什么东西，
这时候就需要用到这个模块分析工具了 `webpack-bundle-analyzer`

```shell
npm install --save-dev webpack-bundle-analyzer
```

`webpack-prod.js`，在 plugins属性中新增一个插件

> 在开发环境中，我们是没必要进行模块打包分析的，所以我们将插件配置在了生产环境的配置项中

```js
const BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin;

module.exports = merge(webpackConfig, {
  mode: 'production',
  devtool: '#source-map',
  optimization: {
    // ...
  },
  module: {
    // ...
  },
  plugins: [
    // ...
    new BundleAnalyzerPlugin({
      analyzerMode: 'static'
    })
  ]
})
```

### 七、集成 `VueRouter`, `Vuex`

```shell
npm install vue-router vuex --save
```

##### 7.1  集成 `Vue-Router`

新增视图组件 在 src 目录下新增两个视图组件 `src/views/Home.vue` 和 `src/views/About.vue`

```html
// src/views/Home.vue
<template>
  <div class="Home">
    <h2>Home</h2>
  </div>
</template>

<script>
export default {
  name: 'Home',

  data() {
    return {};
  }
};
</script>

<style lang="scss" scoped>
</style>
```
> About.vue 内容跟 Home.vue 差不多，将里面的 Home 换成 About 就OK了

在 `src` 目录下新增一个 `router/index.js` 文件

```js
// src/router/index.js
import Vue from 'vue'
import VueRouter from "vue-router";
import Home from '../views/Home';
import About from '../views/About';
Vue.use(VueRouter)
export default new VueRouter({
  mode: 'hash',
  routes: [
    {
      path: '/Home',
      component: Home
    },
    {
      path: '/About',
      component: About
    },
    {
      path: '*',
      redirect: '/Home'
    }
  ]
})
```

修改 `main.js`

```js
// main.js
import Vue from 'vue'
import App from './App.vue'
import router from './router'

new Vue({
  router,
  render: h => h(App)
}).$mount('#app')
```

修改 `App.vue` 组件
```html
<template>
  <div class="App">
    <div>
      // router-link 组件 用来导航到哪个路由
      <router-link to="/Home">go Home</router-link>
      <router-link to="/About">go About</router-link>
    </div>
    <div>
      // 用于展示匹配到的路由视图组件
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {};
  },
  computed: {},
  methods: {}
};
</script>

<style lang="scss" scoped>
.App {
  color: skyblue;
}
</style>
```

##### 7.2  配置路由懒加载

在没配置路由懒加载的情况下，我们的路由组件在打包的时候，都会打包到同一个js文件去，当我们的视图组件越来越多的时候，就会导致这个 js 文件越来越大。然后就会导致请求这个文件的时间变长，最终影响用户体验

```shell
npm install @babel/plugin-syntax-dynamic-import --save-dev
```

`babel.config.js`
```js
module.exports = {
  presets: [
    [
      "@babel/preset-env",
      {
        useBuiltIns: "usage",
        corejs: "3.0.0"
      }
    ]
  ],
  plugins: ["@babel/plugin-syntax-dynamic-import"]
};
```

`router/index.js`
```js
// src/router/index.js
import Vue from 'vue'
import VueRouter from "vue-router";
// import Home from '../views/Home';
// import About from '../views/About';
Vue.use(VueRouter)
export default new VueRouter({
  mode: 'hash',
  routes: [
    {
      path: '/Home',
      component: () => import(/* webpackChunkName: "Home" */ '../views/Home.vue'),
      // component: Home
    },
    {
      path: '/About',
      component: () => import(/* webpackChunkName: "About" */ '../views/About.vue'),
      // component: About
    },
    {
      path: '*',
      redirect: '/Home'
    }
  ]
})
```
运行命令 npm run build 查看是否生成了 Home...js 文件 和 About...js 文件

##### 7.3 集成Vuex

在 `src` 目录下新建一个 `store/index.js` 文件
```js
// store/index.js
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
const state = {
  counter: 0
}
const actions = {
  add: ({commit}) => {
    return commit('add')
  }
}
const mutations = {
  add: (state) => {
    state.counter++
  }
}
const getters = {
  getCounter (state) {
    return state.counter
  }
}
export default new Vuex.Store({
  state,
  actions,
  mutations,
  getters
})
```

修改 `main.js` 文件 导入 `vuex`
```js
// main.js
import Vue from 'vue'
import App from './App.vue'
import router from './router'
import store from './store'  // ++
new Vue({
  router,
  store,    // ++
  render: h => h(App)
}).$mount('#app')
```

修改 `App.vue` ，查看 `vuex` 配置效果

```html
<template>
  <div class="App">
    <div>
      // router-link 组件 用来导航到哪个路由
      <router-link to="/Home">go Home</router-link>
      <router-link to="/About">go About</router-link>
    </div>
    <div>
      <p>{{getCounter}}</p>
      <button @click="add">add</button>
    </div>
    <div>
      // 用于展示匹配到的路由视图组件
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
export default {
  name: 'App',
  data() {
    return {};
  },
  computed: {
    ...mapGetters(['getCounter'])
  },
  methods: {
    ...mapActions(['add'])
  }
};
</script>

<style lang="scss" scoped>
.App {
  text-align: center;
  color: skyblue;
  font-size: 28px;
}
</style>
```
