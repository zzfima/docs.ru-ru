---
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: a64db49b521651ccff8b928720fe3273f8600b68
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921320"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="98db6-102">\<Элемент appSettings > для \<конфигурации ></span><span class="sxs-lookup"><span data-stu-id="98db6-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="98db6-103">Содержит пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-103">Contains custom application settings.</span></span> <span data-ttu-id="98db6-104">Это предварительно определенный раздел конфигурации, предоставляемый .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="98db6-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="98db6-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="98db6-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="98db6-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="98db6-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="98db6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98db6-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="98db6-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="98db6-108">Attribute</span></span>

|           | <span data-ttu-id="98db6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="98db6-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="98db6-110">**file**</span><span class="sxs-lookup"><span data-stu-id="98db6-110">**file**</span></span>  | <span data-ttu-id="98db6-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="98db6-111">Optional attribute.</span></span><br><br><span data-ttu-id="98db6-112">Указывает относительный путь к внешнему файлу, содержащему настраиваемые параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="98db6-113">Указанный файл содержит одинаковые параметры, заданные в **\<Добавить >** , **\<удалить >** , и **\<снимите >** элементы и использует формата одной пары ключ/значение, что и эти элементы.</span><span class="sxs-lookup"><span data-stu-id="98db6-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="98db6-114">Путь указан относительно основного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="98db6-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="98db6-115">Для Windows Forms приложения это двоичная папка (например, */бин/дебуг*), а не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="98db6-116">Для приложений веб-форм путь определяется относительно корневого каталога приложения, где находится файл *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="98db6-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="98db6-117">Обратите внимание, что среда выполнения игнорирует атрибут, если не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="98db6-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="98db6-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="98db6-118">Parent element</span></span>

|     | <span data-ttu-id="98db6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="98db6-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="98db6-120">элемент  **Configuration\<>** </span><span class="sxs-lookup"><span data-stu-id="98db6-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="98db6-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="98db6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="98db6-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="98db6-122">Child elements</span></span>

|     | <span data-ttu-id="98db6-123">Описание</span><span class="sxs-lookup"><span data-stu-id="98db6-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="98db6-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="98db6-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="98db6-125">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="98db6-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="98db6-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="98db6-127">Удаляет все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="98db6-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="98db6-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="98db6-129">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="98db6-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="98db6-130">Remarks</span></span>

<span data-ttu-id="98db6-131">**\<AppSettings >** элемент сохраняет сведения о конфигурации пользовательского приложения, например строки подключения к базам данных, пути к файлам, URL-адреса XML-веб-служб или любые другие сведения о пользовательской конфигурации приложение.</span><span class="sxs-lookup"><span data-stu-id="98db6-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="98db6-132">Пары "ключ-значение", указанные в <xref:System.Configuration.ConfigurationSettings>  **\<элементе appSettings >** , доступны в коде с помощью класса.</span><span class="sxs-lookup"><span data-stu-id="98db6-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="98db6-133">Атрибут **File** можно использовать в  **\<элементе appSettings >** файла конфигурации *Web. config* и приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="98db6-134">Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в  **\<элементе appSettings >** .</span><span class="sxs-lookup"><span data-stu-id="98db6-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="98db6-135">Атрибут **File** может использоваться в сценариях разработки группы управления исходным кодом, например, когда пользователь хочет переопределить параметры проекта, указанные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="98db6-136">Файлы конфигурации, заданные **файл** атрибут должен иметь корневой узел **\<appSettings >** вместо **\<конфигурации >** .</span><span class="sxs-lookup"><span data-stu-id="98db6-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="98db6-137">Пример</span><span class="sxs-lookup"><span data-stu-id="98db6-137">Example</span></span>

<span data-ttu-id="98db6-138">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="98db6-139">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="98db6-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="98db6-140">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="98db6-140">Configuration file</span></span>

<span data-ttu-id="98db6-141">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="98db6-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="98db6-142">См. также</span><span class="sxs-lookup"><span data-stu-id="98db6-142">See also</span></span>

- [<span data-ttu-id="98db6-143">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98db6-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
