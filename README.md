# GGTools — Package List

Catálogo de pacotes das GGTools consumido pela aba **Packages** da *GGTools Config Window*
(pacote `com.ggtools.windowconfig`).

## Como usar

Na Unity: `Window ▸ GGTools Config Window ▸ Packages` e cole a **raw URL** do `catalog.json`:

```
https://raw.githubusercontent.com/GazGamesOrganization/GGTools.PackageListJson/main/catalog.json
```

Clique em **Atualizar** para carregar a lista e em **Instalar** para adicionar a tool
(e suas dependências) ao Package Manager do projeto.

> Se este repositório for **privado**, a `raw.githubusercontent.com` exige autenticação e o
> download pela janela falha (404). Deixe **este** repositório público para o catálogo ser
> baixável — os repositórios das tools podem continuar privados (a instalação via git usa as
> suas credenciais git).

## Formato (`catalog.json`)

```json
{
  "tools": [
    {
      "name": "Nome exibido",
      "description": "Descrição curta.",
      "id": "com.ggtools.exemplo",
      "gitUrl": "https://github.com/GazGamesOrganization/Repo.git",
      "dependencies": ["com.ggtools.windowconfig"]
    }
  ]
}
```

- `id`: nome do pacote (usado para marcar "Instalado ✔").
- `gitUrl`: URL git do pacote (aceita `...git?path=/Packages/x#branch`).
- `dependencies`: git URLs, ids de registry (`com.unity.*`) ou o `id` de outra tool deste
  catálogo (resolvido para o `gitUrl` dela). Dependências de registry declaradas no
  `package.json` de cada pacote são resolvidas automaticamente pelo UPM.
