# Dynamic imports
- Dynamic imports is to lazily import libraries or modules or logic that use window or dom apis.
- Dynamic imports tells nextjs to not do SSR.

### Code for Lazy load react-components
```js
import dynamic from 'next/dynamic';

const HeavyComponent = dynamic(()=>import('./HeavyComponent'),{
    ssr:false
})

export default function Page(){
    return <HeavyComponent/>;
}
```

### Code for logic
```js
const util = async ()=>{
    const {heavyFunction} = await import("./bigfunction");
    heavyFunction.doSomething();
}
``` 
