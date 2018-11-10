# external-load
This small function helps you to load external CSS / Javascript from url.

It's helpful if you are using some framework, and code that you wanted to use is not directly supported by that framework, and you don't want to put load scripts into your html (why? code splitting).

Load is a immediately invoked function which returns 3 functions that you may use;

```
Load.js()
Load.css()
Load.img()
``` 

This functions take url and return promise. In case off error, you can catch it.

# Usage
```
import Load from 'external-load';

Load.js('https://js.stripe.com/v3/')
    .then( () => {
        // Stripe is now avaliable
        const stripe = Stripe(environment.stripeKey);
    })
    .catch( error => {
        console.log(error)
    })
```

# Credit

This function is taken from David Walsh's [Create a Basic Loader with JavaScript Promises](Create a Basic Loader with JavaScript Promises) tutorial. Reason I'm publishing is; It's been very useful for me, and It's hard to find the code.