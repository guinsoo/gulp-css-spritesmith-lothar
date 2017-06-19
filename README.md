# gulp-css-spritesmith-lothar
modify according to gulp-css-spritesmith

此工具根据gulp-css-spritesmith做了稍微修改<br />
原工具作者：`laoshu133` <br />
原工具地址：https://github.com/laoshu133/gulp-css-spritesmith <br />
修改后配置如下：

        var module.name = 'phone'；//举个栗子，省略了一些循环 
        gulp.task('autoSprite', function() { 
                gulp.src('./public/stylesheets/' + module.name + '/**.css') 
                    .pipe(autoSpriter({ 
                    //css文件输出地址，文件完整绝对地址 
                    userFileDir: path.join(__dirname ,'dist/css/', module.name), 
                    // sprite背景图源文件夹，只有匹配此路径才会处理，默认 images/slice/ 
                    imagepath: './public/images/' + module.name, 
                    // 映射CSS中背景路径，支持函数和数组，默认为 null 
                    imagepath_map: null,
                    // 雪碧图输出目录，注意，会覆盖之前文件！默认 images/ 
                    spritedest: '../../images/' + module.name, 
                    // 替换后的背景路径，默认 ../images/ 
                    spritepath: '../../images/' + module.name, 
                    // 各图片间间距，如果设置为奇数，会强制+1以保证生成的2x图片为偶数宽高，默认 0 
                    padding: 2, 
                    // 是否使用 image-set 作为2x图片实现，默认不使用
                    useimageset: false,
                    // 是否以时间戳为文件名生成新的雪碧图文件，如果启用请注意清理之前生成的文件，默认不生成新文件
                    newsprite: false,
                    // 给雪碧图追加时间戳，默认不追加
                   spritestamp: false,
                    // 在CSS文件末尾追加时间戳，默认不追加
                    cssstamp: false
                }))
        });
        
目录示例：

        ├── MyApp/ 
                ├──public/ 
                   ├── css/ 
                        ├── phone/ 
                            └── index.css 
                   ├─ images/ 
                        ├── phone/ 
                            ├── icon-a.png 
                            ├── icon-a@2x.png 
                            ├── icon-b.png 
                            └── icon-b@2x.png 
                ├─dist/
                    ├── css/
                        ├── phone/
                            └── index.css 
                    ├─ images/ 
                        ├── phone/ 
                        ├── icon.png
                        └── icon@2x.png
