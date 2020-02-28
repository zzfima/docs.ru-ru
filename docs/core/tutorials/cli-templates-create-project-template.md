---
title: Создание шаблона проекта для dotnet new
description: Из этой статьи вы узнаете, как создать шаблон проекта для команды dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503535"
---
# <a name="tutorial-create-a-project-template"></a>Учебник. Создание шаблона проекта

С помощью .NET Core вы можете создавать и развертывать шаблоны, которые генерируют проекты, файлы и даже ресурсы. Это руководство представляет собой вторую часть серии, в которой описано, как создавать, устанавливать и удалять шаблоны с помощью команды `dotnet new`.

Из этой части вы узнаете, как выполнять такие задачи:

> [!div class="checklist"]
>
> * создание ресурсов для шаблона проекта;
> * создание папки и файла конфигурации шаблона;
> * установка шаблона из файла;
> * тестирование шаблона элемента;
> * удаление шаблона элемента.

## <a name="prerequisites"></a>Предварительные требования

* Изучите [первую часть](cli-templates-create-item-template.md) этой серии руководств.
* Откройте терминал и перейдите к папке _working\templates_.

## <a name="create-a-project-template"></a>Создание шаблона проекта

Шаблоны проектов предоставляют готовые проекты, которые упрощают пользователям взаимодействие с рабочим набором кода. .NET Core включает несколько шаблонов проектов, например консольное приложение или библиотеку класса. В этом описано, как создать консольный проект, который включает поддержку C# 8.0 и создает точку входа `async main`.

В окне терминала перейдите к папке _working\templates_ и создайте вложенную папку с именем _consoleasync_. Откройте созданную папку и выполните команду `dotnet new console`, чтобы создать стандартное консольное приложение. Чтобы создать новый шаблон, созданные им файлы нужно изменить.

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a>Изменение файла program.cs

Откройте файл _program.cs_. Консольный проект не использует асинхронную точку входа, поэтому мы добавим ее. Измените код на приведенный ниже и сохраните файл.

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a>Изменение файла consoleasync.csproj

Мы изменим версию языка C#, которую использует проект, на 8.0. Отредактируйте файл _consoleasync.csproj_ и добавьте параметр `<LangVersion>` для узла `<PropertyGroup>`.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a>Построение проекта

Перед завершением работы с шаблоном проекта протестируйте его, чтобы проверить правильность компиляции и выполнения.

В терминале выполните приведенную ниже команду.

```dotnetcli
dotnet run
```

Вы получите приведенные ниже выходные данные.

```console
Hello World with C# 8.0!
```

Вы можете удалить папки _obj_ и _bin_, созданные после запуска команды `dotnet run`. Удаление этих файлов гарантирует, что шаблон будет включать только те файлы, которые связаны с шаблоном (без файлов, созданных в результате сборки).

Теперь, когда вы создали содержимое шаблона, необходимо создать файл конфигурации шаблона в его корневой папке.

## <a name="create-the-template-config"></a>Создание конфигурации шаблона

Шаблоны распознаются в .NET Core по специальной папке и файлу конфигурации, которые находятся в корневой папке шаблона. В нашем случае папка шаблона имеет такое расположение: _working\templates\consoleasync_.

При создании шаблона все файлы и папки в этой папке включаются как его часть, кроме специальной папки конфигурации. Эта папка конфигурации имеет имя _.template.config_.

Сначала создайте вложенную папку с именем _.template.config_ и откройте ее. Затем создайте файл с именем _template.json_. Структура папки должна быть такой, как указано ниже.

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

Откройте файл _template.json_ в любом текстовом редакторе, вставьте приведенный ниже код JSON и сохраните его.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

Этот файл конфигурации содержит все параметры шаблона. Вы можете увидеть основные параметры, например `name` и `shortName`, но в нем также присутствует параметр `tags/type` со значением `project`. Он указывает на то, что ваш шаблон является шаблоном проекта. Вы можете создать шаблон любого типа. Значения `item` и `project` — это общие рекомендуемые имена .NET Core, которые позволяют без усилий фильтровать типы шаблонов при поиске.

Элемент `classifications` представляет столбец **tags**, который отображается после запуска команды `dotnet new` и получения списка шаблонов. Пользователи также могут выполнять поиск по тегам классификации. Не путайте свойство `tags` в JSON-файле со списком тегов `classifications`. Это два разных элемента, которые, к сожалению, имеют одинаковые имена. Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template). Дополнительные сведения о файле *template.json* см. на [вики-сайте о шаблонах dotnet](https://github.com/dotnet/templating/wiki).

Теперь, когда у вас есть допустимый файл _.template.config/template.json_, вы можете установить шаблон. Перед установкой шаблона убедитесь, что вы удалили все лишние файлы и папки, которые не должны включаться в шаблон, например папки _bin_ или _obj_. В окне терминала перейдите к папке _consoleasync_ и выполните команду `dotnet new -i .\`, чтобы установить шаблон, расположенный в текущей папке. Если вы используете операционную систему Linux или macOS, используйте косую черту: `dotnet new -i ./`.

Эта команда выводит список установленных шаблонов, в числе которых должен быть и ваш шаблон.

```dotnetcli
dotnet new -i .\
```

Вы получите результат, аналогичный приведенному ниже.

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a>Тестирование шаблона проекта

Теперь, когда вы установили шаблон элемента, протестируйте его.

1. Перейдите в папку _теста_.

1. Создайте консольное приложение с помощью приведенной ниже команды, которая позволяет создать рабочий проект, который можно без труда протестировать, используя команду `dotnet run`.

    ```dotnetcli
    dotnet new consoleasync
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. Запустите проект с помощью приведенной ниже команды.

    ```dotnetcli
    dotnet run
    ```

    Вы получите приведенные ниже выходные данные.

    ```console
    Hello World with C# 8.0!
    ```

Поздравляем! Вы создали и развернули шаблон проекта с помощью .NET Core. Для подготовки к следующей части этой серии руководств вам необходимо удалить созданный шаблон. Также обязательно удалите все файлы из папки _test_. Так вы воссоздадите первоначальные условия для работы со следующим разделом этого руководства.

### <a name="uninstall-the-template"></a>Удаление шаблона

Так как вы установили шаблон с указанием пути к файлу, вам нужно удалить его, указав **абсолютный** путь к файлу. Вы можете просмотреть список всех установленных шаблонов, выполнив команду `dotnet new -u`. Ваш шаблон должен быть последним в списке. Удалите шаблон с помощью команды `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`, указав путь к нему.

```dotnetcli
dotnet new -u
```

Вы получите результат, аналогичный приведенному ниже.

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

Чтобы удалить шаблон, выполните указанную ниже команду.

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a>Следующие шаги

В рамках этого руководства вы создали шаблон проекта. Чтобы узнать, как создать простой в использовании пакетный файл с элементом и шаблонами проектов, перейдите к следующей части этой серии.

> [!div class="nextstepaction"]
> [Создание пакета шаблонов](cli-templates-create-template-pack.md)
