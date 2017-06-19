# gulp-css-spritesmith-lothar
modify according to gulp-css-spritesmith

此工具根据gulp-css-spritesmith做了稍微修改<br />
原工具作者：laoshu133<br />
原工具地址：https://github.com/laoshu133/gulp-css-spritesmith <br />
修改后配置如下：<br />
var module.name = ’phone‘；//举个栗子，省略了一些循环<br />
gulp.task('autoSprite', function() {<br />
    gulp.src('./public/stylesheets/' + module.name + '/**.css')<br />
        .pipe(autoSpriter({<br />
            //css文件输出地址，文件完整绝对地址<br />
            userFileDir: path.join(__dirname ,'dist/css/', module.name),<br />
            // sprite背景图源文件夹，只有匹配此路径才会处理，默认 images/slice/<br />
            imagepath: './public/images/' + module.name,<br />
            // 映射CSS中背景路径，支持函数和数组，默认为 null<br />
            imagepath_map: null,
            // 雪碧图输出目录，注意，会覆盖之前文件！默认 images/<br />
            spritedest: '../../images/' + module.name,<br />
            // 替换后的背景路径，默认 ../images/<br />
            spritepath: '../../images/' + module.name,<br />
            // 各图片间间距，如果设置为奇数，会强制+1以保证生成的2x图片为偶数宽高，默认 0<br />
            padding: 2,<br />
            // 是否使用 image-set 作为2x图片实现，默认不使用<br />
            useimageset: false,<br />
            // 是否以时间戳为文件名生成新的雪碧图文件，如果启用请注意清理之前生成的文件，默认不生成新文件<br />
            newsprite: false,<br />
            // 给雪碧图追加时间戳，默认不追加<br />
            spritestamp: false,<br />
            // 在CSS文件末尾追加时间戳，默认不追加<br />
            cssstamp: false<br />
        }))<br />
});<br />
目录示例：
<br />
├── MyApp/ <br />
        ├──public/ <br />
          ├── css/ <br /> 
                ├── phone/ <br />
                   └── index.css <br />
          ├─ images/ <br />
                ├── phone/ <br />
                  ├── icon-a.png <br />
                  ├── icon-a@2x.png <br />
                  ├── icon-b.png <br />
                  └── icon-b@2x.png <br />
       ├─dist <br />
          ├── css/ <br />
               ├── phone/ <br />
                    └── index.css <br />
          ├─ images/ <br />
              ├── phone/ <br />
                ├── icon.png <br />
                └── icon@2x.png <br />

