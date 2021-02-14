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

### Webpack
***

El browser  necesita convertir un codigo de modulos a un codigo que el navegador pueda interpretar.
Permite agregar  archivos js  si no tambien archivos como imagenes.

> Se exporta el objeto de configuracion de js

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
> Webpack server  utiliza el server plugin de webpack
``` javascript

 devServer: {
    historyApiFallback: true,
    noInfo: true,
    overlay: true
  },

```

>  Performance nos
``` javascript

 performance: {
    hints: false
  },
  devtool: '#eval-source-map'

```

### Babel
***

Es un transpilador de codigo, que genera codigo que acepta el browser.

Para configurar babel debemos usar presets, los presets son tipos de funcionalidades que queremos que se compilen

> Se indica a babel que no resuelva  los modulos ya que esa responsabilidad es de webpack
``` javascript
{
  "presets": [
    ["env", { "modules": false }],
    "stage-3"
  ]
}
```

| Module        | Name         | Description  |
| ------------- |:-------------:| -----:|
| babel-core|  babel-core | es el core de babel
| babel-loader | babel-loader| permite que webpack puede transpilar el codigo de vue a codigo js
|babel-preset-env| babel-preset-env| son el conjunto de funcionalidades que entiende babel para transpilar codigo
