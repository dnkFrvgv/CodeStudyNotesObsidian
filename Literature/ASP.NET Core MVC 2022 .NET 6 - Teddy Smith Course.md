# ASP.NET Core MVC 2022 .NET 6 - Teddy Smith Course
#literature | #youtube | *15/12/23* | [[ASP.NET Core MVC]] | [Link](https://www.youtube.com/playlist?list=PL82C6-O4XrHde_urqhKJHH-HTUfTK6siO)

---
# 1. overview

Flow of the request: Controller to View to Model

Controller 
- Is the door to your app
- Think URL

Model 
- business rules

View
- display data on web page

---
- program.cs file - where all of your options, configurations and middlewares are bundled together.
- wwwroot folder - assets
---
# 2. Models

- Poco - plain old c# objects
	- Just a normal class, no attributes describing infrastructure concerns or other responsibilities that your domain objects shouldn't have
	- are not c# objects - they are a database table representations
	
```c#
public class Address
{
	[Key]
	public int Id { get; set; }
	public string Street { get; set; }
	public string City { get; set; }
	public string State { get; set; }
}
```

When you build models you are using [[Programação Orientada a Objetos - OOP#Abstração ( Generalização e Especialização)|abstraction]]. You abstract the complexity of the app - Instead of putting every information into one single table, the information is separated into multiple tables.

---
## 3 - install EF

you are "Installing the data layer".

- Create Data folder
- Install NuGut packages
	- `Microsoft.EntityFrameworkCore`
	- `Microsoft.EntityFrameworkCore.SqlServer` - if using SQL Server
	- `Microsoft.EntityFrameworkCore.Tools`
- Add [[Entity Framework|dbcontext class]]:

```c#
using Microsoft.EntityFrameworkCore;

namespace RunningWebAppMVC.Data
{
    public class ApplicationDbContext : DbContext
    {
    }
}

```

- Add `DbSet` 
- Build the EF service:

```c#
builder.Services.AddDbContext<ApplicationDbContext>(options =>
{
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection"));
});

// program file
```

- Add Connection String:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=[server];Database=[database];Trusted_Connection=True;TrustServerCertificate=True"
},

// appsettings
```

- Add initial migration with EF-tools command: `Add-Migration InitialMigration`
- Add seed data class and set up the seed command:

```C#
if(args.Length == 1 && args[0].ToLower() == "seeddata")
{
    Seed.SeedData(app);
}
```

- Add create database with EF-tools command: `Update-Database`
- Add populate the database with the seed data with the command: `dotnet run seeddata`

---
# 4 - controllers

control the URLs

Controller
- add new controller
- add new view/razor page
	- Folder with the same name as the model
	- The view should match the action name on the controller

---
# 5 View

Views are web pages
Copy and paste bootstrap from [examples](https://getbootstrap.com/docs/5.3/examples/)


- Attach the model to the view:

 ```c#
public IActionResult Index() // Controler
{
	var clubs = _context.Clubs.ToList(); // Model
	return View(clubs); // View
}
```

-  Declare the type of model to the razor page:

```c#
@model IEnumerable<Club>
```