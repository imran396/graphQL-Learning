# What is GraphQL
GraphQl is a query language for api. This service is created by defining
types and fields, Each fields on each type will have own method.
example:
```
type Query{
 me: User
}
type User{
 id: Id
 name: String
}
```
The functions along each field on each type:
```
function Query_me(request){
    return request.auth.user;
}
function User_name(user){
    return user.getName();
}
```
After graphQl service is running it can receive graphQl queries and execute. First the service query will 
check defined type and fields then call provided function to produce result.

For example the query
```
{
    me{
       name
      }
}
Output:
{
  "me": {
    "name": "Luke Skywalker"
  }
}
```