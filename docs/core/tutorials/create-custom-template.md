---
title: Создание пользовательского шаблона для команды dotnet new
description: В этом учебнике вы узнаете, как создать пользовательский шаблон для команды dotnet new.
author: guardrex
ms.date: 08/12/2017
ms.custom: seodec18
ms.openlocfilehash: 63f8c8a4d029285a02255637c8a79358e5ef0095
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169740"
---
# <a name="create-a-custom-template-for-dotnet-new"></a>Создание пользовательского шаблона для команды dotnet new

В этом учебнике демонстрируется выполнение следующих действий:

- создание базового шаблона на основе существующего проекта или нового проекта консольного приложения;
- упаковка шаблона для распространения с сайта nuget.org или из локального файла *NUPKG*;
- установка шаблона с сайта nuget.org, из локального файла *NUPKG* или из локальной файловой системы;
- удаление шаблона.

Если при изучении руководства вы хотите использовать готовый пример, скачайте [его](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package). Образец шаблона настроен для распространения посредством NuGet.

Если вы хотите скачать образец и использовать распространение из файловой системы, выполните указанные ниже действия.

- Переместите содержимое папки *content* образца на один уровень вверх в папку *GarciaSoftware.ConsoleTemplate.CSharp*.
- Удалите пустую папку *content*.
- Удалите файл *NUSPEC*.

## <a name="prerequisites"></a>Предварительные требования

- Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/core) или более поздней версии.
- Ознакомьтесь со справочным разделом [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md).

## <a name="create-a-template-from-a-project"></a>Создание шаблона на основе проекта

Используйте существующий проект, который компилируется и выполняется, или создайте проект консольного приложения в папке на жестком диске. В этом руководстве предполагается, что папка проекта имеет имя *GarciaSoftware.ConsoleTemplate.CSharp* и хранится в каталоге *Documents\Templates* в профиле пользователя. Имя шаблона проекта в учебнике имеет формат *\<Название организации>.\<Тип шаблона>.\<Язык программирования>*, однако вы можете назвать проект и шаблон, как вам нравится.

