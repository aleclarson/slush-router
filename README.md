
# slush-router v1.0.0 

The `Router` class stripped from the `slush` library.

```js
const Router = require('slush-router')

const router = Router()

router.get('users', async (req, res) => {
  // Do your magic.
  users = await fetchUsers()

  // Return JSON object, status code, or undefined/null.
  return {users}
})

// You can match parts of the URL too!
router.get('users/:id', async (req, res) => {
  return {
    user: await fetchUser(req.query.id)
  }
})

// Unlock advanced route validation!
router.post(function() {
  this.match('users/:id')
  this.body = {name: 'string'}
  return async function(body, res) {
    await addUser({
      id: this.query.id,
      name: body.name,
    })
    return 201
  }
})
```

There's more, but I will document it later.

