---
title: Пользовательский элемент NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 3a16952c5cd3759873faeb0fce45b8aa5170b083
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5e889-102">Пользовательский элемент NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="5e889-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5e889-103">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="5e889-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="5e889-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5e889-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5e889-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="5e889-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="5e889-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e889-106">Attributes</span></span>

<span data-ttu-id="5e889-107">Нет</span><span class="sxs-lookup"><span data-stu-id="5e889-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="5e889-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="5e889-108">Parent element</span></span>

|     | <span data-ttu-id="5e889-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5e889-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5e889-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="5e889-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="5e889-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e889-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5e889-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e889-112">Child elements</span></span>

|     | <span data-ttu-id="5e889-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5e889-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="5e889-114">[**\<Добавить >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5e889-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="5e889-115">Добавляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="5e889-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="5e889-116">[**\<Удалите >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5e889-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="5e889-117">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="5e889-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="5e889-118">[**\<Очистить >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5e889-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="5e889-119">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="5e889-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5e889-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e889-120">Remarks</span></span>

<span data-ttu-id="5e889-121">**\<SectionName >** элемент является пользовательским элементом определяется  **\<раздел >** тегом  **\<configSections >** элемент.</span><span class="sxs-lookup"><span data-stu-id="5e889-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="5e889-122">В следующей таблице показаны возвращает тип объекта, метод ConfigurationSettings.GetConfig для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="5e889-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="5e889-123">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="5e889-123">Configuration section handler</span></span>                        | <span data-ttu-id="5e889-124">Тип возвращаемого значения</span><span class="sxs-lookup"><span data-stu-id="5e889-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="5e889-125">Пример</span><span class="sxs-lookup"><span data-stu-id="5e889-125">Example</span></span>

<span data-ttu-id="5e889-126">В следующем примере показан способ объявления разделах, использующих <xref:System.Configuration.DictionarySectionHandler> и <xref:System.Configuration.NameValueSectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="5e889-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="5e889-127">Первый элемент пользовательского  **\<dictionarySample >**, который содержит параметры, считываемых <xref:System.Configuration.DictionarySectionHandler> в класс `System.dll` сборки.</span><span class="sxs-lookup"><span data-stu-id="5e889-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="5e889-128">Второй пользовательский элемент —  **\<mySection >**, который содержит параметры, считываемых <xref:System.Configuration.NameValueSectionHandler> в класс `System.dll` сборки.</span><span class="sxs-lookup"><span data-stu-id="5e889-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5e889-129">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5e889-129">Configuration file</span></span>

<span data-ttu-id="5e889-130">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="5e889-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e889-131">См. также</span><span class="sxs-lookup"><span data-stu-id="5e889-131">See also</span></span>

[<span data-ttu-id="5e889-132">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5e889-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
