# MAC
my-i18n-project
shell
mkdir my-i18n-project
cd my-i18n-project
npm init -y
Install Dependencies:

Install necessary dependencies like typescript (if you plan to use TypeScript), babel for transpilation, and other relevant packages.

shell
npm install typescript @babel/core @babel/preset-env
Directory Structure:

Set up a basic directory structure similar to Yoi18n.

my-i18n-project/
├── src/
│   ├── index.js
│   └── i18n/
│       ├── en.json
│       └── es.json
├── tests/
│   └── i18n.test.js
├── package.json
└── README.md
Create Core Functionality:

Write the core functions for loading and switching languages.

javascript
// src/index.js
const translations = {
  en: require('./i18n/en.json'),
  es: require('./i18n/es.json')
};

let currentLang = 'en';

const t = (key) => {
  return translations[currentLang][key] || key;
};

const setLanguage = (lang) => {
  if (translations[lang]) {
    currentLang = lang;
  }
};

module.exports = { t, setLanguage };
Add Tests:

Write tests to ensure your internationalization functionality works correctly.

javascript
// tests/i18n.test.js
const { t, setLanguage } = require('../src/index');

test('translation test', () => {
  setLanguage('es');
  expect(t('hello')).toBe('hola');
});
Documentation:

Create a README.md file to document how to use your internationalization tool.

markdown
# My I18n Project

A simple internationalization tool for JavaScript applications.

## Installation

```shell
npm install my-i18n-project
Usage
javascript
const { t, setLanguage } = require('my-i18n-project');

setLanguage('es');
console.log(t('hello')); // Output: 'hola'

Version Control:

Initialize a Git repository and push your project to GitHub.

shell
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/my-i18n-project.git
git push -u 
