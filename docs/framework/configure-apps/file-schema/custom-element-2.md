---
title: Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: e5c5c6cf5744aa385e6f6700cad623751a4d7427
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215478"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="aa272-102">Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="aa272-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="aa272-103">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="aa272-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="aa272-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa272-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="aa272-105">&nbsp;&nbsp; **\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="aa272-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="aa272-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa272-106">Attributes</span></span>

<span data-ttu-id="aa272-107">Нет</span><span class="sxs-lookup"><span data-stu-id="aa272-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="aa272-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="aa272-108">Parent element</span></span>

|     | <span data-ttu-id="aa272-109">Описание</span><span class="sxs-lookup"><span data-stu-id="aa272-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="aa272-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="aa272-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="aa272-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa272-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="aa272-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa272-112">Child elements</span></span>

|     | <span data-ttu-id="aa272-113">Описание</span><span class="sxs-lookup"><span data-stu-id="aa272-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="aa272-114">[ **\<добавить >** ](add-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="aa272-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="aa272-115">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="aa272-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="aa272-116">[ **\<удалить >** ](remove-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="aa272-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="aa272-117">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa272-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="aa272-118">[ **\<очистить >** ](clear-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="aa272-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="aa272-119">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="aa272-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="aa272-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa272-120">Remarks</span></span>

<span data-ttu-id="aa272-121">Элемент **\<sectionName >** — это пользовательский элемент, определяемый тегом **\<раздела >** в элементе **\<configSections >** .</span><span class="sxs-lookup"><span data-stu-id="aa272-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="aa272-122">В следующей таблице показан тип объекта, возвращаемого методом ConfigurationSettings. config для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="aa272-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="aa272-123">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="aa272-123">Configuration section handler</span></span>                        | <span data-ttu-id="aa272-124">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="aa272-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="aa272-125">Пример</span><span class="sxs-lookup"><span data-stu-id="aa272-125">Example</span></span>

<span data-ttu-id="aa272-126">В следующем примере показано, как объявить разделы, в которых используются классы <xref:System.Configuration.DictionarySectionHandler> и <xref:System.Configuration.NameValueSectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="aa272-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="aa272-127">Первый настраиваемый элемент — **\<диктионарисампле >** , который содержит параметры, считанные классом <xref:System.Configuration.DictionarySectionHandler> в сборке `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="aa272-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="aa272-128">Второй настраиваемый элемент — **\<мисектион >** , который содержит параметры, считанные классом <xref:System.Configuration.NameValueSectionHandler> в сборке `System.dll`.</span><span class="sxs-lookup"><span data-stu-id="aa272-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="aa272-129">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="aa272-129">Configuration file</span></span>

<span data-ttu-id="aa272-130">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="aa272-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa272-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="aa272-131">See also</span></span>

- [<span data-ttu-id="aa272-132">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa272-132">Configuration file schema for the .NET Framework</span></span>](index.md)
