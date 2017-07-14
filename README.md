## RNS
An abstraction on top of AsyncStorage for React-Native.
Also support local cache. (It's not recommended)

### Usage

`npm install rns`

```javascript
import RNS from 'rns'
import { AsyncStorage } from 'react-native'

const appName = 'test'

const rns = new RNS(appName, {
    AsyncStorage,
    expire: 24 * 3600 * 1000, //expireTime for local cache
})

rns.SET('hello', 'world') 
rns.GET('hello') // 'world'

rns.SETC('hello', {
    hello: 'world'
}) // set in local cache, just support data like JSON

rns.GETC('hello') // {hello: 'world'}

```