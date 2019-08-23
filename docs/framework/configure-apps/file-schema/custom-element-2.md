---
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 890269857aaa00ce62195ccb2f4cb184b363b61e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921038"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="11df8-102">Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="11df8-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="11df8-103">Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="11df8-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="11df8-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11df8-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="11df8-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="11df8-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="11df8-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11df8-106">Attributes</span></span>

<span data-ttu-id="11df8-107">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="11df8-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="11df8-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="11df8-108">Parent element</span></span>

|     | <span data-ttu-id="11df8-109">Описание</span><span class="sxs-lookup"><span data-stu-id="11df8-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="11df8-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="11df8-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="11df8-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="11df8-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="11df8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11df8-112">Child elements</span></span>

|     | <span data-ttu-id="11df8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="11df8-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="11df8-114">Добавьте > для и [ **\<** ](add-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11df8-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="11df8-115">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="11df8-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="11df8-116">Удалите > для и [ **\<** ](remove-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11df8-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="11df8-117">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="11df8-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="11df8-118">очистить > для и [ **\<** ](clear-element-for-custom-2.md) <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="11df8-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="11df8-119">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="11df8-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="11df8-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="11df8-120">Remarks</span></span>

<span data-ttu-id="11df8-121">**\<Параметра sectionName>** элемент является пользовательским элементом определяется **\<разделе>** тегом **\<configSections>** элемент.</span><span class="sxs-lookup"><span data-stu-id="11df8-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="11df8-122">В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="11df8-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="11df8-123">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="11df8-123">Configuration section handler</span></span>                        | <span data-ttu-id="11df8-124">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="11df8-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="11df8-125">Пример</span><span class="sxs-lookup"><span data-stu-id="11df8-125">Example</span></span>

<span data-ttu-id="11df8-126">В следующем примере показано, как объявить разделы, в <xref:System.Configuration.DictionarySectionHandler> которых <xref:System.Configuration.NameValueSectionHandler> используются классы и.</span><span class="sxs-lookup"><span data-stu-id="11df8-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="11df8-127">Первый настраиваемый элемент —  **\<диктионарисампле >** , который содержит <xref:System.Configuration.DictionarySectionHandler> параметры, считанные классом в `System.dll` сборке.</span><span class="sxs-lookup"><span data-stu-id="11df8-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="11df8-128">Второй настраиваемый элемент —  **\<мисектион >** , который содержит <xref:System.Configuration.NameValueSectionHandler> параметры, считанные классом в `System.dll` сборке.</span><span class="sxs-lookup"><span data-stu-id="11df8-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="11df8-129">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="11df8-129">Configuration file</span></span>

<span data-ttu-id="11df8-130">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="11df8-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="11df8-131">См. также</span><span class="sxs-lookup"><span data-stu-id="11df8-131">See also</span></span>

- [<span data-ttu-id="11df8-132">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="11df8-132">Configuration file schema for the .NET Framework</span></span>](index.md)
