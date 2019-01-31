---
title: <remove> - элемент для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: cf9a34e47b70aaff12b29b9c5cf944d5bb15fee9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258725"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="2b867-102">\<Удалить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="2b867-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="2b867-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="2b867-103">Removes custom application settings.</span></span>

<span data-ttu-id="2b867-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2b867-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2b867-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2b867-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="2b867-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="2b867-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2b867-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b867-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="2b867-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2b867-108">Attribute</span></span>

|         | <span data-ttu-id="2b867-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="2b867-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="2b867-110">**key**</span><span class="sxs-lookup"><span data-stu-id="2b867-110">**key**</span></span> | <span data-ttu-id="2b867-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2b867-111">Required attribute.</span></span><br><br><span data-ttu-id="2b867-112">Указывает имя ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="2b867-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="2b867-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="2b867-113">Parent element</span></span>

|     | <span data-ttu-id="2b867-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="2b867-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2b867-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="2b867-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="2b867-116">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="2b867-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2b867-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b867-117">Child elements</span></span>

<span data-ttu-id="2b867-118">Нет</span><span class="sxs-lookup"><span data-stu-id="2b867-118">None</span></span>

## <a name="example"></a><span data-ttu-id="2b867-119">Пример</span><span class="sxs-lookup"><span data-stu-id="2b867-119">Example</span></span>

<span data-ttu-id="2b867-120">В следующем примере показан способ удаления настроек пользовательской конфигурации для `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="2b867-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="2b867-121">См. также</span><span class="sxs-lookup"><span data-stu-id="2b867-121">See also</span></span>

- [<span data-ttu-id="2b867-122">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2b867-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
