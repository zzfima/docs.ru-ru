---
title: Пользовательский элемент для SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155158"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="ba88d-102">Пользовательский элемент для SingleTagSectionHandler</span><span class="sxs-lookup"><span data-stu-id="ba88d-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="ba88d-103">Определяет настройки в специальном разделе конфигурации, который определяется разделом \<> элементом и использует <xref:System.Configuration.SingleTagSectionHandler> класс.</span><span class="sxs-lookup"><span data-stu-id="ba88d-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="ba88d-104">конфигурация &nbsp; &nbsp; [\*\* \<>\*\*](configuration-element.md) \* \<разделаName>\*</span><span class="sxs-lookup"><span data-stu-id="ba88d-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="ba88d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba88d-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="ba88d-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba88d-106">Attributes</span></span>

<span data-ttu-id="ba88d-107">Атрибуты и значения атрибутов определяются пользователем.</span><span class="sxs-lookup"><span data-stu-id="ba88d-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="ba88d-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="ba88d-108">Parent element</span></span>

|     | <span data-ttu-id="ba88d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ba88d-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ba88d-110">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="ba88d-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="ba88d-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba88d-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ba88d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba88d-112">Child elements</span></span>

<span data-ttu-id="ba88d-113">None</span><span class="sxs-lookup"><span data-stu-id="ba88d-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ba88d-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="ba88d-114">Remarks</span></span>

<span data-ttu-id="ba88d-115">\*\* \<Элемент sectionName>\*\* является пользовательским элементом, определяемым [\*\* \<разделом>\*\*](section-element.md) тегом [\*\* \<в элементе configSections>.\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="ba88d-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="ba88d-116">Система конфигурации <xref:System.Collections.IDictionary> возвращает объект <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>при вызове.</span><span class="sxs-lookup"><span data-stu-id="ba88d-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="ba88d-117">Пример</span><span class="sxs-lookup"><span data-stu-id="ba88d-117">Example</span></span>

<span data-ttu-id="ba88d-118">В следующем примере объявляется пользовательский элемент, называемый <xref:System.Configuration.SingleTagSectionHandler> \*\* \<sampleSection>,\*\* содержащий параметры, прочитаны классом:</span><span class="sxs-lookup"><span data-stu-id="ba88d-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ba88d-119">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ba88d-119">Configuration file</span></span>

<span data-ttu-id="ba88d-120">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="ba88d-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba88d-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba88d-121">See also</span></span>

- [<span data-ttu-id="ba88d-122">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="ba88d-122">Configuration file schema for the .NET Framework</span></span>](index.md)
