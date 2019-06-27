# dila-api-client

This JS package helps querying the DILA API

## Usage

You need to set two envrionment variables : `OAUTH_CLIENT_ID` and `OAUTH_CLIENT_SECRET`.

These variables are the "oauth identifier" defined in your custom application in the [AIFE portal](https://developer.aife.economie.gouv.fr)

## Récupérer la table des matières d'un code

```js
const DilaApiClient = require("dila-api-client");

const dilaApi = new DilaApiClient();

dilaApi.fetchCodeTableMatieres({
  date: new Date().getTime(),
  sctId: "",
  textId: "LEGITEXT000006072050"
}).then(console.log)

```

## Other API calls

```js
dilaApi.apiFetch({
  path: 'dila/legifrance/lf-engine-app/list/code'
  method: 'POST,
  params: {
    test: 42
  }
}).then(console.log)
```

## Debug

you need to set the `DEBUG=dila-api-client` environment variable in order to see
the output of inner logs.