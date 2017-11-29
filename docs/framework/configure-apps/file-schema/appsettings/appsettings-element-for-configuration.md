---
title: "&lt;appSettings&gt; элемент для &lt;конфигурации&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cb59120d88816ea193bd8588b152d6b848b682d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="59c48-102">\<appSettings > элемент для \<конфигурации ></span><span class="sxs-lookup"><span data-stu-id="59c48-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="59c48-103">Содержит пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-103">Contains custom application settings.</span></span> <span data-ttu-id="59c48-104">Это предопределенный раздел параметров конфигурации в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59c48-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="59c48-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="59c48-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="59c48-106">&nbsp;&nbsp;**\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="59c48-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="59c48-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59c48-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="59c48-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59c48-108">Attribute</span></span>

|           | <span data-ttu-id="59c48-109">Описание</span><span class="sxs-lookup"><span data-stu-id="59c48-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="59c48-110">**file**</span><span class="sxs-lookup"><span data-stu-id="59c48-110">**file**</span></span>  | <span data-ttu-id="59c48-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="59c48-111">Optional attribute.</span></span><br><br><span data-ttu-id="59c48-112">Указывает относительный путь к внешнему файлу, содержащему пользовательские параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="59c48-113">Указанный файл содержит одинаковые параметры, заданные в  **\<Добавить >**,  **\<удалить >**, и  **\<снимите >** элементы и использует ту же пару ключ значение формата как эти элементы.</span><span class="sxs-lookup"><span data-stu-id="59c48-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="59c48-114">Указанный путь задается относительно основной файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="59c48-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="59c48-115">Для приложения Windows Forms, это двоичный папку (например, */bin/debug*), не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="59c48-116">Для приложений Web Forms путь задается относительно корневой каталог приложения, где *web.config* находится файл.</span><span class="sxs-lookup"><span data-stu-id="59c48-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="59c48-117">Обратите внимание, что среда выполнения не учитывает атрибут, если не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="59c48-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="59c48-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="59c48-118">Parent element</span></span>

|     | <span data-ttu-id="59c48-119">Описание</span><span class="sxs-lookup"><span data-stu-id="59c48-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="59c48-120">**\<Конфигурация >** элемент</span><span class="sxs-lookup"><span data-stu-id="59c48-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="59c48-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59c48-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="59c48-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59c48-122">Child elements</span></span>

|     | <span data-ttu-id="59c48-123">Описание</span><span class="sxs-lookup"><span data-stu-id="59c48-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="59c48-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="59c48-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="59c48-125">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="59c48-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="59c48-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="59c48-127">Удаляет все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="59c48-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="59c48-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="59c48-129">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="59c48-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="59c48-130">Remarks</span></span>

<span data-ttu-id="59c48-131">**\<AppSettings >** элемент хранит пользовательские данные конфигурации приложения, например строки подключения базы данных, пути к файлам, URL-адреса XML-веб-службы или любые другие пользовательские сведения о конфигурации приложение.</span><span class="sxs-lookup"><span data-stu-id="59c48-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="59c48-132">Пары ключ значение, указанное в  **\<appSettings >** доступ к элементу в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="59c48-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="59c48-133">Можно использовать **файл** атрибута в  **\<appSettings >** элемент *Web.config* и файлов конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="59c48-134">Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяет параметры, указанные в  **\<appSettings >** элемента.</span><span class="sxs-lookup"><span data-stu-id="59c48-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="59c48-135">**Файл** атрибут может использоваться в исходном сценариях разработки группы управления, например, если пользователю необходимо переопределить параметры проекта, указанный в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="59c48-136">Файлы конфигурации, указанные по **файл** атрибут должен иметь корневой узел  **\<appSettings >** вместо  **\<конфигурации >**.</span><span class="sxs-lookup"><span data-stu-id="59c48-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="59c48-137">Пример</span><span class="sxs-lookup"><span data-stu-id="59c48-137">Example</span></span>

<span data-ttu-id="59c48-138">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="59c48-139">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="59c48-140">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="59c48-140">Configuration file</span></span>

<span data-ttu-id="59c48-141">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="59c48-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="59c48-142">См. также</span><span class="sxs-lookup"><span data-stu-id="59c48-142">See also</span></span>

[<span data-ttu-id="59c48-143">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="59c48-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
