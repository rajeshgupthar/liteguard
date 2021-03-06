![LiteGuard](https://raw.github.com/liteguard/liteguard/master/assets/liteguard_128.png)

[![Build Status](https://travis-ci.org/liteguard/liteguard.png?branch=master)](https://travis-ci.org/liteguard/liteguard) [![Build Status](http://teamcity.codebetter.com/app/rest/builds/buildType:%28id:bt973%29/statusIcon)](http://teamcity.codebetter.com/viewType.html?buildTypeId=bt973&guest=1)

Why, it's lighter than air!

The guard clause library which stands out from the crowd like the faintest passing whisper.

You'll hardly know it's there!

Get it at [NuGet](https://nuget.org/packages?q=liteguard "LiteGuard on NuGet").

## How do I use it?

```C#
public void Foo(Bar bar)
{
	Guard.AgainstNullArgument("bar", bar);
    Guard.AgainstNullArgumentProperty("bar", "Baz", bar.Baz);
    Guard.AgainstNullArgumentProperty("bar", "Baz.Bazza", bar.Baz.Bazza);

    // the rest of your method, nice and safe, wrapped in the protecting arms of LiteGuard
}

public void Foo<T>(T bar) where T : class
{
	Guard.AgainstNullArgument("bar", bar);
    ...
}

public void Foo<T>(T bar)
{
	Guard.AgainstNullArgumentIfNullable("bar", bar);
    ...
}
```

## Why did we create it?

The aim of LiteGuard is to be the most simple, unambiguous and lightweight guard clause library available.

### A very explicit DSL

The names of LiteGuard clauses are unambiguous to ensure correct usage. Misuse should be obvious.
```C#
public void Foo(Bar bar)
{
    var baz = GetBaz();
	Guard.AgainstNullArgument("baz", baz); // clearly incorrect - baz is not an argument
}
```

### No fluent API

Some guard clause libraries provide a fluent API.

A fluent API requires the creation of objects which serve no purpose other than to provide an access point for the next method in the DSL. The creation of these objects decreases performance, increases memory usage and adds pressure to the garbage collector. It is our belief that a guard clause library has no business in doing this. It should use as few resources as possible and be eligible for use in as wide a set of applications as possible. We love a good fluent API but it has its places and a guard clause library is not one of them.

### No business rule clauses

Many guard clause libraries provide a huge range of methods for determining whether arguments satisfy all manner of business rules.

In our opinion, it is not the job of a guard clause library to validate arguments against business rules. We believe the role of a guard clause library is to prevent method calls with null arguments or null argument values. Ideally, we'd like such things to be built into .NET languages. If that ever happens we will happily allow LiteGuard to retire gracefully to a small but comfortable home near the seaside with a carriage clock and a little Havanese.

## Where do I get it?

Install it from [Nuget](https://nuget.org/packages/LiteGuard/). For update notifications, follow [@adamralph](https://twitter.com/#!/adamralph).

To build manually, clone or fork this repository and see ['How to build'](https://github.com/liteguard/liteguard/blob/master/how_to_build.md).

## Can I help to improve it and/or fix bugs? ##

Absolutely! Please feel free to raise issues, fork the source code, send pull requests, etc.

No pull request is too small. Even whitespace fixes are appreciated. Before you contribute anything make sure you read [CONTRIBUTING.md](https://github.com/liteguard/liteguard/blob/master/CONTRIBUTING.md).

## What do the version numbers mean? ##

LiteGuard uses [Semantic Versioning](http://semver.org/). The current release is 0.x which means 'initial development'. Version 1.0 is imminent.

## Sponsors ##
Our build server is kindly provided by [CodeBetter](http://codebetter.com/) and [JetBrains](http://www.jetbrains.com/).

![YouTrack and TeamCity](http://www.jetbrains.com/img/banners/Codebetter300x250.png)

## Credits ##

LiteGuard logo designed by Vanja Pakaski.
