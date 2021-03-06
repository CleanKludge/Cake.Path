# Cake.Path

A Cake AddIn that extends Cake with the ability to add items to the PATH.

[![cakebuild.net](https://img.shields.io/badge/WWW-cakebuild.net-blue.svg)](http://cakebuild.net/)
[![NuGet Version](http://img.shields.io/nuget/v/Cake.Path.svg?style=flat)](https://www.nuget.org/packages/Cake.Path/)


## Dependencies

* Cake v0.17

## Including the AddIn

```csharp
#addin "Cake.Path"
```

## Usage

```csharp
#addin "Cake.Path"

...

Task("AddToPath")
    .Does(() => 
    {
        AddToPath("C:\\Python27\\");
    });

Task("AddToPathWithSettings")
    .Does(() => 
    {
        var settings = new PathSettings {
           Target = PathTarget.User // Target is only available in net45
        }
        
        AddToPath("C:\\Python27\\", settings);
    });

Task("RemoveFromPath")
    .Does(() => 
    {
        RemoveFromPath("C:\\Python27\\");
    });

Task("RemoveFromPathWithSettings")
    .Does(() => 
    {
        var settings = new PathSettings {
           Target = PathTarget.Machine // Target is only available in net45
        }
        
        RemoveFromPath("C:\\Python27\\", settings);
    });

Task("ReloadPath")
    .Does(() => 
    {
        ReloadPath();
    });

Task("GetEnvironmentPath")
    .Does(() => 
    {
        string path = GetEnvironmentPath();
    });

Task("GetEnvironmentPathWithSettings")
    .Does(() => 
    {
        var settings = new PathSettings {
           Target = PathTarget.Machine // Target is only available in net45
        }
        
        string path = GetEnvironmentPath(settings);
    });

```

# General Notes
**Please note Target is only available on net45**

**This is an initial version and not tested thoroughly**.

I've made these AddIns for use in my own cake scripts therefore they have only been tested on Windows.
