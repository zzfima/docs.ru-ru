---
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73c07d58bb226346cb99a1fe50b12bb0e7e746e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118534"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="da325-102">Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="da325-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="da325-103">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="da325-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="da325-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da325-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="da325-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="da325-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="da325-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da325-106">Attributes</span></span>

<span data-ttu-id="da325-107">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="da325-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="da325-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="da325-108">Parent element</span></span>

|     | <span data-ttu-id="da325-109">Описание</span><span class="sxs-lookup"><span data-stu-id="da325-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="da325-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="da325-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="da325-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da325-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="da325-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da325-112">Child elements</span></span>

|     | <span data-ttu-id="da325-113">Описание</span><span class="sxs-lookup"><span data-stu-id="da325-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="da325-114">[ **\<добавить >** ](add-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="da325-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="da325-115">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="da325-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="da325-116">[ **\<удалить >** ](remove-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="da325-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="da325-117">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="da325-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="da325-118">[ **\<очистить >** ](clear-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="da325-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="da325-119">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="da325-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="da325-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="da325-120">Remarks</span></span>

<span data-ttu-id="da325-121">Элемент **\<sectionName >** — это пользовательский элемент, определяемый тегом **\<раздела >** в элементе **\<configSections >** .</span><span class="sxs-lookup"><span data-stu-id="da325-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="da325-122">В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="da325-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="da325-123">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="da325-123">Configuration section handler</span></span>                        | <span data-ttu-id="da325-124">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="da325-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="da325-125">Пример</span><span class="sxs-lookup"><span data-stu-id="da325-125">Example</span></span>

<span data-ttu-id="da325-126">В следующем примере показано, как объявить разделы, в которых используются классы <xref:System.Configuration.DictionarySectionHandler> и <xref:System.Configuration.NameValueSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="da325-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="da325-127">Первый настраиваемый элемент — **\<диктионарисампле >** , который содержит параметры, считанные классом <xref:System.Configuration.DictionarySectionHandler> в сборке `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="da325-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="da325-128">Второй настраиваемый элемент — **\<мисектион >** , который содержит параметры, считанные классом <xref:System.Configuration.NameValueSectionHandler> в сборке `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="da325-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="da325-129">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="da325-129">Configuration file</span></span>

<span data-ttu-id="da325-130">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="da325-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="da325-131">См. также</span><span class="sxs-lookup"><span data-stu-id="da325-131">See also</span></span>

- [<span data-ttu-id="da325-132">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da325-132">Configuration file schema for the .NET Framework</span></span>](index.md)
