---
title: Элемент <clear> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3e1c3a3cfd61a9fa8e7abdae9a25ec1bc674492
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119230"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="51413-102">\<очистить элемент > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="51413-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="51413-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="51413-103">Clears custom application settings.</span></span>

<span data-ttu-id="51413-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="51413-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="51413-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="51413-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="51413-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="51413-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="51413-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51413-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="51413-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51413-108">Attributes</span></span>

<span data-ttu-id="51413-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="51413-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="51413-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="51413-110">Parent element</span></span>

|     | <span data-ttu-id="51413-111">Описание</span><span class="sxs-lookup"><span data-stu-id="51413-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="51413-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="51413-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="51413-113">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="51413-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="51413-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51413-114">Child elements</span></span>

<span data-ttu-id="51413-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="51413-115">None</span></span>

## <a name="example"></a><span data-ttu-id="51413-116">Пример</span><span class="sxs-lookup"><span data-stu-id="51413-116">Example</span></span>

<span data-ttu-id="51413-117">В следующем примере показано, как удалить настраиваемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="51413-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="51413-118">См. также</span><span class="sxs-lookup"><span data-stu-id="51413-118">See also</span></span>

- [<span data-ttu-id="51413-119">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="51413-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
