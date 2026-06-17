- redux is a package installed by nope package manager (npm)
- redux is used to store a  large files globally without using context api
- context api doesn't handle large files
- now redux is a toolkit whose full name is Redux Tool Kit (RTK)
![[Pasted image 20260617100251.png]]
- context api is built in in react
- file - global (provider)
- eg theme , user , auth , cart 
- main - (themeprovider(app)themeprovider)
- (userprov(app)userprov)
- (authprov(app)authprov)
```
Next.js using the `with-redux` template  
npx create-next-app --example with-redux my-app

```
- redux is basically built on typescript when we use it in other languages it converts to that language 
- For more info visit [redux core docs](https://redux-toolkit.js.org/introduction/getting-started)
# how to use 
first we have to make a file named store and userslice 
```
redux 
|
|__>store.js
|_>userslice
```
in store we have to configure the store 
```
import { configureStore } from '@reduxjs/toolkit'   
export const store = configureStore({  
reducer: { 
users: usersReducer,  
},  
})
```
then we have to make a slice e.g. userslice or counterslice
```
import { createSlice } from '@reduxjs/toolkit'
const intialState = {
user :{
name:"ali"
email:"abc@gmail.com"
}
}
export const userslice = createSlice ({
name:"user",
initialState,
reducers:{
setUser : (state,action)=>{
state.user = action.payload
},
clearUser:(state)=>{
state.user = null
}
}
})
export default userSlice.reducer
```
- now in app file
```
const user = userSelector((state)=>state.user.user)

```