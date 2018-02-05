# Gulp
---

类似于webpack. 是一款打包工具.


# Install
---

```
npm install --global gulp
npm install --save-dev gulp
```

# Usage
---


```
gulp.task('default', function() {
  // 将你的默认的任务代码放在这
});
```

# Plugins
---

我看了下面的方式就喜欢上了这种方式, Fluent 方式的处理, 通过pipe一个一个加载插件.

```
const gulp = require('gulp');
const cleanCSS = require('gulp-clean-css');
const less = require('gulp-less');
const rename = require('gulp-rename');
const autoprefixer = require('gulp-autoprefixer');

// 编译less
gulp.task('css', function () {
    gulp.src('../src/styles/index.less')
        .pipe(less())
        .pipe(autoprefixer({
            browsers: ['last 2 versions', 'ie > 8']
        }))
        .pipe(cleanCSS())
        .pipe(rename('iview.css'))
        .pipe(gulp.dest('../dist/styles'));
});

// 拷贝字体文件
gulp.task('fonts', function () {
    gulp.src('../src/styles/common/iconfont/fonts/*.*')
        .pipe(gulp.dest('../dist/styles/fonts'));
});

gulp.task('default', ['css', 'fonts']);

```

