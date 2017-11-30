# eslint-config
ESLint config with dependencies in a single package

## Installation
```
npm install --save-dev @methodexists/eslint-config
```
Ignore these warnings:  
```
npm WARN eslint-plugin-react@7.0.1 requires a peer of eslint@^3.0.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-config-airbnb@15.0.1 requires a peer of eslint@^3.19.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-import@2.3.0 requires a peer of eslint@2.x - 3.x but none is installed. You must install peer dependencies yourself.
npm WARN eslint-plugin-jsx-a11y@5.0.3 requires a peer of eslint@^2.10.2 || 3.x but none is installed. You must install peer dependencies yourself.
npm WARN eslint-config-airbnb-base@11.3.2 requires a peer of eslint@^3.19.0 || ^4.5.0 but none is installed. You must install peer dependencies yourself.
npm WARN eslint-config-airbnb-base@11.3.2 requires a peer of eslint-plugin-import@^2.7.0 but none is installed. You must install peer dependencies yourself.
```

In your `package.json` add the following:
```
"scripts": {
  "lint-fix": "./node_modules/.bin/eslint --fix <YOUR_PROJECT_SRC>",
  "lint": "./node_modules/.bin/eslint --ext .js <YOUR_PROJECT_SRC>",
}
```
where `<YOUR_PROJECT_SRC>` is a dir or space-separated dirs where your javascript code lives. E.g. `src` or `src tests`.

### Pre-commit lint
To keep your repo clean from lint errors add pre-commit lint check. Make it smart enough to check only commited files rather than whole repo by using `lint-staged` util:
```
npm install --save-dev pre-commit lint-staged
```
In your `package.json` add the following:
```
"scripts": {
  "lint-staged": "lint-staged"
},
"pre-commit": [
  "lint-staged"
],
"lint-staged": {
  "*.js": "eslint"
}
```

## Usage
### Check whole repo for the lint errors
```
npm run lint
```

### Auto-fix lint errors where possible
```
npm run lint-fix
```

## Realtime lint in editors
Make sure that your editor set up to use locally installed eslint (`./node_modules/.bin/eslint`)

### Sublime
### VIM
