---
title: "&lt;Очистить&gt; элемент для &lt;appSettings&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54479cab9abc2c1a107cd055341404c0fe1308fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="6eae0-102">\<Очистить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="6eae0-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="6eae0-103">Очищает пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="6eae0-103">Clears custom application settings.</span></span>

<span data-ttu-id="6eae0-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6eae0-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6eae0-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6eae0-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="6eae0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Очистить >**</span><span class="sxs-lookup"><span data-stu-id="6eae0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6eae0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6eae0-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="6eae0-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6eae0-108">Attributes</span></span>

<span data-ttu-id="6eae0-109">Нет</span><span class="sxs-lookup"><span data-stu-id="6eae0-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="6eae0-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="6eae0-110">Parent element</span></span>

|     | <span data-ttu-id="6eae0-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="6eae0-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6eae0-112">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="6eae0-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="6eae0-113">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-службы или любые другие пользовательские данные конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="6eae0-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6eae0-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6eae0-114">Child elements</span></span>

<span data-ttu-id="6eae0-115">Нет</span><span class="sxs-lookup"><span data-stu-id="6eae0-115">None</span></span>

## <a name="example"></a><span data-ttu-id="6eae0-116">Пример</span><span class="sxs-lookup"><span data-stu-id="6eae0-116">Example</span></span>

<span data-ttu-id="6eae0-117">Приведенный ниже показано, как очистить настраиваемыми параметрами конфигурации:</span><span class="sxs-lookup"><span data-stu-id="6eae0-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="6eae0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6eae0-118">See also</span></span>

[<span data-ttu-id="6eae0-119">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6eae0-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
