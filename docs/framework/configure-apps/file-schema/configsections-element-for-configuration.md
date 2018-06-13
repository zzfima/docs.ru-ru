---
title: '&lt;configSections&gt; элемент для &lt;конфигурации&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 33406a67389cdf857fa5030e20d8a4dec7662741
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752082"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="633e5-102">\<configSections > элемент для \<конфигурации ></span><span class="sxs-lookup"><span data-stu-id="633e5-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="633e5-103">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="633e5-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="633e5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="633e5-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="633e5-105">&nbsp;&nbsp;**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="633e5-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="633e5-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="633e5-106">Attributes</span></span>

<span data-ttu-id="633e5-107">Нет</span><span class="sxs-lookup"><span data-stu-id="633e5-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="633e5-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="633e5-108">Parent element</span></span>

|     | <span data-ttu-id="633e5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="633e5-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="633e5-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="633e5-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="633e5-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="633e5-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="633e5-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="633e5-112">Child elements</span></span>

|     | <span data-ttu-id="633e5-113">Описание</span><span class="sxs-lookup"><span data-stu-id="633e5-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="633e5-114">**\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="633e5-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="633e5-115">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="633e5-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="633e5-116">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="633e5-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="633e5-117">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="633e5-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="633e5-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="633e5-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="633e5-119">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="633e5-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="633e5-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="633e5-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="633e5-121">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="633e5-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="633e5-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="633e5-122">Remarks</span></span>

<span data-ttu-id="633e5-123">Если этот элемент находится в файле конфигурации, его необходимо быть первым дочерним элементом  **\<конфигурации >** элемента.</span><span class="sxs-lookup"><span data-stu-id="633e5-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="633e5-124">Пример</span><span class="sxs-lookup"><span data-stu-id="633e5-124">Example</span></span>

<span data-ttu-id="633e5-125">Приведенный ниже показан способ определения раздела конфигурации и его параметров.</span><span class="sxs-lookup"><span data-stu-id="633e5-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="633e5-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="633e5-126">Configuration file</span></span>

<span data-ttu-id="633e5-127">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="633e5-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="633e5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="633e5-128">See also</span></span>

[<span data-ttu-id="633e5-129">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="633e5-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