1. Добавьте в корневой каталог проекта папку с именем *.template.config*.
1. В папке *.template.config* создайте файл *template.json* для настройки шаблона. Дополнительные сведения и определения элементов для файла *template.json* см. в статье [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md#templatejson) и [схеме *template.json* в хранилище схем JSON](http://json.schemastore.org/template).

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

Шаблон готов. На этом этапе возможны два варианта распространения шаблона. Чтобы продолжить прохождение учебника, выберите один из них.

1. [Распространение посредством NuGet](#use-nuget-distribution): установите шаблон из пакета NuGet или из локального файла *NUPKG*, а затем используйте установленный шаблон.
2. [Распространение из файловой системы](#use-file-system-distribution).

## <a name="use-nuget-distribution"></a>Распространение посредством NuGet

### <a name="pack-the-template-into-a-nuget-package"></a>Упаковка шаблона в пакет NuGet

1. Создайте папку для пакета NuGet. В этом руководстве используется имя папки *GarciaSoftware.ConsoleTemplate.CSharp*. Папка создается в каталоге *Documents\NuGetTemplates* в профиле пользователя. В новой папке шаблона создайте папку *content*, в которой будут размещаться файлы проекта.
1. Скопируйте содержимое папки проекта вместе с файлом *.template.config/template.json* помещаются в созданную папку *content*.
1. Рядом с папкой *content* добавьте [файл *NUSPEC*](/nuget/create-packages/creating-a-package). Файл NUSPEC представляет собой XML-файл манифеста, описывающий содержимое пакета и управляющий процессом создания пакета NuGet.

   ![Структура каталогов пакета NuGet](./media/create-custom-template/nuget-directory-layout.png)

1. Внутри элемента **\<packageTypes>** в файле *NUSPEC* добавьте элемент **\<packageType>** с атрибутом `name`, имеющим значение `Template`. Папка *content* и файл *NUSPEC* должны находиться в одном каталоге. В таблице ниже приведен минимальный набор элементов файла *NUSPEC*, необходимых для создания шаблона как пакета NuGet.

   | Элемент            | Тип   | Описание |
   | ------------------ | ------ | ----------- |
   | **\<authors>**     | string | Разделенный запятыми список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Авторы отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов. |
   | **\<description>** | string | Подробное описание пакета для отображения пользовательского интерфейса. |
   | **\<id>**          | string | Идентификатор пакета без учета регистра, который должен быть уникальным в пределах сайта nuget.org или иной коллекции, в которой будет находиться пакет. Идентификаторы не должны содержать пробелов или символов, которые недопустимы в URL-адресах, и в них должны соблюдаться общие правила касательно пространств имен .NET. Инструкции см. в разделе [Выбор уникального идентификатора пакета и задание номера версии](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number). |
   | **\<packageType>** | string | Поместите этот элемент внутри элемента **\<packageTypes>** среди элементов **\<metadata>**. Присвойте атрибуту `name` элемента **\<packageType>** значение `Template`. |
   | **\<version>**     | string | Версия пакета, указываемая согласно шаблону основной_номер.дополнительный_номер.исправление. Номер версии может включать в себя суффикс предварительной версии, как описано в разделе, посвященном [предварительным версиям](/nuget/create-packages/prerelease-packages#semantic-versioning). |

   Полную схему файла *NUSPEC* см. в [справочнике по NUSPEC](/nuget/schema/nuspec).

   Файл *NUSPEC* для учебника называется *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* и имеет следующее содержимое:

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. [Создайте пакет](/nuget/create-packages/creating-a-package#creating-the-package) с помощью команды `nuget pack <PATH_TO_NUSPEC_FILE>`. В приведенной ниже команде предполагается, что папка, содержащая ресурсы NuGet, находится в каталоге *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*. Однако где бы ни находилась эта папка в вашей системе, команда `nuget pack` принимает путь к файлу *NUSPEC*:

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a>Публикация пакета на сайте nuget.org

Чтобы опубликовать пакет NuGet, выполните инструкции, приведенные в статье [Создание и публикация пакета](/nuget/quickstart/create-and-publish-a-package#publish-the-package). Однако мы не рекомендуем публиковать шаблон из учебника в NuGet, так как после публикации его нельзя будет удалить. Вы сможете только удалить его из списка. Теперь, когда имеется пакет NuGet в виде файла *NUPKG*, мы рекомендуем вам выполнить приведенные ниже инструкции, чтобы установить шаблон непосредственно из локального файла *NUPKG*.

### <a name="install-the-template-from-a-nuget-package"></a>Установка шаблона из пакета NuGet

#### <a name="install-the-template-from-the-local-nupkg-file"></a>Установка шаблона из локального файла *NUPKG*

Чтобы установить шаблон из созданного файла *NUPKG*, используйте команду `dotnet new` с параметром `-i|--install` и укажите путь к файлу *NUPKG*.

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a>Установка шаблона из пакета NuGet, хранящегося на сайте nuget.org

Чтобы установить шаблон из пакета NuGet, хранящегося на сайте nuget.org, используйте команду `dotnet new` с параметром `-i|--install` и укажите имя пакета NuGet.

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Этот пример приведен только в качестве демонстрации. На сайте nuget.org нет пакета NuGet `GarciaSoftware.ConsoleTemplate.CSharp`, и мы не рекомендуем публиковать тестовые шаблоны и использовать их из NuGet. При выполнении этой команды шаблон не устанавливается. Однако вы можете установить шаблон, который не опубликован на сайте nuget.org, напрямую сославшись на файл *NUPKG* в локальной файловой системе, как описано в предыдущем разделе [Установка шаблона из локального файла NUPKG](#install-the-template-from-the-local-nupkg-file).

Чтобы ознакомиться с рабочим примером установки шаблона из пакета на сайте nuget.org, воспользуйтесь [шаблоном NUnit 3 для dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/). Этот шаблон создает проект для использования модульного тестирования NUnit. Для его установки используйте следующую команду:

```console
dotnet new -i NUnit3.DotNetNew.Template
```

Если вывести список шаблонов с помощью команды `dotnet new -l`, в нем будет присутствовать элемент *NUnit 3 Test Project* с коротким именем *nunit*. Шаблон готов к использованию в следующем разделе.

![Окно консоли с шаблоном NUnit и другими шаблонами](./media/create-custom-template/nunit-template-console-window.png)

### <a name="create-a-project-from-the-template"></a>Создание проекта на основе шаблона

После установки шаблона из NuGet используйте его, выполнив команду `dotnet new <TEMPLATE>` из каталога, в котором должны размещаться выходные данные модуля шаблонов (если вы не применяете параметр `-o|--output` для указания определенного каталога). Дополнительные сведения см. в разделе [Параметры](~/docs/core/tools/dotnet-new.md#options) статьи, посвященной команде `dotnet new`. Укажите короткое имя шаблона непосредственно в команде `dotnet new`. Чтобы создать проект на основе шаблона NUnit, выполните следующую команду:

```console
dotnet new nunit
```

В консоли показано, что проект создан и что его пакеты восстановлены. После выполнения команды проект готов к использованию.

![Окно консоли с результатом выполнения команды dotnet new nunit и восстановленными зависимостями проекта](./media/create-custom-template/dotnet-new-nunit-console-output.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>Удаление шаблона из пакета NuGet, хранящегося на сайте nuget.org

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Этот пример приведен только в качестве демонстрации. На сайте nuget.org нет пакета NuGet `GarciaSoftware.ConsoleTemplate.CSharp`, и он не устанавливается с пакетом SDK для .NET Core. При выполнении команды пакет или шаблон не удаляется и возникает следующее исключение:
>
> > Не удалось найти объект для удаления с именем GarciaSoftware.ConsoleTemplate.CSharp.

Если вы установили [шаблон NUnit 3 для dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) и хотите удалить его, используйте следующую команду:

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a>Удаление шаблона из локального файла NUPKG

Если необходимо удалить шаблон, не пытайтесь использовать путь к файлу *NUPKG*. *Попытка удалить шаблон с помощью команды `dotnet new -u <PATH_TO_NUPKG_FILE>` завершится сбоем.* Ссылайтесь на пакет по `id`.

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a>Распространение из файловой системы

Для распространения шаблона поместите папку шаблона проекта в месте, которое доступно пользователям сети. Используйте команду `dotnet new` с параметром `-i|--install` и укажите путь к папке шаблона (папке проекта, содержащей проект и папку *.template.config*).

В этом учебнике предполагается, что шаблон проекта находится в папке *Documents/Templates* в профиле пользователя. Установите шаблон из этого расположения с помощью следующей команды, заменив \<ПОЛЬЗОВАТЕЛЬ> на имя профиля пользователя:

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a>Создание проекта на основе шаблона

После установки шаблона из файловой системы используйте его, выполнив команду `dotnet new <TEMPLATE>` из каталога, в котором должны размещаться выходные данные модуля шаблонов (если вы не применяете параметр `-o|--output` для указания определенного каталога). Дополнительные сведения см. в разделе [Параметры](~/docs/core/tools/dotnet-new.md#options) статьи, посвященной команде `dotnet new`. Укажите короткое имя шаблона непосредственно в команде `dotnet new`.

Из новой папки проекта, созданной в каталоге *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, создайте проект на основе шаблона `garciaconsole`:

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a>Удаление шаблона

Если вы создали шаблон в локальной файловой системе в каталоге *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, для его удаления укажите параметр `-u|--uninstall` и путь к папке шаблона:

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> Чтобы удалить шаблон из локальной файловой системы, вам необходимо указать полный путь. Например, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* из содержащей папки — нет.
> Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.

## <a name="see-also"></a>См. также

* [Вики-сайт, посвященный репозиторию dotnet/templating в GitHub](https://github.com/dotnet/templating/wiki)  
* [Репозиторий dotnet/dotnet-template-samples в GitHub](https://github.com/dotnet/dotnet-template-samples)  
* [Создание собственных шаблонов для команды dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)
* [Схема *template.json* в хранилище схем JSON](http://json.schemastore.org/template)  
