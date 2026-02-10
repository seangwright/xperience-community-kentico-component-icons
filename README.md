# Xperience Community: Kentico Component Icons

[![CI: Build and Test](https://github.com/seangwright/xperience-community-kentico-component-icons/actions/workflows/ci.yml/badge.svg)](https://github.com/seangwright/xperience-community-kentico-component-icons/actions/workflows/ci.yml)

[![Release: Publish to NuGet](https://github.com/seangwright/xperience-community-kentico-component-icons/actions/workflows/publish.yml/badge.svg)](https://github.com/seangwright/xperience-community-kentico-component-icons/actions/workflows/publish.yml)

[![NuGet Package](https://img.shields.io/nuget/v/XperienceCommunity.KenticoComponentIcons.svg)](https://www.nuget.org/packages/XperienceCommunity.KenticoComponentIcons)

## Description

A pre-packaged, annotated list of all icons used in Xperience by Kentico Page, Email, and Form Builder components. Great for AI agents building Xperience components!

The icon list is a C# class with doc comments on every icon that clearly describe what the icon looks like. This helps AI agents (and human developers) understand what the icon "looks like".

```csharp
public static class KenticoIcons
{
    /// <summary>
    /// Lowercase letter "a" in a simple font.
    /// </summary>
    public const string A_LOWERCASE = "icon-a-lowercase";
    /// <summary>
    /// Three horizontal lines with a bordered rectangle above.
    /// </summary>
    public const string ACCORDION = "icon-accordion";
    /// <summary>
    /// Puzzle piece with a plus sign circle badge.
    /// </summary>
    public const string ADD_MODULE = "icon-add-module";
    /// <summary>
    /// Simplified robot figure with antennae and rounded limbs.
    /// </summary>
    public const string ANDROID = "icon-android";
    /// <summary>
    /// Stylized apple with a leaf and a bite taken out
    /// </summary>
    public const string APPLE = "icon-apple";
    // ...
}
```

## Requirements

### Library Version Matrix

| Xperience Version | Library Version |
| ----------------- | --------------- |
| No dependency     | >= 1.0.0        |

### Dependencies

- [.NET 10.0](https://dotnet.microsoft.com/en-us/download)
- [Xperience by Kentico](https://docs.kentico.com) or [Kentico Xperience 13](https://docs.kentico.com/13)

## Package Installation

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

> [!NOTE]
> The descriptions for these icons were generated with $0.04 of OpenAI credits using `gpt-4.1-mini` to analyze the icons.
> The `/lib` folder contains the entire vibe-coded Python app used to scrape the Kentico icons web page, screenshot the icon fonts
> call the OpenAI API and store the details in the xlsx file.
> Another vibe-coded script was run to generate the XML doc comments in the icons file.
> This Python app contains its own README so you can run it yourself to see it work.

## Full Instructions

View the [Usage Guide](./docs/Usage-Guide.md) for more detailed instructions on permission management and custom scenarios.

## Contributing

To see the guidelines for Contributing to Kentico open source software, please see [Kentico's `CONTRIBUTING.md`](https://github.com/Kentico/.github/blob/main/CONTRIBUTING.md) for more information and follow the [Kentico's `CODE_OF_CONDUCT`](https://github.com/Kentico/.github/blob/main/CODE_OF_CONDUCT.md).

Instructions and technical details for contributing to **this** project can be found in [Contributing Setup](./docs/Contributing-Setup.md).

## License

Distributed under the MIT License. See [`LICENSE.md`](./LICENSE.md) for more information.

## Support

This project is provided freely to the Kentico community and has no guaranteed support policy. If updates to this repository are not made on timelines that meet your needs, you are welcome to fork it and customize your version to add features and resolve bugs 😄.
