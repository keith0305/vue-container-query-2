This is a fork from [Vue Container Query 2](https://github.com/Mehdi-Hp/vue-container-query-2) with a bug fix when 'useBEM' is set to false.

This library does not support Vue 3 (yet).

## v0.2.9:
- Now exports a new function ```VueContainerQueryMixin```, to allow the use of Vue mixin for per-component usage instead of enabling CQ globally.
    - The ```VueContainerQueryMixin``` function returns an object which can be used as mixin. This function accepts a config object. E.g.:

```js
import { VueContainerQueryMixin } from 'vue-container-query-3';

const cqMixin = VueContainerQueryMixin({
	classNames: {
		sizes: {
			'sm': 'sm',
			'md': 'md',
			'lg': 'lg',
			'xl': 'xl',
			'2xl': '2xl',
		},
		prepend: 'cq-',
	},
	useBEM: false,
});

export default {
	name: 'DemoComponent',
	mixins: [
		cqMixin,
    ],
    cq: {
		'sm': { minWidth: 640 },
		'md': { minWidth: 768 },
		'lg': { minWidth: 1024 },
		'xl': { minWidth: 1280 },
		'2xl': { minWidth: 1536 },
	},
}
```

