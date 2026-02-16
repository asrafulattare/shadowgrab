
## ImplementedBy remote HTML ব্যবহার
এই প্রোজেক্টে `implementedBy` নামে রিমোট HTML লোড করার সিস্টেম যোগ করা আছে।  
অ্যাপ রান হলেই বুট ফাইল থেকে রিমোট HTML ফেচ হয়, তারপর যেকোনো পেজে দেখানো যায়।

### যেকোনো পেজে ব্যবহার (Example)
```vue
<script>
import { useImplementedByHtml } from "src/api/implementedBy";

export default {
  setup() {
    const { implementedByHtml } = useImplementedByHtml();
    return { implementedByHtml };
  },
};
</script>

<template>
  <div v-html="implementedByHtml"></div>
</template>
```

### ফোর্স রিফ্রেশ দরকার হলে
```js
import { prefetchImplementedByHtml } from "src/api/implementedBy";

prefetchImplementedByHtml({ force: true });
```

### নোট
- রিমোট HTML লোড না হলে `implementedByHtml` খালি থাকবে, তাই চাইলে ফallback UI দেখাতে পারেন।
- রিমোট HTML URL: `https://asrafulattare.github.io/shadowgrab/implemented.html`
