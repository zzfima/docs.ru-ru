---
title: Пользовательский элемент для SingleTagSectionHandler
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8ee722c7d5db9d58ab1a91f4b1299912981510af
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="6d376-102">Пользовательский элемент для SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="6d376-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="6d376-103">Определяет параметры настраиваемого раздела конфигурации, определяемый</span><span class="sxs-lookup"><span data-stu-id="6d376-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="6d376-104">элемент и использует <xref:System.Configuration.SingleTagSectionHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="6d376-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="6d376-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6d376-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6d376-106">&nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="6d376-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="6d376-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d376-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="6d376-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6d376-108">Attributes</span></span>

<span data-ttu-id="6d376-109">Атрибуты и значения атрибутов, определенные пользователем.</span><span class="sxs-lookup"><span data-stu-id="6d376-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="6d376-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="6d376-110">Parent element</span></span>

|     | <span data-ttu-id="6d376-111">Описание</span><span class="sxs-lookup"><span data-stu-id="6d376-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6d376-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="6d376-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="6d376-113">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d376-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6d376-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6d376-114">Child elements</span></span>

<span data-ttu-id="6d376-115">Нет</span><span class="sxs-lookup"><span data-stu-id="6d376-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6d376-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d376-116">Remarks</span></span>

<span data-ttu-id="6d376-117"> **\<SectionName >** элемент является пользовательским элементом определяется [  **\<раздел >** ](~/docs/framework/configure-apps/file-schema/section-element.md) тегом [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6d376-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="6d376-118">Система конфигурации возвращает <xref:System.Collections.IDictionary> объект при вызове <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6d376-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="6d376-119">Пример</span><span class="sxs-lookup"><span data-stu-id="6d376-119">Example</span></span>

<span data-ttu-id="6d376-120">В следующем примере объявляется пользовательский элемент с именем  **\<sampleSection >** , содержащий параметры, считываемых <xref:System.Configuration.SingleTagSectionHandler> класса:</span><span class="sxs-lookup"><span data-stu-id="6d376-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6d376-121">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="6d376-121">Configuration file</span></span>

<span data-ttu-id="6d376-122">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="6d376-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d376-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6d376-123">See also</span></span>

[<span data-ttu-id="6d376-124">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6d376-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
