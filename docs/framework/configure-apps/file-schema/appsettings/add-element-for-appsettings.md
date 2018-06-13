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
ms.openlocfilehash: 35a9fc08033d2b9cd1dae5a1f1f3ddcd361f03eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753642"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="32a24-102">\<Добавить > элемент для \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="32a24-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="32a24-103">Добавляет пользовательский параметр приложения.</span><span class="sxs-lookup"><span data-stu-id="32a24-103">Adds a custom application setting.</span></span>

<span data-ttu-id="32a24-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="32a24-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="32a24-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="32a24-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="32a24-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="32a24-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="32a24-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32a24-107">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="32a24-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32a24-108">Attributes</span></span>

|           | <span data-ttu-id="32a24-109">Описание</span><span class="sxs-lookup"><span data-stu-id="32a24-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="32a24-110">**key**</span><span class="sxs-lookup"><span data-stu-id="32a24-110">**key**</span></span>   | <span data-ttu-id="32a24-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="32a24-111">Required attribute.</span></span><br><br><span data-ttu-id="32a24-112">Задает имя ключа.</span><span class="sxs-lookup"><span data-stu-id="32a24-112">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="32a24-113">**value**</span><span class="sxs-lookup"><span data-stu-id="32a24-113">**value**</span></span> | <span data-ttu-id="32a24-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="32a24-114">Required attribute.</span></span><br><br><span data-ttu-id="32a24-115">Указывает значение ключа.</span><span class="sxs-lookup"><span data-stu-id="32a24-115">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="32a24-116">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="32a24-116">Parent element</span></span>

|     | <span data-ttu-id="32a24-117">Описание</span><span class="sxs-lookup"><span data-stu-id="32a24-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="32a24-118">**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="32a24-118">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="32a24-119">Содержит пользовательские параметры приложения, такие как пути к файлам, URL-адреса XML-веб-служб и другие сведения о пользовательской конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="32a24-119">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="32a24-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32a24-120">Child elements</span></span>

<span data-ttu-id="32a24-121">Нет</span><span class="sxs-lookup"><span data-stu-id="32a24-121">None</span></span>

## <a name="example"></a><span data-ttu-id="32a24-122">Пример</span><span class="sxs-lookup"><span data-stu-id="32a24-122">Example</span></span>

<span data-ttu-id="32a24-123">Следующий пример демонстрирует добавление настроек пользовательской конфигурации для имени приложения:</span><span class="sxs-lookup"><span data-stu-id="32a24-123">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="32a24-124">См. также</span><span class="sxs-lookup"><span data-stu-id="32a24-124">See also</span></span>

[<span data-ttu-id="32a24-125">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="32a24-125">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
