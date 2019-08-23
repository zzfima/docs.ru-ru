---
title: Настраиваемый элемент для Синглетагсектионхандлер
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927504"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="f2e30-102">Настраиваемый элемент для Синглетагсектионхандлер</span><span class="sxs-lookup"><span data-stu-id="f2e30-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="f2e30-103">Определяет параметры в разделе пользовательской конфигурации, который определяется по \<разделу > элементу и <xref:System.Configuration.SingleTagSectionHandler> использует класс.</span><span class="sxs-lookup"><span data-stu-id="f2e30-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="f2e30-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="f2e30-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="f2e30-105">&nbsp;&nbsp; *\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="f2e30-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="f2e30-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2e30-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="f2e30-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f2e30-107">Attributes</span></span>

<span data-ttu-id="f2e30-108">Атрибуты и значения атрибутов определяются пользователем.</span><span class="sxs-lookup"><span data-stu-id="f2e30-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="f2e30-109">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="f2e30-109">Parent element</span></span>

|     | <span data-ttu-id="f2e30-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f2e30-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f2e30-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f2e30-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="f2e30-112">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2e30-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f2e30-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f2e30-113">Child elements</span></span>

<span data-ttu-id="f2e30-114">None</span><span class="sxs-lookup"><span data-stu-id="f2e30-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f2e30-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2e30-115">Remarks</span></span>

<span data-ttu-id="f2e30-116">Элемент > [ **\<** ](section-element.md) sectionName является пользовательским элементом, определяемым разделом > тегом в [ **\<элементе > configSections**](configsections-element-for-configuration.md) .  **\<**</span><span class="sxs-lookup"><span data-stu-id="f2e30-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="f2e30-117">Система конфигурации возвращает <xref:System.Collections.IDictionary> объект при вызове метода <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2e30-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="f2e30-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f2e30-118">Example</span></span>

<span data-ttu-id="f2e30-119">В следующем примере объявляется пользовательский элемент с именем  **\<самплесектион >** , который содержит <xref:System.Configuration.SingleTagSectionHandler> параметры, считанные классом:</span><span class="sxs-lookup"><span data-stu-id="f2e30-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="f2e30-120">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="f2e30-120">Configuration file</span></span>

<span data-ttu-id="f2e30-121">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="f2e30-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2e30-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f2e30-122">See also</span></span>

- [<span data-ttu-id="f2e30-123">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f2e30-123">Configuration file schema for the .NET Framework</span></span>](index.md)
