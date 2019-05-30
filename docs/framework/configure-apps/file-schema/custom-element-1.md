---
title: Настраиваемый элемент для SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: ad98617cd4e88d1650f67136536b7dd5994233a4
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301157"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="74e17-102">Настраиваемый элемент для SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="74e17-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="74e17-103">Определяет параметры настраиваемого раздела конфигурации, определяемый \<разделе > элемент и использует <xref:System.Configuration.SingleTagSectionHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="74e17-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="74e17-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="74e17-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="74e17-105">&nbsp;&nbsp; *\<параметра sectionName >*</span><span class="sxs-lookup"><span data-stu-id="74e17-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="74e17-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="74e17-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="74e17-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="74e17-107">Attributes</span></span>

<span data-ttu-id="74e17-108">Атрибуты и значения атрибутов являются определяемые пользователем.</span><span class="sxs-lookup"><span data-stu-id="74e17-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="74e17-109">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="74e17-109">Parent element</span></span>

|     | <span data-ttu-id="74e17-110">Описание</span><span class="sxs-lookup"><span data-stu-id="74e17-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="74e17-111"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="74e17-111">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="74e17-112">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74e17-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="74e17-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="74e17-113">Child elements</span></span>

<span data-ttu-id="74e17-114">None</span><span class="sxs-lookup"><span data-stu-id="74e17-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="74e17-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="74e17-115">Remarks</span></span>

<span data-ttu-id="74e17-116"> *\*\<Параметра sectionName >** элемент является пользовательским элементом определяется [  *\*\<разделе >** ](~/docs/framework/configure-apps/file-schema/section-element.md) тегом [  *\*\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="74e17-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="74e17-117">Система конфигурации возвращает <xref:System.Collections.IDictionary> объекта при вызове <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74e17-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="74e17-118">Пример</span><span class="sxs-lookup"><span data-stu-id="74e17-118">Example</span></span>

<span data-ttu-id="74e17-119">В следующем примере объявляется пользовательский элемент с именем  **\<sampleSection >** , содержащий параметры, считываемые <xref:System.Configuration.SingleTagSectionHandler> класса:</span><span class="sxs-lookup"><span data-stu-id="74e17-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="74e17-120">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="74e17-120">Configuration file</span></span>

<span data-ttu-id="74e17-121">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="74e17-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="74e17-122">См. также</span><span class="sxs-lookup"><span data-stu-id="74e17-122">See also</span></span>

- [<span data-ttu-id="74e17-123">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74e17-123">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
