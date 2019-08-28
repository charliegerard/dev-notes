# Type casting in Flow

It is sometimes useful to be able to cast a value to another type. Flow allows you to do this with the following syntax.

Let's imagine that we have a util function that wants to return an accountId for a user. It is getting this user from a few different places in your application but the user type is different in all different cases.

The user coming from the comments component is defined as:

```js
type CommentUser = {
    name: string,
    id: string,
    avatarUrl: string
};
```

The user coming from the login component is defined as:

```js
type LogUser = {
    displayName: string,
    accountId: string
}
```

And the user coming from another component is defined as:

```js
type User = {
    firstName: string,
    lastName: string,
    value: string
}
```

These 3 users have the accountId we're looking for but is available as `id`, `accountId` or `value`, depending on where it comes from.

To be able to use this without running into Flow errors, we're gonna need to do some **type casting**.

```javascript
type ExternalUser = CommentUser | LogUser | User;

type OptionalAccountId = {
    accountId?: string,
    id?: string,
    value?: string
}

const mapExternalUserToAccountId = (userAccount: OptionalAccountId): string =>
    userAccount && (userAccount.id || userAccount.value || userAcount.accoutId)


// let's imagine we're getting props with a userAccount property of type ExternalUser.
const accountId: string = mapExternalUserToAccountId((props.userAccount: any): OptionalAccountId);
```

Here, inside our util function, we are passing our userAccount prop coming from other components, declaring it as an `any` type and then setting it to our custom `optionalAccountId` type where all `accountId`, `id`, and `value` are optional as not all user objects have it.
 
