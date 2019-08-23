---
title: Элемент <remove> для <appSettings>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 121b1c4b124ba07ff3bd312fd3832d3da592f486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921284"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="8f828-102">\<Удалите элемент > для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="8f828-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="8f828-103">Удаляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="8f828-103">Removes custom application settings.</span></span>

<span data-ttu-id="8f828-104">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8f828-104">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="8f828-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8f828-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="8f828-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="8f828-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8f828-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f828-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="8f828-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8f828-108">Attribute</span></span>

|         | <span data-ttu-id="8f828-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8f828-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="8f828-110">**key**</span><span class="sxs-lookup"><span data-stu-id="8f828-110">**key**</span></span> | <span data-ttu-id="8f828-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8f828-111">Required attribute.</span></span><br><br><span data-ttu-id="8f828-112">Задает имя удаляемого ключа.</span><span class="sxs-lookup"><span data-stu-id="8f828-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="8f828-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="8f828-113">Parent element</span></span>

|     | <span data-ttu-id="8f828-114">Описание</span><span class="sxs-lookup"><span data-stu-id="8f828-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8f828-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="8f828-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="8f828-116">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="8f828-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8f828-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f828-117">Child elements</span></span>

<span data-ttu-id="8f828-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8f828-118">None</span></span>

## <a name="example"></a><span data-ttu-id="8f828-119">Пример</span><span class="sxs-lookup"><span data-stu-id="8f828-119">Example</span></span>

<span data-ttu-id="8f828-120">В следующем примере показано, как удалить настраиваемый параметр конфигурации для `ApplicationName`:</span><span class="sxs-lookup"><span data-stu-id="8f828-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="8f828-121">См. также</span><span class="sxs-lookup"><span data-stu-id="8f828-121">See also</span></span>

- [<span data-ttu-id="8f828-122">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8f828-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
