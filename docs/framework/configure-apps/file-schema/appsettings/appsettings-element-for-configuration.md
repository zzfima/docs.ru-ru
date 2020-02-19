---
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: e1f285aae10a89fa49846534d5b47e15920294ea
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452283"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="669b1-102">\<appSettings > элемент для \<конфигурации ></span><span class="sxs-lookup"><span data-stu-id="669b1-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="669b1-103">Содержит пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-103">Contains custom application settings.</span></span> <span data-ttu-id="669b1-104">Это предварительно определенный раздел конфигурации, предоставляемый .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="669b1-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="669b1-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="669b1-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="669b1-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="669b1-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="669b1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="669b1-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="669b1-108">attribute</span><span class="sxs-lookup"><span data-stu-id="669b1-108">Attribute</span></span>

|           | <span data-ttu-id="669b1-109">Description</span><span class="sxs-lookup"><span data-stu-id="669b1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="669b1-110">**файл**</span><span class="sxs-lookup"><span data-stu-id="669b1-110">**file**</span></span>  | <span data-ttu-id="669b1-111">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="669b1-111">Optional attribute.</span></span><br><br><span data-ttu-id="669b1-112">Указывает относительный путь к внешнему файлу, содержащему настраиваемые параметры конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="669b1-113">Указанный файл содержит те же параметры, которые указаны в **\<добавить >** , **\<удалить >** и **\<очистить >** , и в качестве этих элементов использует один и тот же формат пар ключ-значение.</span><span class="sxs-lookup"><span data-stu-id="669b1-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="669b1-114">Путь указан относительно основного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="669b1-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="669b1-115">Для Windows Forms приложения это двоичная папка (например, */бин/дебуг*), а не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="669b1-116">Для приложений веб-форм путь определяется относительно корневого каталога приложения, где находится файл *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="669b1-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="669b1-117">Среда выполнения игнорирует атрибут, если не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="669b1-117">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="669b1-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="669b1-118">Parent element</span></span>

|     | <span data-ttu-id="669b1-119">Description</span><span class="sxs-lookup"><span data-stu-id="669b1-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="669b1-120"> **> конфигурации\<** Дерев</span><span class="sxs-lookup"><span data-stu-id="669b1-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="669b1-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="669b1-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="669b1-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="669b1-122">Child elements</span></span>

|     | <span data-ttu-id="669b1-123">Description</span><span class="sxs-lookup"><span data-stu-id="669b1-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="669b1-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="669b1-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="669b1-125">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="669b1-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="669b1-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="669b1-127">Удаляет все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="669b1-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="669b1-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="669b1-129">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="669b1-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="669b1-130">Remarks</span></span>

<span data-ttu-id="669b1-131">Элемент **\<appSettings >** сохраняет сведения о конфигурации пользовательского приложения, такие как строки подключения к базе данных, пути к файлам, URL-адреса XML или другие пользовательские сведения о конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="669b1-132">Пары "ключ-значение", указанные в элементе **\<appSettings >** , доступны в коде с помощью класса <xref:System.Configuration.ConfigurationSettings>.</span><span class="sxs-lookup"><span data-stu-id="669b1-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="669b1-133">Атрибут **File** можно использовать в элементе **\<appSettings >** в файлах *Web. config* и конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="669b1-134">Этот атрибут задает файл конфигурации, предоставляющий дополнительные параметры или переопределяющий параметры, указанные в элементе **\<appSettings >** .</span><span class="sxs-lookup"><span data-stu-id="669b1-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="669b1-135">Атрибут **File** может использоваться в сценариях разработки группы управления исходным кодом, например, когда пользователь хочет переопределить параметры проекта, указанные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="669b1-136">Файлы конфигурации, заданные атрибутом **File** , должны иметь корневой узел **\<appSettings >** , а не **\<> конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="669b1-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="669b1-137">Пример</span><span class="sxs-lookup"><span data-stu-id="669b1-137">Example</span></span>

<span data-ttu-id="669b1-138">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="669b1-139">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="669b1-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="669b1-140">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="669b1-140">Configuration file</span></span>

<span data-ttu-id="669b1-141">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="669b1-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="669b1-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="669b1-142">See also</span></span>

- [<span data-ttu-id="669b1-143">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="669b1-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
