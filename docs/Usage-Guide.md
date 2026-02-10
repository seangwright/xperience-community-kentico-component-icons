# Usage Guide

## Setup

Add the package to any project with component registration attributes, using the .NET CLI.

```powershell
dotnet add package XperienceCommunity.KenticoComponentIcons
```

## Quick Start

Register the library's services in your ASP.NET Core application:

```csharp
// FAQWidget.cs

using Kentico.Content.Web.Mvc;
using Kentico.PageBuilder.Web.Mvc;
using Kentico.Xperience.Admin.Base.FormAnnotations;
using Kentico.Xperience.Admin.Base.Forms;
using XperienceCommunity.KenticoComponentIcons;

[assembly: RegisterWidget(
    identifier: FAQWidget.IDENTIFIER,
    viewComponentType: typeof(FAQWidget),
    name: FAQWidget.NAME,
    propertiesType: typeof(FAQWidgetProperties),
    Description = "Displays FAQ items in an expandable accordion format",
    IconClass = KenticoIcons.CHECKLIST,
    AllowCache = true)]

namespace App.Components.PageBuilder.Widgets.FAQ;

public class FAQWidget : ViewComponent
{
  // ...
}
```

Every icon field in `KenticoIcons` is annotated with a comment describing the visual appearance of the icon. This means you can use an AI agent to select icons for each Widget, Section, etc... in your project by having it analyze the `KenticoIcons` class.
