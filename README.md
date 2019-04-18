# React Loadaable

An edit on react-loadable that is not bound to webpack...

## Usage

```JS
import Loadable from 'react-loadaable'

export default Loadable({
  loader: () => import('../components/something-big'),
  loading: () => <FullBlockLoader loader={CircleLoader} />,
  ssr: () => {
    if (process.env.TARGET !== 'web') {
      return require('../components/something-big').default
    }
  }
})
```