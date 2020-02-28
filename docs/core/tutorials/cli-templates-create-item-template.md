---
title: Создание шаблона элемента для dotnet new — .NET Core CLI
description: Из этой статьи вы узнаете, как создать шаблон элемента для команды dotnet new. Шаблоны элементов могут содержать любое число файлов.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5f4038e863d9bb59df470d3516c08fd2ad29c078
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503555"
---
# <a name="tutorial-create-an-item-template"></a>Учебник. Создание шаблона элемента

С помощью .NET Core вы можете создавать и развертывать шаблоны, которые генерируют проекты, файлы и даже ресурсы. Это руководство представляет собой первую часть серии, в которой описано, как создавать, устанавливать и удалять шаблоны для использования с командой `dotnet new`.

Из этой части вы узнаете, как выполнять такие задачи:

> [!div class="checklist"]
>
> * создание класса для шаблона элемента;
> * создание папки и файла конфигурации шаблона;
> * установка шаблона из файла;
> * тестирование шаблона элемента;
> * удаление шаблона элемента.

## <a name="prerequisites"></a>Предварительные требования

* [Пакет SDK для .NET Core 2.2](https://dotnet.microsoft.com/download) или более поздней версии.
* Ознакомьтесь со статьей справки [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md).

  В ней приведены общие сведения о шаблонах и о способах их создания. Некоторые сведения будут повторены и здесь.

* Откройте терминал и перейдите к папке _working\templates_.

## <a name="create-the-required-folders"></a>Создание нужных папок

Для этой серии используется рабочая папка, в которой размещен источник шаблона, и тестовая папка для тестирования шаблонов. Рабочая папка и тестовая папка должны находиться в одной родительской папке.

Сначала создайте родительскую папку (имя не имеет значения). Затем создайте вложенную папку с именем _working_. В папке _working_ создайте вложенную папку с именем _templates_.

Затем в родительской папке создайте папку с именем _test_. Структура папок должна выглядеть так, как показано ниже.

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a>Создание шаблона элемента

Шаблон элемента — это шаблон определенного типа, который содержит один или несколько файлов. Шаблоны такого типа полезны, если вам нужно создать определенный объект, например файл конфигурации, кода или решения. В этом примере описано, как создать класс, который добавляет метод расширения в строковый тип.

В окне терминала перейдите к папке _working\templates_ и создайте вложенную папку с именем _extensions_. Войдите в папку.

```console
working
└───templates
    └───extensions
```

Создайте файл с именем _CommonExtensions.cs_ и откройте его в текстовом редакторе. Этот класс предоставит метод расширения с именем `Reverse`, который изменяет порядок символов в строке на обратный. Вставьте приведенный ниже код и сохраните файл:

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

Теперь, когда вы создали содержимое шаблона, необходимо создать файл конфигурации шаблона в его корневой папке.

## <a name="create-the-template-config"></a>Создание конфигурации шаблона

Шаблоны распознаются в .NET Core по специальной папке и файлу конфигурации, которые находятся в корневой папке шаблона. В нашем случае папка шаблона имеет такое расположение: _working\templates\extensions_.

При создании шаблона все файлы и папки в этой папке включаются как его часть, кроме специальной папки конфигурации. Эта папка конфигурации имеет имя _.template.config_.

Сначала создайте вложенную папку с именем _.template.config_ и откройте ее. Затем создайте файл с именем _template.json_. Структура папки должна быть такой:

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

Откройте файл _template.json_ в любом текстовом редакторе, вставьте приведенный ниже код JSON и сохраните его.

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

Этот файл конфигурации содержит все параметры шаблона. Вы можете увидеть основные параметры, например `name` и `shortName`, но здесь также присутствует параметр `tags/type` со значением `item`. Он указывает, что ваш шаблон является шаблоном элемента. Вы можете создать шаблон любого типа. Значения `item` и `project` — это общие рекомендуемые имена .NET Core, которые позволяют без усилий фильтровать типы шаблонов при поиске.

Элемент `classifications` представляет столбец **tags**, который отображается после запуска команды `dotnet new` и получения списка шаблонов. Пользователи также могут выполнять поиск по тегам классификации. Не спутайте свойство `tags` в файле \*.json со списком тегов `classifications`. Это два разных элемента, которые, к сожалению, имеют одинаковые имена. Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template). Дополнительные сведения о файле *template.json* см. на [вики-сайте о шаблонах dotnet](https://github.com/dotnet/templating/wiki).

Теперь, когда у вас есть допустимый файл _.template.config/template.json_, вы можете установить шаблон. В окне терминала перейдите к папке _extensions_ и выполните приведенную ниже команду, чтобы установить шаблон, расположенный в текущей папке:

* **В Windows**: `dotnet new -i .\`
* **В Linux или macOS**: `dotnet new -i ./`

Эта команда выводит список установленных шаблонов, в числе которых должен быть и ваш шаблон.

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a>Тестирование шаблона элемента

Теперь, когда вы установили шаблон элемента, протестируйте его. Перейдите к папке _test/_ и создайте консольное приложение с помощью команды `dotnet new console`. При этом будет создан рабочий проект, который вы можете с легкостью протестировать, выполнив команду `dotnet run`.

```dotnetcli
dotnet new console
```

Вы получите результат, аналогичный приведенному ниже.

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

Запустите проект с помощью следующей команды:

```dotnetcli
dotnet run
```

Вы получите приведенные ниже выходные данные.

```console
Hello World!
```

Затем выполните команду `dotnet new stringext`, чтобы создать файл _CommonExtensions.cs_ из шаблона.

```dotnetcli
dotnet new stringext
```

Вы получите приведенные ниже выходные данные.

```console
The template "Example templates: string extensions" was created successfully.
```

Измените код в файле _Program.cs_, чтобы поменять порядок символов в строке `"Hello World"` на обратный с помощью метода расширения, предоставляемого шаблоном.

```csharp
Console.WriteLine("Hello World!".Reverse());
```

Запустите программу еще раз, и вы увидите, что порядок символов изменен на обратный.

```dotnetcli
dotnet run
```

Вы получите приведенные ниже выходные данные.

```console
!dlroW olleH
```

Поздравляем! Вы создали и развернули шаблон элемента с помощью .NET Core. Для подготовки к следующей части этой серии руководств вам необходимо удалить созданный шаблон. Также обязательно удалите все файлы из папки _test_. Так вы воссоздадите первоначальные условия для работы со следующим разделом этого руководства.

## <a name="uninstall-the-template"></a>Удаление шаблона

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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

Чтобы удалить шаблон, выполните указанную ниже команду.

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a>Следующие шаги

С помощью этого руководства вы создали шаблон элемента. Чтобы узнать, как создать шаблон проекта, перейдите к следующей части этой серии.

> [!div class="nextstepaction"]
> [Создание шаблона проекта](cli-templates-create-project-template.md)
