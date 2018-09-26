---
title: '&lt;Добавить&gt; элемент для &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bcdac76528e7a8b07b56b6fd1d827c3c8072c371
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081556"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="f82ec-102">\<Добавить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="f82ec-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="f82ec-103">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="f82ec-103">Adds a custom application setting.</span></span>

<span data-ttu-id="f82ec-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f82ec-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="f82ec-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="f82ec-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="f82ec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="f82ec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f82ec-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f82ec-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="f82ec-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f82ec-108">Attributes</span></span>

|           | <span data-ttu-id="f82ec-109">Описание</span><span class="sxs-lookup"><span data-stu-id="f82ec-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f82ec-110">**key**</span><span class="sxs-lookup"><span data-stu-id="f82ec-110">**key**</span></span>   | <span data-ttu-id="f82ec-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f82ec-111">Required attribute.</span></span><br><br><span data-ttu-id="f82ec-112">Указывает имя ключа.</span><span class="sxs-lookup"><span data-stu-id="f82ec-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="f82ec-113">**value**</span><span class="sxs-lookup"><span data-stu-id="f82ec-113">**value**</span></span> | <span data-ttu-id="f82ec-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="f82ec-114">Required attribute.</span></span><br><br><span data-ttu-id="f82ec-115">Указывает значение ключа.</span><span class="sxs-lookup"><span data-stu-id="f82ec-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f82ec-116">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f82ec-116">Parent element</span></span>

|     | <span data-ttu-id="f82ec-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f82ec-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f82ec-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="f82ec-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="f82ec-119">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="f82ec-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f82ec-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f82ec-120">Child elements</span></span>

<span data-ttu-id="f82ec-121">Нет</span><span class="sxs-lookup"><span data-stu-id="f82ec-121">None</span></span>

## <a name="example"></a><span data-ttu-id="f82ec-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f82ec-122">Example</span></span>

<span data-ttu-id="f82ec-123">Следующий пример показывает добавление настроек пользовательской конфигурации для имени приложения:</span><span class="sxs-lookup"><span data-stu-id="f82ec-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="f82ec-124">В следующем примере используется `<add>` для определения двух параметров совместимости в приложении ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="f82ec-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="f82ec-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f82ec-125">See also</span></span>

[<span data-ttu-id="f82ec-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f82ec-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
