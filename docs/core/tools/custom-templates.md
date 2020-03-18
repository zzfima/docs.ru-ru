---
title: Пользовательские шаблоны для команды dotnet new
description: Сведения о пользовательских шаблонах для проектов или файлов .NET любых типов.
author: thraka
ms.date: 06/14/2019
ms.openlocfilehash: 8e1ac4ca21a8a90ad0f7c9bd3dd11281eb4a6e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73420883"
---
# <a name="custom-templates-for-dotnet-new"></a>Пользовательские шаблоны для команды dotnet new

В состав [пакета SDK для .NET Core](https://dotnet.microsoft.com/download) входит множество шаблонов, которые уже установлены и готовы к использованию. [Команда `dotnet new`](dotnet-new.md) позволяет не только использовать шаблоны, но и устанавливать и удалять их. Начиная с версии .NET Core 2.0, можно создавать собственные шаблоны для проектов любого типа, например приложений, служб, средств или библиотек классов. Можно также создать шаблон, формирующий один или несколько отдельных файлов, например файл конфигурации.

Устанавливать пользовательские шаблоны из пакета NuGet можно в любом веб-канале NuGet, указывая прямую ссылку на файл *NUPKG* для NuGet или каталог в файловой системе, который содержит нужный шаблон. Модуль шаблонов предоставляет возможности, которые позволяют заменять значения, включать и исключать файлы, а также выполнять пользовательские операции обработки при использовании шаблона.

Модуль шаблонов имеет открытый код. Репозиторий кода в Интернете — [dotnet/templating](https://github.com/dotnet/templating/) в GitHub. Образцы шаблонов можно найти в репозитории [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples). Дополнительные шаблоны, в том числе шаблоны от сторонних разработчиков, можно найти на странице [Доступные шаблоны для dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) в GitHub. Дополнительные сведения о создании и использовании пользовательских шаблонов см. в записи блога [Создание собственных шаблонов для команды dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) и на [вики-сайте, посвященном репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki).

Пошаговое руководство по созданию шаблона см. в учебнике [Создание пользовательского шаблона для команды dotnet new](../tutorials/cli-templates-create-item-template.md).

### <a name="net-default-templates"></a>Шаблоны .NET по умолчанию

При установке [пакета SDK для .NET Core](https://dotnet.microsoft.com/download) вы получаете более десяти встроенных шаблонов для создания проектов и файлов, включая консольные приложения, библиотеки классов, проекты модульных тестов, приложения ASP.NET Core (в том числе проекты [Angular](https://angular.io/) и [React](https://facebook.github.io/react/)) и файлы конфигурации. Чтобы получить список встроенных шаблонов, выполните команду `dotnet new` с параметром `-l|--list`.

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a>Конфигурация

Шаблон состоит из следующих частей:

- исходные файлы и папки;
- файл конфигурации (*template.json*).

### <a name="source-files-and-folders"></a>исходные файлы и папки;

К исходным файлам и папкам относятся все файлы и папки, которые должен использовать модуль шаблонов при выполнении команды `dotnet new <TEMPLATE>`. Модуль шаблонов предполагает использование *запускаемых проектов* в качестве исходного кода для создания проектов. Это дает ряд преимуществ.

- Модуль шаблонов не требует внедрения специальных токенов в исходный код проекта.
- Файлы кода не являются особыми файлами и не требуют каких-либо изменений для работы с модулем шаблонов. Поэтому для работы с содержимым шаблонов можно использовать те же средства, которые вы обычно используете при работе с проектами.
- Сборка, выполнение и отладка проектов шаблонов осуществляется так же, как и в случае с любыми другими проектами.
- Вы можете быстро создать шаблон на основе существующего проекта, просто добавив в проект файл конфигурации *./.template.config/template.json*.

Файлы и папки, которые могут храниться в шаблоне, не ограничены формальными типами проектов .NET. Исходные файлы и папки могут включать в себя любое содержимое, которое требуется создавать при использовании шаблона, даже если модуль шаблонов создает только один файл в качестве выходного.

Создаваемые шаблоном файлы можно изменять с помощью логики и параметров, которые предоставляются в файле конфигурации *template.json*. Пользователь может переопределять эти параметры, передавая их в команду `dotnet new <TEMPLATE>`. Типичный пример пользовательской логики — определение имени класса или переменной в файле кода, который развернут с помощью шаблона.

### <a name="templatejson"></a>template.json.

Файл *template.json* размещается в папке *.template.config* в корневом каталоге шаблона. Он предоставляет сведения о конфигурации модулю шаблонов. В приведенной ниже таблице приведены элементы конфигурации, которые необходимы и достаточны для создания работающего шаблона.

| Участник            | Type          | Описание: |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Схема JSON для файла *template.json*. Редакторы, поддерживающие схемы JSON, обеспечивают возможности редактирования JSON при указании схемы. Например, в [Visual Studio Code](https://code.visualstudio.com/) требуется, чтобы этот элемент включал поддержку IntelliSense. Используйте значение `http://json.schemastore.org/template`. |
| `author`          | string        | Автор шаблона. |
| `classifications` | array(string) | Ноль или более характеристик шаблона, по которым пользователь может найти его. Если шаблон присутствует в списке шаблонов, созданных с помощью команды *, классификации также приводятся в столбце* Теги`dotnet new -l|--list`. |
| `identity`        | string        | Уникальное имя шаблона. |
| `name`            | string        | Имя шаблона, которое видят пользователи. |
| `shortName`       | string        | Сокращенное имя по умолчанию для выбора шаблона, которое используется во всех средах, где имя шаблона указывается пользователем, а не выбирается в графическом пользовательском интерфейсе. Например, короткое имя полезно при использовании шаблонов из командной строки с помощью команд CLI. |

Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template). Дополнительные сведения о файле *template.json* см. на [вики-сайте о шаблонах dotnet](https://github.com/dotnet/templating/wiki).

#### <a name="example"></a>Пример

Например, следующая папка шаблонов включает два файла содержимого: *console.cs* и *readme.txt*. Обратите внимание, что существует обязательная папка с именем *. template.config* и файлом *template.json*.

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

Файл *template.json* выглядит примерно так:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

Папка *mytemplate* представляет собой устанавливаемый пакет шаблонов. После установки этого пакета вы сможете использовать `shortName` с помощью команды `dotnet new`. Например, `dotnet new adatumconsole` будет выводить файлы `console.cs` и `readme.txt` в текущую папку.

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Упаковка шаблона в пакет NuGet (файл NUPKG)

Пользовательский шаблон упаковывается с помощью команды [dotnet pack](dotnet-pack.md) и файла *.csproj*. Вместо этого можно применить [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) с помощью команды [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) и файла *.nuspec*. Но для работы NuGet требуется платформа .NET Framework в ОС Windows или [Mono](https://www.mono-project.com/) в ОС Linux и macOS.

Этот файл *.csproj* несколько отличается от традиционных файлов *.csproj* в проектах кода. Обратите внимание на следующие параметры.

01. Добавляется параметр `<PackageType>` со значением `Template`.
01. Добавляется параметр `<PackageVersion>` со значением допустимой [версии NuGet](/nuget/reference/package-versioning).
01. Добавляется параметр `<PackageId>` со значением уникального идентификатора. Этот идентификатор используется для удаления пакета шаблона, а также в веб-каналах NuGet для регистрации пакета шаблонов.
01. Нужно задать параметры для универсальных метаданных: `<Title>`, `<Authors>`, `<Description>` и `<PackageTags>`.
01. Нужно задать параметр `<TargetFramework>`, даже если не используется созданный процессом шаблона двоичный файл. В приведенном ниже примере он имеет значение `netstandard2.0`.

Пакет шаблонов в формате пакета NuGet *.nupkg* ожидает, что все шаблоны будут сохранены в папке *content* внутри пакета. Есть еще несколько параметров, которые нужно добавить в файл *.csproj*, чтобы созданный файл *.nupkg* можно было установить как пакет шаблонов:

01. Параметр `<IncludeContentInPack>` получает значение `true`, чтобы включить все файлы проекта, отмеченные в пакете NuGet как содержимое (**content**).
01. Параметр `<IncludeBuildOutput>` получает значение `false`, чтобы исключить все бинарные файлы, созданные компилятором из пакета NuGet.
01. Параметр `<ContentTargetFolders>` получает значение `content`. Это гарантирует, что указанные в качестве содержимого (**content**) файлы будут сохранены в папку *content* в пакете NuGet. Эта папка в пакете NuGet анализируется системой шаблонов dotnet.

Вы можете легко исключить все файлы кода из компиляции с проектом шаблона, указав элемент `<Compile Remove="**\*" />` в файле проекта, внутри элемента `<ItemGroup>`.

Чтобы структурировать пакет шаблонов, можно поместить все шаблоны в отдельные папки, а сами эти папки шаблонов — в папку *templates* в том же каталоге, где расположен файл *.csproj*. Это позволит вам использовать один элемент проекта для включения всех файлов и папок из папки *templates* в качестве содержимого (**content**). Внутри элемента `<ItemGroup>` создайте элемент `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.

Вот пример файла *.csproj*, созданного с соблюдением всех указанных выше рекомендаций. Он упаковывает дочернюю папку *templates* в папку пакета *content* и исключает из компиляции все файлы кода.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

В приведенном ниже примере показана структура файлов и папок, полученная при создании пакета шаблонов с помощью файла *.csproj*. Файл *MyDotnetTemplates.csproj* и папка *templates* размещаются в корневом каталоге с именем *project_folder*. Папка *templates* содержит два шаблона с именами *mytemplate1* и *mytemplate2*. Каждый шаблон включает файлы содержимого и папку *.template.config* с файлом конфигурации *template.json*.

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a>Установка шаблона

Чтобы установить пакет, выполните команду [dotnet new -i|--install](dotnet-new.md).

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Установка шаблона из пакета NuGet, хранящегося на сайте nuget.org

Для установки пакета шаблонов используйте идентификатор пакета NuGet.

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Установка шаблона из локального файла NUPKG

Укажите путь к файлу *.nupkg* пакета NuGet.

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Установка шаблона из каталога в файловой системе

Шаблоны можно установить из папки шаблонов, например из папки *mytemplate1* в приведенном выше примере. Укажите путь к папке *.template.config*. Не обязательно указывать абсолютный путь к каталогу шаблонов. Но для удаления шаблона, который был установлен из папки, требуется абсолютный путь.

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a>Получение списка установленных шаблонов

Команда удаления (uninstall) без дополнительных параметров возвращает полный список установленных шаблонов.

```dotnetcli
dotnet new -u
```

Эта команда возвращает примерно следующие выходные данные:

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

На первом уровне элементов под `Currently installed items:` расположены идентификаторы, используемые для удаления шаблонов. В представленном выше примере в список входят `Microsoft.DotNet.Common.ItemTemplates` и `Microsoft.DotNet.Common.ProjectTemplates.3.0`. Если шаблон был установлен через путь файловой системы, этот идентификатор совпадает с путем к папке *.template.config*.

## <a name="uninstalling-a-template"></a>Удаление шаблона

Чтобы установить пакет, выполните команду [dotnet new -u|--uninstall](dotnet-new.md).

Если пакет был установлен веб-каналом NuGet или напрямую из файла *.nupkg*, вам нужно предоставить идентификатор для него.

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

Если пакет был установлен указанием пути к папке *.template.config*, используйте тот же **абсолютный** путь для удаления пакета. Абсолютный путь к шаблону можно найти в выходных данных команды `dotnet new -u`. Дополнительные сведения см. выше в разделе [Получение списка установленных шаблонов](#get-a-list-of-installed-templates).

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Создание проекта с помощью пользовательского шаблона

После установки шаблона для его использования выполните команду `dotnet new <TEMPLATE>` так же, как и в случае с любым другим предустановленным шаблоном. Кроме того, можно указать [параметры](dotnet-new.md#options) для команды `dotnet new`, в том числе относящиеся к шаблону параметры, заданные в настройках шаблона. Укажите короткое имя шаблона непосредственно в команде.

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>См. также раздел

- [Создание пользовательского шаблона для команды dotnet new (учебник)](../tutorials/cli-templates-create-item-template.md)
- [Вики-сайт, посвященный репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki)
- [Репозиторий dotnet/dotnet-template-samples в GitHub](https://github.com/dotnet/dotnet-template-samples)
- [Создание собственных шаблонов для команды dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [Схема *template.json* в хранилище схем JSON](http://json.schemastore.org/template)
