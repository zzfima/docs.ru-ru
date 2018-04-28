---
title: Создание пользовательского шаблона для команды dotnet new
description: В этом учебнике вы узнаете, как создать пользовательский шаблон для команды dotnet new.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9ff58634daa6d51c10df9a3c9a1af0fd6420c69c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="912a2-103">Создание пользовательского шаблона для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="912a2-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="912a2-104">В этом учебнике демонстрируется выполнение следующих действий:</span><span class="sxs-lookup"><span data-stu-id="912a2-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="912a2-105">создание базового шаблона на основе существующего проекта или нового проекта консольного приложения;</span><span class="sxs-lookup"><span data-stu-id="912a2-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="912a2-106">упаковка шаблона для распространения с сайта nuget.org или из локального файла *NUPKG*;</span><span class="sxs-lookup"><span data-stu-id="912a2-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="912a2-107">установка шаблона с сайта nuget.org, из локального файла *NUPKG* или из локальной файловой системы;</span><span class="sxs-lookup"><span data-stu-id="912a2-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="912a2-108">удаление шаблона.</span><span class="sxs-lookup"><span data-stu-id="912a2-108">Uninstall the template.</span></span>

<span data-ttu-id="912a2-109">Если при изучении руководства вы хотите использовать готовый пример, скачайте [его](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="912a2-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="912a2-110">Образец шаблона настроен для распространения посредством NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="912a2-111">Если вы хотите скачать образец и использовать распространение из файловой системы, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="912a2-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="912a2-112">Переместите содержимое папки *content* образца на один уровень вверх в папку *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="912a2-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="912a2-113">Удалите пустую папку *content*.</span><span class="sxs-lookup"><span data-stu-id="912a2-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="912a2-114">Удалите файл *NUSPEC*.</span><span class="sxs-lookup"><span data-stu-id="912a2-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="912a2-115">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="912a2-115">Prerequisites</span></span>

- <span data-ttu-id="912a2-116">Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/core) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="912a2-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="912a2-117">Ознакомьтесь со справочным разделом [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="912a2-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="912a2-118">Создание шаблона на основе проекта</span><span class="sxs-lookup"><span data-stu-id="912a2-118">Create a template from a project</span></span>

<span data-ttu-id="912a2-119">Используйте существующий проект, который компилируется и выполняется, или создайте проект консольного приложения в папке на жестком диске.</span><span class="sxs-lookup"><span data-stu-id="912a2-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="912a2-120">В этом руководстве предполагается, что папка проекта имеет имя *GarciaSoftware.ConsoleTemplate.CSharp* и хранится в каталоге *Documents\Templates* в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="912a2-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="912a2-121">Имя шаблона проекта в учебнике имеет формат *\<Название организации>.\<Тип шаблона>.\<Язык программирования>*, однако вы можете назвать проект и шаблон, как вам нравится.</span><span class="sxs-lookup"><span data-stu-id="912a2-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="912a2-122">Добавьте в корневой каталог проекта папку с именем *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="912a2-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="912a2-123">В папке *.template.config* создайте файл *template.json* для настройки шаблона.</span><span class="sxs-lookup"><span data-stu-id="912a2-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="912a2-124">Дополнительные сведения и определения элементов для файла *template.json* см. в статье [Пользовательские шаблоны для команды dotnet new](../tools/custom-templates.md#templatejson) и [схеме *template.json* в хранилище схем JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="912a2-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

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

