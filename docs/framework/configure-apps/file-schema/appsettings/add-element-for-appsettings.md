---
title: Элемент <add> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09864ea8f174d0c23f26db49f8cc0d43608522a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119339"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="27fea-102">\<добавить элемент > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="27fea-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="27fea-103">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="27fea-103">Adds a custom application setting.</span></span>

<span data-ttu-id="27fea-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="27fea-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="27fea-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="27fea-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="27fea-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="27fea-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="27fea-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27fea-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="27fea-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27fea-108">Attributes</span></span>

|           | <span data-ttu-id="27fea-109">Описание</span><span class="sxs-lookup"><span data-stu-id="27fea-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="27fea-110">**key**</span><span class="sxs-lookup"><span data-stu-id="27fea-110">**key**</span></span>   | <span data-ttu-id="27fea-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="27fea-111">Required attribute.</span></span><br><br><span data-ttu-id="27fea-112">Указывает имя добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="27fea-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="27fea-113">**value**</span><span class="sxs-lookup"><span data-stu-id="27fea-113">**value**</span></span> | <span data-ttu-id="27fea-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="27fea-114">Required attribute.</span></span><br><br><span data-ttu-id="27fea-115">Указывает значение добавляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="27fea-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="27fea-116">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="27fea-116">Parent element</span></span>

|     | <span data-ttu-id="27fea-117">Описание</span><span class="sxs-lookup"><span data-stu-id="27fea-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="27fea-118"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="27fea-118">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="27fea-119">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="27fea-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="27fea-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27fea-120">Child elements</span></span>

<span data-ttu-id="27fea-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="27fea-121">None</span></span>

## <a name="example"></a><span data-ttu-id="27fea-122">Пример</span><span class="sxs-lookup"><span data-stu-id="27fea-122">Example</span></span>

<span data-ttu-id="27fea-123">В следующем примере показано, как добавить настраиваемый параметр конфигурации для имени приложения:</span><span class="sxs-lookup"><span data-stu-id="27fea-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="27fea-124">В следующем примере элемент `<add>` используется для определения двух параметров совместимости в приложении ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="27fea-124">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="27fea-125">См. также</span><span class="sxs-lookup"><span data-stu-id="27fea-125">See also</span></span>

- [<span data-ttu-id="27fea-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="27fea-126">Configuration file schema for the .NET Framework</span></span>](../index.md)
