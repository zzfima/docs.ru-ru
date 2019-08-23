---
title: Элемент <clear> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d5da531bff3a0e9e198ba9b5ab6cf2b52bf36b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921312"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="49ef9-102">\<Очистка элемента > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="49ef9-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="49ef9-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="49ef9-103">Clears custom application settings.</span></span>

<span data-ttu-id="49ef9-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="49ef9-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="49ef9-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="49ef9-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="49ef9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**</span><span class="sxs-lookup"><span data-stu-id="49ef9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="49ef9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49ef9-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="49ef9-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49ef9-108">Attributes</span></span>

<span data-ttu-id="49ef9-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="49ef9-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="49ef9-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="49ef9-110">Parent element</span></span>

|     | <span data-ttu-id="49ef9-111">Описание</span><span class="sxs-lookup"><span data-stu-id="49ef9-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="49ef9-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="49ef9-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="49ef9-113">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="49ef9-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="49ef9-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49ef9-114">Child elements</span></span>

<span data-ttu-id="49ef9-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="49ef9-115">None</span></span>

## <a name="example"></a><span data-ttu-id="49ef9-116">Пример</span><span class="sxs-lookup"><span data-stu-id="49ef9-116">Example</span></span>

<span data-ttu-id="49ef9-117">В следующем примере показано, как удалить настраиваемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="49ef9-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="49ef9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="49ef9-118">See also</span></span>

- [<span data-ttu-id="49ef9-119">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49ef9-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
