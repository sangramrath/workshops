
### Clone & Run Squidex locally using Containers

### Clone & Run the code locally

__Note__ if you receive the following error, temporarily use legacy SSL provider (highly not recommended beyond this demo)

```
export NODE_OPTIONS=--openssl-legacy-provider
```

1. Edit the __src/service/index.js__ file to update the _url, appName, clientId and clientSecret_ values with actual values from the Squidex App.
```
export const CONFIG = !DEV ? {
    url: 'https://cloud.squidex.io',
    appName: 'hotels',
    clientId: 'hotels:default',
    clientSecret: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
} : {
    url:  'http://localhost:5000',
    appName: 'hotels',
    clientId: 'hotels:default',
    clientSecret: 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
};
```
2. Install the packages using `npm install`
3. Run the code using `npm start`

