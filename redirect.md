# Redirect


### Client Side
```js
import {useRouter} from 'next/navigation'

const router = useRouter();
<button onClick={()=>router.push('/profile')}></button>
```

### Server Side 
```js
import {redirect} from 'next/navigation'

redirect('/login')
```
