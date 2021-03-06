# AuthPackage
Easy and Simple way to add membership feature to your project.
based on Asp.net Identity, Owin, Entity Framework.

Every time you want to setup Asp.net Identity on your project you'll need to add several packages, create new classes and get alot of error, AuthPackage is pre-configured library that enables you to use Asp.net Identity Features in easy way.

## Install
To install AuthPackage, run the following command in the Package Manager Console
```
Install-Package AuthPackage
```

or visit package page on [Nuget](https://www.nuget.org/packages/AuthPackage/)

## How to use:
First of all you need to create instance of 
```
AuthUser(HttpContext)
```

Second you can use one of the features
```
SignIn(string email, string password) 
SignOut()
Register(string email,string password)
```

Finally you need to configure the ConnectionString in your web.config
```
//add this code to   <appSettings>
 <add key="connectionString" value="connectionStringHere" />
```

##Example:
```
 public async Task<ActionResult> SignIn()
        {
            var context = System.Web.HttpContext.Current;
            AuthUser authUser = new AuthUser(context);
            await authUser.SignIn("waleedchayeb2@gmail.com", "123456");
            return RedirectToAction("Index", "Home");
        }

```

##Next Update:

* Ability to configure new Fields in user Table.
* Ability to signIn using Google, Microsoft, Twitter, Facebook.
* Get User Roles.
* Change user roles.
* Delete User.

Credit: [Waleed Chayeb](https://www.wchayeb.com/)
