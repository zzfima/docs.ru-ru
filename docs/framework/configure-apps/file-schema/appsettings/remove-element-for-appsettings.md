---
title: '&lt;Удалить&gt; элемент для &lt;appSettings&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: e9b79a8319b320289f43adac5a82ef22fa5e32b0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199699"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="239b9-102">\<Удалить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="239b9-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="239b9-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="239b9-103">Removes custom application settings.</span></span>

<span data-ttu-id="239b9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="239b9-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="239b9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="239b9-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="239b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="239b9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="239b9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="239b9-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="239b9-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="239b9-108">Attribute</span></span>

|         | <span data-ttu-id="239b9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="239b9-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="239b9-110">**key**</span><span class="sxs-lookup"><span data-stu-id="239b9-110">**key**</span></span> | <span data-ttu-id="239b9-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="239b9-111">Required attribute.</span></span><br><br><span data-ttu-id="239b9-112">Указывает имя ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="239b9-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="239b9-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="239b9-113">Parent element</span></span>

|     | <span data-ttu-id="239b9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="239b9-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="239b9-115">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="239b9-115">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="239b9-116">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="239b9-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="239b9-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="239b9-117">Child elements</span></span>

<span data-ttu-id="239b9-118">Нет</span><span class="sxs-lookup"><span data-stu-id="239b9-118">None</span></span>

## <a name="example"></a><span data-ttu-id="239b9-119">Пример</span><span class="sxs-lookup"><span data-stu-id="239b9-119">Example</span></span>

<span data-ttu-id="239b9-120">В следующем примере показан способ удаления настроек пользовательской конфигурации для `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="239b9-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="239b9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="239b9-121">See also</span></span>

- [<span data-ttu-id="239b9-122">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="239b9-122">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
