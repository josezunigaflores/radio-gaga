# vuefi

> project of music

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

## Documentacion

Webpack
***

El browser  necesita convertir un codigo de modulos a un codigo que el navegador pueda interpretar.
Permite agregar  archivos js  si no tambien archivos como imagenes.

> se exporta el objeto de configuracion de js

``` javascript

module.exports = {

```

> Se definie un entrypoint que webpack necesita para mapear  un arbol de archivos

``` javascript

 entry: './src/main.js',

```

> Salida de archivo al generar el bundle  webpack (es el archivo final)
``` javascript

 output: {
    path: path.resolve(__dirname, './dist'),
    publicPath: '/dist/', // carpeta donde se genera el bundle final
    filename: 'build.js' // nombre del archivo final
  },

```

> Se utiliza para comunicar al compilador node js que archivos debe compilar
``` javascript

 resolve: {
    alias: {
      'vue$': 'vue/dist/vue.esm.js'
    },
    extensions: ['*', '.js', '.vue', '.json']
  },

```
> Webpack server  se utiliza el server de webpack
``` javascript

 devServer: {
    historyApiFallback: true,
    noInfo: true,
    overlay: true
  },

```
