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
ms.openlocfilehash: 8636050b2618d1b2c2da0c08c756b0ed221c7f6f
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300761"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ae243-102">Настраиваемый элемент для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="ae243-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ae243-103">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="ae243-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="ae243-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span><span class="sxs-lookup"><span data-stu-id="ae243-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span></span>
<span data-ttu-id="ae243-105">&nbsp;&nbsp; **\<параметра sectionName >**</span><span class="sxs-lookup"><span data-stu-id="ae243-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="ae243-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ae243-106">Attributes</span></span>

<span data-ttu-id="ae243-107">Нет</span><span class="sxs-lookup"><span data-stu-id="ae243-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ae243-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="ae243-108">Parent element</span></span>

|     | <span data-ttu-id="ae243-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ae243-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ae243-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ae243-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="ae243-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ae243-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ae243-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ae243-112">Child elements</span></span>

|     | <span data-ttu-id="ae243-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ae243-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="ae243-114">[ **\<Добавить >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ae243-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="ae243-115">Добавляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="ae243-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="ae243-116">[ **\<Удалить >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ae243-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ae243-117">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="ae243-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="ae243-118">[ **\<Очистить >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) для <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="ae243-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="ae243-119">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="ae243-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ae243-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae243-120">Remarks</span></span>

<span data-ttu-id="ae243-121">**\<Параметра sectionName>** элемент является пользовательским элементом определяется **\<разделе>** тегом **\<configSections>** элемент.</span><span class="sxs-lookup"><span data-stu-id="ae243-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="ae243-122">В следующей таблице показаны возвращает тип объекта, метод ConfigurationSettings.GetConfig для каждого обработчика раздела конфигурации:</span><span class="sxs-lookup"><span data-stu-id="ae243-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="ae243-123">Обработчик раздела конфигурации</span><span class="sxs-lookup"><span data-stu-id="ae243-123">Configuration section handler</span></span>                        | <span data-ttu-id="ae243-124">Возвращаемый тип</span><span class="sxs-lookup"><span data-stu-id="ae243-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="ae243-125">Пример</span><span class="sxs-lookup"><span data-stu-id="ae243-125">Example</span></span>

<span data-ttu-id="ae243-126">В следующем примере показан способ объявления разделах, использующих <xref:System.Configuration.DictionarySectionHandler> и <xref:System.Configuration.NameValueSectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="ae243-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="ae243-127">Первый элемент управления находится  **\<dictionarySample >** , который содержит параметры, считываемые <xref:System.Configuration.DictionarySectionHandler> в класс `System.dll` сборки.</span><span class="sxs-lookup"><span data-stu-id="ae243-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="ae243-128">Второй элемент управления находится  **\<mySection >** , который содержит параметры, считываемые <xref:System.Configuration.NameValueSectionHandler> в класс `System.dll` сборки.</span><span class="sxs-lookup"><span data-stu-id="ae243-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ae243-129">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ae243-129">Configuration file</span></span>

<span data-ttu-id="ae243-130">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="ae243-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae243-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ae243-131">See also</span></span>

- [<span data-ttu-id="ae243-132">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ae243-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
