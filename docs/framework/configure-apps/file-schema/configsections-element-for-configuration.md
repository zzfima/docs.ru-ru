---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d522d004630dee942e24c39a936feae7dc957bd5
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300793"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="1a3d8-102">\<configSections > элемент для \<configuration ></span><span class="sxs-lookup"><span data-stu-id="1a3d8-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="1a3d8-103">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="1a3d8-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="1a3d8-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="1a3d8-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="1a3d8-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="1a3d8-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a3d8-106">Attributes</span></span>

<span data-ttu-id="1a3d8-107">Нет</span><span class="sxs-lookup"><span data-stu-id="1a3d8-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1a3d8-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="1a3d8-108">Parent element</span></span>

|     | <span data-ttu-id="1a3d8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="1a3d8-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1a3d8-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="1a3d8-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="1a3d8-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1a3d8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1a3d8-112">Child elements</span></span>

|     | <span data-ttu-id="1a3d8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a3d8-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1a3d8-114"> *\*\<раздел >** </span><span class="sxs-lookup"><span data-stu-id="1a3d8-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="1a3d8-115">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="1a3d8-116"> *\*\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="1a3d8-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="1a3d8-117">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="1a3d8-118"> *\*\<remove>** </span><span class="sxs-lookup"><span data-stu-id="1a3d8-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="1a3d8-119">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="1a3d8-120"> *\*\<clear>** </span><span class="sxs-lookup"><span data-stu-id="1a3d8-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="1a3d8-121">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1a3d8-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a3d8-122">Remarks</span></span>

<span data-ttu-id="1a3d8-123">Если этот элемент находится в файле конфигурации, его необходимо первый дочерний элемент элемента  **\<конфигурации >** элемент.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="1a3d8-124">Пример</span><span class="sxs-lookup"><span data-stu-id="1a3d8-124">Example</span></span>

<span data-ttu-id="1a3d8-125">В следующем примере показано, как определения раздела конфигурации и его параметров:</span><span class="sxs-lookup"><span data-stu-id="1a3d8-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="1a3d8-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="1a3d8-126">Configuration file</span></span>

<span data-ttu-id="1a3d8-127">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="1a3d8-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a3d8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="1a3d8-128">See also</span></span>

- [<span data-ttu-id="1a3d8-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a3d8-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
