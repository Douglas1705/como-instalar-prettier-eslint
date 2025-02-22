# Como Instalar Prettier e ESLint

## Instalar Prettier e ESLint

```bash
npm install --save-dev eslint prettier eslint-plugin-prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks
```
<br>

## Crie ou edite o arquivo eslint.config.js na raiz do projeto e adicione:
```bash
import globals from 'globals';
import reactHooks from 'eslint-plugin-react-hooks';
import reactRefresh from 'eslint-plugin-react-refresh';
import prettier from 'eslint-plugin-prettier';
import pluginReact from 'eslint-plugin-react';
import typescriptParser from '@typescript-eslint/parser';

export default [
  {
    ignores: ['dist'],
  },
  {
    files: ['**/*.{ts,tsx}'],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
      parser: typescriptParser,
      sourceType: 'module',
    },
    plugins: {
      'react-hooks': reactHooks,
      'react-refresh': reactRefresh,
      prettier,
      'react': pluginReact,
    },
    settings: {
      react: {
        version: 'detect',
      },
    },
    rules: {
      'prettier/prettier': 'error',
      'react-hooks/rules-of-hooks': 'error',
      'react-hooks/exhaustive-deps': 'warn',
      'react/react-in-jsx-scope': 'off',
      '@typescript-eslint/explicit-module-boundary-types': 'off',
      'no-multi-spaces': 'error',
      'no-trailing-spaces': 'error',
      'react/jsx-uses-react': 'error',
      'react/no-deprecated': 'warn',
      'react/no-direct-mutation-state': 'error',
      'react/no-unknown-property': 'error',
      'react/no-array-index-key': 'warn',
      'react/jsx-no-bind': 'warn',
      'semi': ['error', 'always'],
      'semi-style': ['error', 'last'],
      'comma-dangle': ['error', 'always-multiline'],      
      'quotes': ['error', 'single'],
      'no-console': 'warn',
      'no-unused-vars': ['error', { 'argsIgnorePattern': '^_' }],
      'react/prop-types': 'off',
      'eol-last': ['error', 'always'],
      'no-multiple-empty-lines': ['error', { 'max': 1 }],
      'object-curly-spacing': ['error', 'always'],
      'array-bracket-spacing': ['error', 'never'],
      'arrow-spacing': ['error', { 'before': true, 'after': true }],
      'prefer-const': 'error',
      'no-var': 'error',
      'eqeqeq': ['error', 'always'],
      'no-duplicate-imports': 'error',
      'react-refresh/only-export-components': [
        'warn',
        { allowConstantExport: true },
      ],
    },
  },
];
```

<br>

## Verifique as mensagens nos imports; às vezes, pode ser necessário instalar:
```bash
npm i --save-dev @types/eslint-plugin-react-refresh
```
Nota: Para o plugin react-hooks, não é necessário instalar tipos separados.

<br>

## Crie um arquivo .prettierrc na raiz do projeto com o seguinte conteúdo:
```bash
{
  "singleQuote": true,
  "trailingComma": "all",
  "printWidth": 80,
  "endOfLine": "lf"
}
```

<br>

## Adicione o script format no seu package.json:
```bash
{
  "scripts": {
    "format": "prettier --write \"src/**/*.{js,jsx,ts,tsx,json,css,scss,md}\""
  }
}
```

<br>

## Instalar as Extensões do VS Code

Instale as seguintes extensões no Visual Studio Code, pesquisando por seus IDs:

- **ESLint**:
```bash
`dbaeumer.vscode-eslint`
```
- **Prettier ESLint**:
```bash
`rvest.vs-code-prettier-eslint`
```





