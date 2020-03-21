---
title: Элемент <appSettings> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155535"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="03e71-102">\<элемент appSettings \<> для> конфигурации</span><span class="sxs-lookup"><span data-stu-id="03e71-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="03e71-103">Содержит настройки пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="03e71-103">Contains custom application settings.</span></span> <span data-ttu-id="03e71-104">Это предопределенный раздел конфигурации, предоставляемый рамочной системой .NET.</span><span class="sxs-lookup"><span data-stu-id="03e71-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="03e71-105">конфигурация &nbsp; &nbsp; [\*\* \<>\*\*](../configuration-element.md) \*\* \<appSettings>\*\*</span><span class="sxs-lookup"><span data-stu-id="03e71-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="03e71-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03e71-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="03e71-107">attribute</span><span class="sxs-lookup"><span data-stu-id="03e71-107">Attribute</span></span>

|           | <span data-ttu-id="03e71-108">Описание</span><span class="sxs-lookup"><span data-stu-id="03e71-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="03e71-109">**Файл**</span><span class="sxs-lookup"><span data-stu-id="03e71-109">**file**</span></span>  | <span data-ttu-id="03e71-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="03e71-110">Optional attribute.</span></span><br><br><span data-ttu-id="03e71-111">Определяет относительный путь к внешнему файлу, содержащему настройки конфигурации пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="03e71-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="03e71-112">Указанный файл содержит те же параметры, которые указаны \*\* \< \*\*в \*\* \<добавленной>, **удалить>и \*\* \<очистить>** элементы и использует тот же формат пары ключей/значений, что и эти элементы.</span><span class="sxs-lookup"><span data-stu-id="03e71-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="03e71-113">Указанный путь относительно основного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="03e71-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="03e71-114">Для приложения Windows Forms это двоичная папка (например, */bin/debug),* а не расположение файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="03e71-115">Для приложений Web Forms путь относительно корня приложения, где находится файл *web.config.*</span><span class="sxs-lookup"><span data-stu-id="03e71-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="03e71-116">Время выполнения игнорирует атрибут, если указанный файл не может быть найден.</span><span class="sxs-lookup"><span data-stu-id="03e71-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="03e71-117">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="03e71-117">Parent element</span></span>

|     | <span data-ttu-id="03e71-118">Описание</span><span class="sxs-lookup"><span data-stu-id="03e71-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03e71-119">\*\* \<конфигурация>\*\* Элемент</span><span class="sxs-lookup"><span data-stu-id="03e71-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="03e71-120">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03e71-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="03e71-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03e71-121">Child elements</span></span>

|     | <span data-ttu-id="03e71-122">Описание</span><span class="sxs-lookup"><span data-stu-id="03e71-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03e71-123">**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="03e71-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="03e71-124">Добавляет настройки пользовательского приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="03e71-125">**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="03e71-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="03e71-126">Очищает все ранее определенные параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="03e71-127">**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="03e71-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="03e71-128">Удаляет ранее определенный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="03e71-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="03e71-129">Remarks</span></span>

<span data-ttu-id="03e71-130">\*\* \<В appSettings>\*\* элемент хранит сярдругой информацию о конфигурации приложений, такую как строки соединения базы данных, пути файлов, URL-адреса веб-службы XML или любую другую информацию о пользовательской конфигурации для приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="03e71-131">Пары ключей/значений, указанные в \*\* \<appSettings>\*\* элемент, доступны в коде с помощью <xref:System.Configuration.ConfigurationSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="03e71-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="03e71-132">Атрибут **файла** можно использовать в \*\* \<appSettings>\*\* элементфайлов *конфигурации Web.config* и приложений.</span><span class="sxs-lookup"><span data-stu-id="03e71-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="03e71-133">Этот атрибут определяет файл конфигурации, который предоставляет дополнительные настройки или переопределяет параметры, указанные в \*\* \<элементе appSettings>.\*\*</span><span class="sxs-lookup"><span data-stu-id="03e71-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="03e71-134">Атрибут **файла** может использоваться в сценариях разработки группы управления исходным управлением, например, когда пользователь хочет переопределить параметры проекта, указанные в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="03e71-135">Файлы конфигурации, указанные атрибутом **файла,** должны иметь корневой узел \*\* \<appSettings>,\*\* а \*\* \<не конфигурацию>. \*\*</span><span class="sxs-lookup"><span data-stu-id="03e71-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="03e71-136">Пример</span><span class="sxs-lookup"><span data-stu-id="03e71-136">Example</span></span>

<span data-ttu-id="03e71-137">В приведенном ниже примере показан внешний файл параметров приложения (*custom.config*), в котором определен пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="03e71-138">В приведенном ниже примере показан файл конфигурации приложения, в котором используется параметр из внешнего файла параметров и задается собственный параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="03e71-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="03e71-139">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="03e71-139">Configuration file</span></span>

<span data-ttu-id="03e71-140">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="03e71-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="03e71-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="03e71-141">See also</span></span>

- [<span data-ttu-id="03e71-142">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="03e71-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
