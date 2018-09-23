# Server Side Rendering

## Next.js
- create pages folder
- only pages folder is the special directory in next.js
- Import `Link from 'next/link';`
- Link is a client side routing
- As long as the link is valid it will route ex. /about there should be a about.js in the pages folder
```javascript
import Link from 'next/link';

const Index = () => (
  <div>
    <Link href="/about">
      <button>Go to About Page</button>
    </Link>
    <p>Hello Next.js</p>
  </div>
)

export default Index
```