<span data-ttu-id="912a2-125">Шаблон готов.</span><span class="sxs-lookup"><span data-stu-id="912a2-125">The template is finished.</span></span> <span data-ttu-id="912a2-126">На этом этапе возможны два варианта распространения шаблона.</span><span class="sxs-lookup"><span data-stu-id="912a2-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="912a2-127">Чтобы продолжить прохождение учебника, выберите один из них.</span><span class="sxs-lookup"><span data-stu-id="912a2-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="912a2-128">[Распространение посредством NuGet](#use-nuget-distribution): установите шаблон из пакета NuGet или из локального файла *NUPKG*, а затем используйте установленный шаблон.</span><span class="sxs-lookup"><span data-stu-id="912a2-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="912a2-129">[Распространение из файловой системы](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="912a2-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="912a2-130">Распространение посредством NuGet</span><span class="sxs-lookup"><span data-stu-id="912a2-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="912a2-131">Упаковка шаблона в пакет NuGet</span><span class="sxs-lookup"><span data-stu-id="912a2-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="912a2-132">Создайте папку для пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="912a2-133">В этом руководстве используется имя папки *GarciaSoftware.ConsoleTemplate.CSharp*. Папка создается в каталоге *Documents\NuGetTemplates* в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="912a2-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="912a2-134">В новой папке шаблона создайте папку *content*, в которой будут размещаться файлы проекта.</span><span class="sxs-lookup"><span data-stu-id="912a2-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="912a2-135">Скопируйте содержимое папки проекта вместе с файлом *.template.config/template.json* помещаются в созданную папку *content*.</span><span class="sxs-lookup"><span data-stu-id="912a2-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="912a2-136">Рядом с папкой *content* добавьте [файл *NUSPEC*](/nuget/create-packages/creating-a-package).</span><span class="sxs-lookup"><span data-stu-id="912a2-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="912a2-137">Файл NUSPEC представляет собой XML-файл манифеста, описывающий содержимое пакета и управляющий процессом создания пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![Структура каталогов пакета NuGet](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="912a2-139">Внутри элемента **\<packageTypes>** в файле *NUSPEC* добавьте элемент **\<packageType>** с атрибутом `name`, имеющим значение `Template`.</span><span class="sxs-lookup"><span data-stu-id="912a2-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="912a2-140">Папка *content* и файл *NUSPEC* должны находиться в одном каталоге.</span><span class="sxs-lookup"><span data-stu-id="912a2-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="912a2-141">В таблице ниже приведен минимальный набор элементов файла *NUSPEC*, необходимых для создания шаблона как пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="912a2-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="912a2-142">Element</span></span>            | <span data-ttu-id="912a2-143">Тип</span><span class="sxs-lookup"><span data-stu-id="912a2-143">Type</span></span>   | <span data-ttu-id="912a2-144">Описание:</span><span class="sxs-lookup"><span data-stu-id="912a2-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="912a2-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="912a2-145">**\<authors>**</span></span>     | <span data-ttu-id="912a2-146">string</span><span class="sxs-lookup"><span data-stu-id="912a2-146">string</span></span> | <span data-ttu-id="912a2-147">Разделенный запятыми список авторов пакетов, совпадающих с именами профилей на сайте nuget.org. Авторы отображаются в коллекции NuGet на сайте nuget.org и используются для перекрестных ссылок на пакеты тех же авторов.</span><span class="sxs-lookup"><span data-stu-id="912a2-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="912a2-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="912a2-148">**\<description>**</span></span> | <span data-ttu-id="912a2-149">string</span><span class="sxs-lookup"><span data-stu-id="912a2-149">string</span></span> | <span data-ttu-id="912a2-150">Подробное описание пакета для отображения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="912a2-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="912a2-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="912a2-151">**\<id>**</span></span>          | <span data-ttu-id="912a2-152">string</span><span class="sxs-lookup"><span data-stu-id="912a2-152">string</span></span> | <span data-ttu-id="912a2-153">Идентификатор пакета без учета регистра, который должен быть уникальным в пределах сайта nuget.org или иной коллекции, в которой будет находиться пакет.</span><span class="sxs-lookup"><span data-stu-id="912a2-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="912a2-154">Идентификаторы не должны содержать пробелов или символов, которые недопустимы в URL-адресах, и в них должны соблюдаться общие правила касательно пространств имен .NET.</span><span class="sxs-lookup"><span data-stu-id="912a2-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="912a2-155">Инструкции см. в разделе [Выбор уникального идентификатора пакета и задание номера версии](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number).</span><span class="sxs-lookup"><span data-stu-id="912a2-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="912a2-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="912a2-156">**\<packageType>**</span></span> | <span data-ttu-id="912a2-157">string</span><span class="sxs-lookup"><span data-stu-id="912a2-157">string</span></span> | <span data-ttu-id="912a2-158">Поместите этот элемент внутри элемента **\<packageTypes>** среди элементов **\<metadata>**.</span><span class="sxs-lookup"><span data-stu-id="912a2-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="912a2-159">Присвойте атрибуту `name` элемента **\<packageType>** значение `Template`.</span><span class="sxs-lookup"><span data-stu-id="912a2-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="912a2-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="912a2-160">**\<version>**</span></span>     | <span data-ttu-id="912a2-161">string</span><span class="sxs-lookup"><span data-stu-id="912a2-161">string</span></span> | <span data-ttu-id="912a2-162">Версия пакета, указываемая согласно шаблону основной_номер.дополнительный_номер.исправление.</span><span class="sxs-lookup"><span data-stu-id="912a2-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="912a2-163">Номер версии может включать в себя суффикс предварительной версии, как описано в разделе, посвященном [предварительным версиям](/nuget/create-packages/prerelease-packages#semantic-versioning).</span><span class="sxs-lookup"><span data-stu-id="912a2-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="912a2-164">Полную схему файла *NUSPEC* см. в [справочнике по NUSPEC](/nuget/schema/nuspec).</span><span class="sxs-lookup"><span data-stu-id="912a2-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="912a2-165">Файл *NUSPEC* для учебника называется *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* и имеет следующее содержимое:</span><span class="sxs-lookup"><span data-stu-id="912a2-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

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

1. <span data-ttu-id="912a2-166">[Создайте пакет](/nuget/create-packages/creating-a-package#creating-the-package) с помощью команды `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="912a2-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="912a2-167">В приведенной ниже команде предполагается, что папка, содержащая ресурсы NuGet, находится в каталоге *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="912a2-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="912a2-168">Однако где бы ни находилась эта папка в вашей системе, команда `nuget pack` принимает путь к файлу *NUSPEC*:</span><span class="sxs-lookup"><span data-stu-id="912a2-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="912a2-169">Публикация пакета на сайте nuget.org</span><span class="sxs-lookup"><span data-stu-id="912a2-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="912a2-170">Чтобы опубликовать пакет NuGet, выполните инструкции, приведенные в статье [Создание и публикация пакета](/nuget/quickstart/create-and-publish-a-package#publish-the-package).</span><span class="sxs-lookup"><span data-stu-id="912a2-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="912a2-171">Однако мы не рекомендуем публиковать шаблон из учебника в NuGet, так как после публикации его нельзя будет удалить. Вы сможете только удалить его из списка.</span><span class="sxs-lookup"><span data-stu-id="912a2-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="912a2-172">Теперь, когда имеется пакет NuGet в виде файла *NUPKG*, мы рекомендуем вам выполнить приведенные ниже инструкции, чтобы установить шаблон непосредственно из локального файла *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="912a2-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="912a2-173">Установка шаблона из пакета NuGet</span><span class="sxs-lookup"><span data-stu-id="912a2-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="912a2-174">Установка шаблона из локального файла *NUPKG*</span><span class="sxs-lookup"><span data-stu-id="912a2-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="912a2-175">Чтобы установить шаблон из созданного файла *NUPKG*, используйте команду `dotnet new` с параметром `-i|--install` и укажите путь к файлу *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="912a2-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="912a2-176">Установка шаблона из пакета NuGet, хранящегося на сайте nuget.org</span><span class="sxs-lookup"><span data-stu-id="912a2-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="912a2-177">Чтобы установить шаблон из пакета NuGet, хранящегося на сайте nuget.org, используйте команду `dotnet new` с параметром `-i|--install` и укажите имя пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="912a2-178">Этот пример приведен только в качестве демонстрации.</span><span class="sxs-lookup"><span data-stu-id="912a2-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="912a2-179">На сайте nuget.org нет пакета NuGet `GarciaSoftware.ConsoleTemplate.CSharp`, и мы не рекомендуем публиковать тестовые шаблоны и использовать их из NuGet.</span><span class="sxs-lookup"><span data-stu-id="912a2-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="912a2-180">При выполнении этой команды шаблон не устанавливается.</span><span class="sxs-lookup"><span data-stu-id="912a2-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="912a2-181">Однако вы можете установить шаблон, который не опубликован на сайте nuget.org, напрямую сославшись на файл *NUPKG* в локальной файловой системе, как описано в предыдущем разделе [Установка шаблона из локального файла NUPKG](#install-the-template-from-the-local-nupkg-file).</span><span class="sxs-lookup"><span data-stu-id="912a2-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="912a2-182">Чтобы ознакомиться с рабочим примером установки шаблона из пакета на сайте nuget.org, воспользуйтесь [шаблоном NUnit 3 для dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="912a2-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="912a2-183">Этот шаблон создает проект для использования модульного тестирования NUnit.</span><span class="sxs-lookup"><span data-stu-id="912a2-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="912a2-184">Для его установки используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="912a2-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="912a2-185">Если вывести список шаблонов с помощью команды `dotnet new -l`, в нем будет присутствовать элемент *NUnit 3 Test Project* с коротким именем *nunit*.</span><span class="sxs-lookup"><span data-stu-id="912a2-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="912a2-186">Шаблон готов к использованию в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="912a2-186">You're ready to use the template in the next section.</span></span>

![Окно консоли с шаблоном NUnit в списке установленных шаблонов](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="912a2-188">Создание проекта на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="912a2-188">Create a project from the template</span></span>

<span data-ttu-id="912a2-189">После установки шаблона из NuGet используйте его, выполнив команду `dotnet new <TEMPLATE>` из каталога, в котором должны размещаться выходные данные модуля шаблонов (если вы не применяете параметр `-o|--output` для указания определенного каталога).</span><span class="sxs-lookup"><span data-stu-id="912a2-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="912a2-190">Дополнительные сведения см. в разделе [Параметры](~/docs/core/tools/dotnet-new.md#options) статьи, посвященной команде `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="912a2-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="912a2-191">Укажите короткое имя шаблона непосредственно в команде `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="912a2-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="912a2-192">Чтобы создать проект на основе шаблона NUnit, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="912a2-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="912a2-193">В консоли показано, что проект создан и что его пакеты восстановлены.</span><span class="sxs-lookup"><span data-stu-id="912a2-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="912a2-194">После выполнения команды проект готов к использованию.</span><span class="sxs-lookup"><span data-stu-id="912a2-194">After the command is run, the project is ready for use.</span></span>

![Окно консоли с выходными данными команды dotnet new, создающей проект NUnit и восстанавливающей зависимости проекта](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="912a2-196">Удаление шаблона из пакета NuGet, хранящегося на сайте nuget.org</span><span class="sxs-lookup"><span data-stu-id="912a2-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="912a2-197">Этот пример приведен только в качестве демонстрации.</span><span class="sxs-lookup"><span data-stu-id="912a2-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="912a2-198">На сайте nuget.org нет пакета NuGet `GarciaSoftware.ConsoleTemplate.CSharp`, и он не устанавливается с пакетом SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="912a2-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="912a2-199">При выполнении команды пакет или шаблон не удаляется и возникает следующее исключение:</span><span class="sxs-lookup"><span data-stu-id="912a2-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="912a2-200">Не удалось найти объект для удаления с именем GarciaSoftware.ConsoleTemplate.CSharp.</span><span class="sxs-lookup"><span data-stu-id="912a2-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="912a2-201">Если вы установили [шаблон NUnit 3 для dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) и хотите удалить его, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="912a2-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="912a2-202">Удаление шаблона из локального файла NUPKG</span><span class="sxs-lookup"><span data-stu-id="912a2-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="912a2-203">Если необходимо удалить шаблон, не пытайтесь использовать путь к файлу *NUPKG*.</span><span class="sxs-lookup"><span data-stu-id="912a2-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="912a2-204">*Попытка удалить шаблон с помощью команды `dotnet new -u <PATH_TO_NUPKG_FILE>` завершится сбоем.*</span><span class="sxs-lookup"><span data-stu-id="912a2-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="912a2-205">Ссылайтесь на пакет по `id`.</span><span class="sxs-lookup"><span data-stu-id="912a2-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="912a2-206">Распространение из файловой системы</span><span class="sxs-lookup"><span data-stu-id="912a2-206">Use file system distribution</span></span>

<span data-ttu-id="912a2-207">Для распространения шаблона поместите папку шаблона проекта в месте, которое доступно пользователям сети.</span><span class="sxs-lookup"><span data-stu-id="912a2-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="912a2-208">Используйте команду `dotnet new` с параметром `-i|--install` и укажите путь к папке шаблона (папке проекта, содержащей проект и папку *.template.config*).</span><span class="sxs-lookup"><span data-stu-id="912a2-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="912a2-209">В этом учебнике предполагается, что шаблон проекта находится в папке *Documents/Templates* в профиле пользователя.</span><span class="sxs-lookup"><span data-stu-id="912a2-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="912a2-210">Установите шаблон из этого расположения с помощью следующей команды, заменив \<ПОЛЬЗОВАТЕЛЬ> на имя профиля пользователя:</span><span class="sxs-lookup"><span data-stu-id="912a2-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="912a2-211">Создание проекта на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="912a2-211">Create a project from the template</span></span>

<span data-ttu-id="912a2-212">После установки шаблона из файловой системы используйте его, выполнив команду `dotnet new <TEMPLATE>` из каталога, в котором должны размещаться выходные данные модуля шаблонов (если вы не применяете параметр `-o|--output` для указания определенного каталога).</span><span class="sxs-lookup"><span data-stu-id="912a2-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="912a2-213">Дополнительные сведения см. в разделе [Параметры](~/docs/core/tools/dotnet-new.md#options) статьи, посвященной команде `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="912a2-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="912a2-214">Укажите короткое имя шаблона непосредственно в команде `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="912a2-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="912a2-215">Из новой папки проекта, созданной в каталоге *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, создайте проект на основе шаблона `garciaconsole`:</span><span class="sxs-lookup"><span data-stu-id="912a2-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="912a2-216">Удаление шаблона</span><span class="sxs-lookup"><span data-stu-id="912a2-216">Uninstall the template</span></span>

<span data-ttu-id="912a2-217">Если вы создали шаблон в локальной файловой системе в каталоге *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, для его удаления укажите параметр `-u|--uninstall` и путь к папке шаблона:</span><span class="sxs-lookup"><span data-stu-id="912a2-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="912a2-218">Чтобы удалить шаблон из локальной файловой системы, вам необходимо указать полный путь.</span><span class="sxs-lookup"><span data-stu-id="912a2-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="912a2-219">Например, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* будет работать, а *./GarciaSoftware.ConsoleTemplate.CSharp* из содержащей папки — нет.</span><span class="sxs-lookup"><span data-stu-id="912a2-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="912a2-220">Кроме того, путь к шаблону не должен содержать конечную косую черту закрытия каталога.</span><span class="sxs-lookup"><span data-stu-id="912a2-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="912a2-221">См. также</span><span class="sxs-lookup"><span data-stu-id="912a2-221">See also</span></span>

[<span data-ttu-id="912a2-222">Вики-сайт, посвященный репозиторию dotnet/templating в GitHub</span><span class="sxs-lookup"><span data-stu-id="912a2-222">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
[<span data-ttu-id="912a2-223">Репозиторий dotnet/dotnet-template-samples в GitHub</span><span class="sxs-lookup"><span data-stu-id="912a2-223">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="912a2-224">Создание собственных шаблонов для команды dotnet new</span><span class="sxs-lookup"><span data-stu-id="912a2-224">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
[<span data-ttu-id="912a2-225">Схема *template.json* в хранилище схем JSON</span><span class="sxs-lookup"><span data-stu-id="912a2-225">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
