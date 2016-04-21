# eslint-formatter-pretty [![Build Status](https://travis-ci.org/sindresorhus/eslint-formatter-pretty.svg?branch=master)](https://travis-ci.org/sindresorhus/eslint-formatter-pretty)

>  Pretty formatter for [ESLint](http://eslint.org)

![](screenshot.png)


## Install

```
$ npm install --save-dev eslint-formatter-pretty
```


## Usage

### ESLint CLI

```
$ eslint --format=node_modules/eslint-formatter-pretty file.js
```

### [grunt-eslint](https://github.com/sindresorhus/grunt-eslint)

```js
grunt.initConfig({
	eslint: {
		options: {
			format: 'node_modules/eslint-formatter-pretty'
		},
		target: ['file.js']
	}
});

grunt.loadNpmTasks('grunt-eslint');
grunt.registerTask('default', ['eslint']);
```
### [gulp-eslint](https://github.com/adametry/gulp-eslint)
```js
var gulp = require('gulp');
var eslint = require('gulp-eslint');

gulp.task('lint', function() {
	return gulp.src('./example.js')
		.pipe(eslint())
		.pipe(eslint.format('node_modules/eslint-formatter-pretty');
});
```

### [eslint-loader](https://github.com/MoOx/eslint-loader)
```js
module.exports = {
	entry: 'example.js',
	output: {
		'dist/',
		filename: '[name].js'
	},
	module: {
		loaders: [
			{ test: /\.js$/, loader: 'eslint-loader' }
		]	
	},
	eslint: {
		formatter: require('eslint-formatter-pretty')
	}
};
```

## Tip

In iTerm, <kbd>Cmd</kbd>+click the filename header to open the file in your editor.


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
