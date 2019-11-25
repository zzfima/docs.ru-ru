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
ms.openlocfilehash: d321f3169344e9aa40d65b1722a533549de5315a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088739"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="bbd4c-102">\<очистить элемент > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="bbd4c-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="bbd4c-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="bbd4c-103">Clears custom application settings.</span></span>

<span data-ttu-id="bbd4c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bbd4c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bbd4c-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="bbd4c-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="bbd4c-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="bbd4c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="bbd4c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbd4c-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="bbd4c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bbd4c-108">Attributes</span></span>

<span data-ttu-id="bbd4c-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="bbd4c-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="bbd4c-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="bbd4c-110">Parent element</span></span>

|     | <span data-ttu-id="bbd4c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="bbd4c-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bbd4c-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="bbd4c-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="bbd4c-113">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML или другие сведения о конфигурации пользовательских приложений.</span><span class="sxs-lookup"><span data-stu-id="bbd4c-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bbd4c-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bbd4c-114">Child elements</span></span>

<span data-ttu-id="bbd4c-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="bbd4c-115">None</span></span>

## <a name="example"></a><span data-ttu-id="bbd4c-116">Пример</span><span class="sxs-lookup"><span data-stu-id="bbd4c-116">Example</span></span>

<span data-ttu-id="bbd4c-117">В следующем примере показано, как удалить настраиваемые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bbd4c-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="bbd4c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bbd4c-118">See also</span></span>

- [<span data-ttu-id="bbd4c-119">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bbd4c-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
