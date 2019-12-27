## webpack的一些插件
  1. html-webpack-plugin
    > npm install html-webpack-plugin --save-dev
    - 用于打包index.html文件
    - 在webpack.config.js里设置
    
       		 const HtmlWebpackPlugin=require('html-webpack-plugin') 
			 module.exports={
				plugins:[new HtmlWebpackPlugin({template: 'index.html'})],  //可以配置多个插件，配置template属性可以让原index文件的属性一起打包
					}
  2.uglifyjs-webpack-plugin
    > npm install uglifyjs-webpack-plugin --save-dev
    - 用于压缩打包后的js文件    
    
       		 const uglifyJsPlugin=require('uglifyjs-webpack-plugin') 
			 module.exports={
				plugins:[new HtmlWebpackPlugin({template: 'index.html'}),//配置template属性可以让原index文件的属性一起打包
					new uglifyJsPlugin()
				],  //可以配置多个插件
					
					}
       