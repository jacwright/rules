## Add attributes to a user for specific connection

This rule will add an attribute to the user only for the login transaction (i.e. they won't be persistede to the user). This is useful for cases where you want to enrich the user information for a specific application.

```js
function (user, context, callback) {
  if (context.connection === 'company.com') {
    user.vip = true;
  }

  callback(null, user, context);
}
```