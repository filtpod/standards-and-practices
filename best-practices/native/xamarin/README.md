# Xamarin
So, you think you can "Xam?"  I don't know if you think that you can!  At any rate, I'm here to help you and when that doesn't work... to tell you what to do.

## Follow C# Best Practices and Then Some
Xamarin projects employ C#.  As such, you should follow EngageAI's best practices for C#.  Consider K&R style and expression body syntax when possible to keep code LOC as readable and *concise* as possible.  Don't make us read three lines for one expression.

[Stack Overflow - Visual Studio and K&R](https://stackoverflow.com/questions/3048800/how-can-i-set-visual-studio-to-use-kr-style-bracketing/)

By default, Visual Studio uses the more spacious Allman style.

## Three Projects - But Concentrate on Shared
Xamarin projects targeting mobile devices typically have three projects in one solution.  Structure your business logic and general layout / styles in the *shared project*.  An Android and iOS project each are provided in Xamarin solutions for custom renderers and platform specific stuff (still written in C#).  Use custom renderers, for example, to perform explicit mutations on elements as they are drawn per platform.  For instance, adding a custom border to an Android text entry control.

## Know the Layout Tools
Research `Grid`, `StackLayout` and `RelativeLayout`, Et al.  Know what they do and use them *appropriately*.  Do not use `Grid` when you need `StackLayout`, etc.  Don't needlessly nest layouts, please.  And don't use `AbsoluteLayout` unless you totally need to for a legitimate reason.

[Xamarin Layout Views](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/controls/layouts/)

Remember, in Xamarin, `z-index` is controlled by the order elements are described in the XAML documents.  And you *can* use negative margins.

## Use MVVM and Data Binding
Code-behind should be used as a last resort but there are certainly reasons to extend your view in your code-behind file.  Don't be a purist, but always endeavor to bind properties and `Command` members.  When commands aren't exposed as a `BindableProperty` member then use `EventToCommand` pattern.

## Use Shell
Xamarin Shell has a glut of benefits.  URL-ish, abstracted navigation is one of them, among others.

Note that this technology is new to Xamarin Forms but do indeed attempt to use it unless you need a completely custom UI and custom flyout menu.  There are still some small growing pains.  For example, as of 09/11/2019 they still don't have a bindable, XAML-based back-button override that works without crashing.  Freunlaven!

## Consider Using Prism
Prism is a library that also provides a navigation service, simplified MVVM, dependency injection and simplified EventToCommand behavior.  It may be a good fit for your Xamarin application and is used in at least one (as of writing this) EngageAI project, [FrontDeskKiosk](https://github.com/filtpod/fusd-front-desk-kiosk).  Xamarin Shell steals a bit of thunder from Prism, however, so it may be less useful if Shell is employed.

[Prism for WPF and Xamarin](http://prismlibrary.github.io/docs/)

## Examples Are For Pruhs, Bruhs
I got what you need right here:

- [FrontDeskKiosk](https://github.com/filtpod/fusd-front-desk-kiosk), for Prism implementation, Prism navigation, error-handling, and how to build a custom, reusable control that extends XAML vocabulary.  Targets Android and Windows, UWP.
- [KidWatcher](https://github.com/filtpod/FUSDMonitoringAppXamarin), for job building, intents, running as a background worker, etc.  There's basic UI.  Xamarin.Android.
- [Clair](https://github.com/filtpod/sinclair-scanner-application), for Xamarin Shell, Forms, camera and [linking an application in response to URL clicks](https://github.com/filtpod/sinclair-scanner-application/pull/137).  Targets Android and iOS.

## Deployment
See the Clair project right above.  Deployment documentation to do Android (Play Store) and iOS (App Store) is pretty detailed there, along with screenshots.
