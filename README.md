## Tecnologias

[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)

- [Commitizen](http://commitizen.github.io/cz-cli/)

---

- [Husky](https://typicode.github.io/husky/#/)

```sh
$ npm i husky -D

$ npx husky install

# Adicionar o hook para utilizar o commitizen
$ npx husky add .husky/prepare-commit-msg "exec < /dev/tty && npx cz --hook || true"
```

---

- [Semantic-release]()

```sh
# Instalação da dependência
$ npm i semantic-release -D

# Plugins adicionais
$ npm i @semantic-release/git @semantic-release/changelog -D
```

Adicionar o arquivo `.releaserc.json` contendo:

> Adicionar plugins ou realizar configurações no **semantic-release**.

```json
{
  "plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/github",
    "@semantic-release/changelog",
    [
      "@semantic-release/npm",
      {
        "npmPublish": false
      }
    ]
  ]
}
```

Os plugins `"@semantic-release/commit-analyzer"`, `"@semantic-release/release-notes-generator"`, `"@semantic-release/npm"`, `"@semantic-release/github"` já vem pré-instalados junto ao **semantic-release**;  
 Porém, se adicionados novos plugins, o arquivo de configuração sobescreve o padrão, por isso é preciso incluí-los também no `.releaserc.json`;
