---
title: <appSettings> - элемент для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289592"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="22bc9-102">\<appSettings > элемент для \<configuration ></span><span class="sxs-lookup"><span data-stu-id="22bc9-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="22bc9-103">Содержит пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-103">Contains custom application settings.</span></span> <span data-ttu-id="22bc9-104">Это раздел стандартные конфигурации, предоставляемые платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22bc9-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="22bc9-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="22bc9-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="22bc9-106">&nbsp;&nbsp;**\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="22bc9-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="22bc9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22bc9-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="22bc9-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22bc9-108">Attribute</span></span>

|           | <span data-ttu-id="22bc9-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="22bc9-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="22bc9-110">**file**</span><span class="sxs-lookup"><span data-stu-id="22bc9-110">**file**</span></span>  | <span data-ttu-id="22bc9-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="22bc9-111">Optional attribute.</span></span><br><br><span data-ttu-id="22bc9-112">Указывает относительный путь во внешний файл, содержащий пользовательские параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="22bc9-113">Указанный файл содержит одинаковые параметры, заданные в **\<Добавить >** , **\<удалить >** , и **\<снимите >** элементы и использует формата одной пары ключ/значение, что и эти элементы.</span><span class="sxs-lookup"><span data-stu-id="22bc9-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="22bc9-114">Указанный путь задается относительно основной файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="22bc9-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="22bc9-115">Для приложения Windows Forms, это двоичного папка (например, */bin/debug*), не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="22bc9-116">Для приложений Web Forms, этот путь задается относительно корневого каталога приложения, где *web.config* он находится.</span><span class="sxs-lookup"><span data-stu-id="22bc9-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="22bc9-117">Обратите внимание на то, что среда выполнения игнорирует атрибут, если не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="22bc9-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="22bc9-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="22bc9-118">Parent element</span></span>

|     | <span data-ttu-id="22bc9-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="22bc9-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="22bc9-120">**\<Конфигурация >** элемент</span><span class="sxs-lookup"><span data-stu-id="22bc9-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="22bc9-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22bc9-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="22bc9-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22bc9-122">Child elements</span></span>

|     | <span data-ttu-id="22bc9-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="22bc9-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="22bc9-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="22bc9-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="22bc9-125">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="22bc9-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="22bc9-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="22bc9-127">Удаляет все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="22bc9-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="22bc9-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="22bc9-129">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="22bc9-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="22bc9-130">Remarks</span></span>

<span data-ttu-id="22bc9-131">**\<AppSettings >** элемент сохраняет сведения о конфигурации пользовательского приложения, например строки подключения к базам данных, пути к файлам, URL-адреса XML-веб-служб или любые другие сведения о пользовательской конфигурации приложение.</span><span class="sxs-lookup"><span data-stu-id="22bc9-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="22bc9-132">Пары ключ/значение, указанное в  **\<appSettings >** доступ к элементу в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="22bc9-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="22bc9-133">Можно использовать **файл** атрибут в  **\<appSettings >** элемент *Web.config* и файлах конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="22bc9-134">Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в  **\<appSettings >** элемент.</span><span class="sxs-lookup"><span data-stu-id="22bc9-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="22bc9-135">**Файл** атрибут может использоваться в сценариев управления версиями team development, например когда пользователь хочет переопределить параметры проекта, указанный в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="22bc9-136">Файлы конфигурации, заданные **файл** атрибут должен иметь корневой узел **\<appSettings >** вместо **\<конфигурации >**.</span><span class="sxs-lookup"><span data-stu-id="22bc9-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="22bc9-137">Пример</span><span class="sxs-lookup"><span data-stu-id="22bc9-137">Example</span></span>

<span data-ttu-id="22bc9-138">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="22bc9-139">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="22bc9-140">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="22bc9-140">Configuration file</span></span>

<span data-ttu-id="22bc9-141">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="22bc9-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="22bc9-142">См. также</span><span class="sxs-lookup"><span data-stu-id="22bc9-142">See also</span></span>

- [<span data-ttu-id="22bc9-143">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="22bc9-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
