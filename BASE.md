# Configuracion de vscode

- Instalar extensiones recomendadas
- Configurar gist y etc.

- Instalar modulos npm requeridos

```
yarn add -D eslint@^7.11.0 eslint-plugin-react prettier prettier-eslint eslint-plugin-jest eslint-plugin-react-hooks @typescript-eslint/eslint-plugin @typescript-eslint/parser husky
yarn add -D @typescript-eslint/eslint-plugin@latest

Solo funciona en linux o con gitbash
yarn add -D @commitlint/{config-conventional,cli}
```

- Agregar scripts en package.json

```json
{
  "scripts": {
    "lint": "eslint \"**/*.{ts,tsx,js,jsx}\"",
    "prepare": "husky install"
  }
}
```

- Agregar precommit hook con husky
  Crear carpeta `.husky`

```
npx husky add .husky/pre-commit 'yarn lint && yarn test --watchAll=false'
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit $1'

```

Se puede agregar -n/--no-verify en el commit para salta esta validacion
