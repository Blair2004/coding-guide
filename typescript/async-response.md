## Async Response : In what does that consist
Async response is an interface which describe how the server return data to an application or in response to a request.
Each request which lead to a specific action (deleting something, creating something, doing a specific action). 
We're then assuming we're handling a single component or a set of specific items. The response is therefore specific as follow : 
```json
{
    "type" : "success" | "error" | "failed" | "warning",
    "message" : "a description of the operation",
    "errors" : {
        "firstName" : [
            "this field is required !"
        ]
    },
    "data" : []
}
```
The response can then be a "success", "error", "failed" or "warning". The "errors" is required if we're handling a form validation. 
"data" doesn't follow a specific schema since it can be used differently according to the UI & component.

This doesn't apply if we're retriving items from the server. Here the resposne can only be an array fo that item. Here is an example : 
```json
[
    {
        "username"  :   "John Doe",
        "email"     :   "johndoe@email.com"
    }, {
        "username"  :   "Jane Doe",
        "email"     :   "janedoe@email.com"
    }
]
```
However, fetching items from the server might sometime lead to 403 errors, which return an AsyncResponse as explained on top.
