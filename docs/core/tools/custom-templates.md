---
title: Пользовательские шаблоны для команды dotnet new
description: Сведения о пользовательских шаблонах для проектов или файлов .NET любых типов.
author: guardrex
ms.date: 08/11/2017
ms.openlocfilehash: 23dac9f4efd64ff93b00e41b1f4195e964871a3e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503930"
---
# <a name="custom-templates-for-dotnet-new"></a>Пользовательские шаблоны для команды dotnet new

В состав [пакета SDK для .NET Core](https://www.microsoft.com/net/download/core) входит множество готовых шаблонов, предназначенных для использования с [командой `dotnet new`](dotnet-new.md). Начиная с версии .NET Core 2.0, можно создавать собственные шаблоны для проектов любого типа, например приложений, служб, средств или библиотек классов. Можно также создать шаблон, формирующий один или несколько отдельных файлов, например файл конфигурации.

Устанавливать пользовательские шаблоны из пакета NuGet можно в любом веб-канале NuGet, ссылаясь на файл *NUPKG* NuGet напрямую или указывая каталог в файловой системе, который содержит шаблон. Модуль шаблонов предоставляет возможности, которые позволяют заменять значения, включать и исключать файлы или области файлов, а также выполнять пользовательские операции обработки при использовании шаблона.

Модуль шаблонов имеет открытый код. Репозиторий кода в Интернете — [dotnet/templating](https://github.com/dotnet/templating/) в GitHub. Образцы шаблонов можно найти в репозитории [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples). Дополнительные шаблоны, в том числе шаблоны от сторонних разработчиков, можно найти на странице [Доступные шаблоны для dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) в GitHub. Дополнительные сведения о создании и использовании пользовательских шаблонов см. в записи блога [Создание собственных шаблонов для команды dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) и на [вики-сайте, посвященном репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki).

Пошаговое руководство по созданию шаблона см. в учебнике [Создание пользовательского шаблона для команды dotnet new](~/docs/core/tutorials/create-custom-template.md).

## <a name="configuration"></a>Конфигурация

Шаблон состоит из следующих компонентов:

- исходные файлы и папки;
- файл конфигурации (*template.json*).

### <a name="source-files-and-folders"></a>Исходные файлы и папки

К исходным файлам и папкам относятся все файлы и папки, которые должны использоваться модулем шаблонов при выполнении команды `dotnet new <TEMPLATE>`. Модуль шаблонов предполагает использование *запускаемых проектов* в качестве исходного кода для создания проектов. Это дает ряд преимуществ.

- Модуль шаблонов не требует внедрения специальных токенов в исходный код проекта.
- Файлы кода не являются особыми файлами и не требуют каких-либо изменений для работы с модулем шаблонов. Поэтому для работы с содержимым шаблонов можно использовать те же средства, которые вы обычно используете при работе с проектами.
- Сборка, выполнение и отладка проектов шаблонов осуществляется так же, как и в случае с любыми другими проектами.
- Вы можете быстро создать шаблон на основе существующего проекта, просто добавив файл конфигурации *template.json* в проект.

Файлы и папки, которые могут храниться в шаблоне, не ограничены формальными типами проектов .NET, такими как решения .NET Core или .NET Framework. Исходные файлы и папки могут включать в себя любое содержимое, которое требуется создавать при использовании шаблона, даже если модуль шаблонов создает только один файл в качестве выходного, например файл конфигурации или файл решения. Например, можно создать шаблон, который содержит исходный файл *web.config* и создает измененный файл *web.config* для проектов, в которых используется этот шаблон. Изменения в исходные файлы вносятся на основе логики и параметров, указанных в файле конфигурации *template.json*, а также значений, предоставляемых пользователем и передаваемых в качестве параметров в команду `dotnet new <TEMPLATE>`.

### <a name="templatejson"></a>template.json

Файл *template.json* размещается в папке *.template.config* в корневом каталоге шаблона. Он предоставляет сведения о конфигурации модулю шаблонов. В приведенной ниже таблице приведены элементы конфигурации, которые необходимы и достаточны для создания работающего шаблона.

| Член            | Тип          | Описание |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | Схема JSON для файла *template.json*. Редакторы, поддерживающие схемы JSON, обеспечивают возможности редактирования JSON при указании схемы. Например, в [Visual Studio Code](https://code.visualstudio.com/) требуется, чтобы этот элемент включал поддержку IntelliSense. Используйте значение `http://json.schemastore.org/template`. |
| `author`          | string        | Автор шаблона. |
| `classifications` | array(string) | Ноль или более характеристик шаблона, по которым пользователь может найти его. Если шаблон присутствует в списке шаблонов, созданных с помощью команды <code>dotnet new -l&#124;--list</code>, классификации также приводятся в столбце *Теги*. |
| `identity`        | string        | Уникальное имя шаблона. |
| `name`            | string        | Имя шаблона, которое видят пользователи. |
| `shortName`       | string        | Сокращение по умолчанию для выбора шаблона, которое используется во всех средах, где имя шаблона указывается пользователем, а не выбирается в графическом пользовательском интерфейсе. Например, короткое имя полезно при использовании шаблонов из командной строки с помощью команд CLI. |

#### <a name="example"></a>Пример

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

Полная схема файла *template.json* находится в [хранилище схем JSON](http://json.schemastore.org/template).

## <a name="net-default-templates"></a>Шаблоны .NET по умолчанию

При установке [пакета SDK для .NET Core](https://www.microsoft.com/net/download/core) вы получаете более десяти встроенных шаблонов для создания проектов и файлов, включая консольные приложения, библиотеки классов, проекты модульных тестов, приложения ASP.NET Core (в том числе проекты [Angular](https://angular.io/) и [React](https://facebook.github.io/react/)) и файлы конфигурации. Чтобы получить список встроенных шаблонов, выполните команду `dotnet new` с параметром `-l|--list`.

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>Упаковка шаблона в пакет NuGet (файл NUPKG)

В настоящее время пользовательский шаблон упаковывается в Windows с помощью [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe) (а не команды [dotnet pack](dotnet-pack.md)). Для кроссплатформенной упаковки рекомендуется использовать [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000).

Содержимое папки проекта вместе с файлом *.template.config/template.json* помещаются в папку *content*. Рядом с папкой *content* добавьте [файл *NUSPEC*](/nuget/create-packages/creating-a-package), который представляет собой XML-файл манифеста, описывающий содержимое пакета и управляющий процессом создания пакета NuGet. Внутри элемента **\<packageTypes>** в файле *NUSPEC* добавьте элемент **\<packageType>** с атрибутом `name`, имеющим значение `Template`. Папка *content* и файл *NUSPEC* должны находиться в одном каталоге. В таблице ниже приведен минимальный набор элементов файла *NUSPEC*, необходимых для создания шаблона как пакета NuGet.

| Элемент            | Тип   | Описание |
| ------------------ | ------ | ----------- |
| **\<authors>**     | string | Разделенный запятыми список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Авторы отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов. |
| **\<description>** | string | Подробное описание пакета для отображения пользовательского интерфейса. |
| **\<id>**          | string | Идентификатор пакета без учета регистра, который должен быть уникальным в пределах сайта nuget.org или иной коллекции, в которой будет находиться пакет. Идентификаторы не должны содержать пробелов или символов, которые недопустимы в URL-адресах, и в них должны соблюдаться общие правила касательно пространств имен .NET. Инструкции см. в разделе [Выбор уникального идентификатора пакета и задание номера версии](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number). |
| **\<packageType>** | string | Поместите этот элемент внутри элемента **\<packageTypes>** среди элементов **\<metadata>**. Присвойте атрибуту `name` элемента **\<packageType>** значение `Template`. |
| **\<version>**     | string | Версия пакета, указываемая согласно шаблону основной_номер.дополнительный_номер.исправление. Номер версии может включать в себя суффикс предварительной версии, как описано в разделе, посвященном [предварительным версиям](/nuget/create-packages/prerelease-packages#semantic-versioning). |

Полную схему файла *NUSPEC* см. в [справочнике по NUSPEC](/nuget/schema/nuspec). Пример файла *NUSPEC* для шаблона приведен в учебнике по [созданию пользовательского шаблона для команды dotnet new](~/docs/core/tutorials/create-custom-template.md).

[Создайте пакет](/nuget/create-packages/creating-a-package#creating-the-package) с помощью команды `nuget pack <PATH_TO_NUSPEC_FILE>`.

## <a name="installing-a-template"></a>Установка шаблона

Установите пользовательский шаблон из пакета NuGet в любом веб-канале NuGet, сославшись на файл *NUPKG* NuGet напрямую или указав каталог в файловой системе, который содержит конфигурацию шаблона. Используйте параметр `-i|--install` с командой [dotnet new](dotnet-new.md).

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Установка шаблона из пакета NuGet, хранящегося на сайте nuget.org

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>Установка шаблона из локального файла NUPKG

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>Установка шаблона из каталога в файловой системе

`FILE_SYSTEM_DIRECTORY` — это папка проекта, содержащая проект и папку *.template.config*.

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a>Удаление шаблона

Удалите пользовательский шаблон, сославшись на пакет NuGet по `id` или указав каталог в файловой системе, который содержит конфигурацию шаблона. Используйте параметр установки `-u|--uninstall` с командой [dotnet new](dotnet-new.md).

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Удаление шаблона из пакета NuGet, хранящегося на сайте nuget.org

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a>Удаление шаблона из локального файла NUPKG

Чтобы удалить шаблон, не пытайтесь использовать путь к файлу *NUPKG*. Попытка удалить шаблон с помощью команды `dotnet new -u <PATH_TO_NUPKG_FILE>` завершится сбоем. Ссылайтесь на пакет по `id`.

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a>Удаление шаблона из каталога в файловой системе

`FILE_SYSTEM_DIRECTORY` — это папка проекта, содержащая проект и папку *.template.config*. Нужно предоставить абсолютный путь. Попытка удалить шаблон с помощью команды относительного пути завершится сбоем. Дополнительные сведения см. в статье [dotnet new](dotnet-new.md).

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>Создание проекта с помощью пользовательского шаблона

После установки шаблона для его использования выполните команду `dotnet new <TEMPLATE>` так же, как и в случае с любым другим предустановленным шаблоном. Кроме того, можно указать [параметры](dotnet-new.md#options) для команды `dotnet new`, в том числе относящиеся к шаблону параметры, заданные в настройках шаблона. Укажите короткое имя шаблона непосредственно в команде.

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>См. также

- [Создание пользовательского шаблона для команды dotnet new (учебник)](../tutorials/create-custom-template.md)
- [Вики-сайт, посвященный репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki)
- [Репозиторий dotnet/dotnet-template-samples в GitHub](https://github.com/dotnet/dotnet-template-samples)
- [Создание собственных шаблонов для команды dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)
- [Схема *template.json* в хранилище схем JSON](http://json.schemastore.org/template)
