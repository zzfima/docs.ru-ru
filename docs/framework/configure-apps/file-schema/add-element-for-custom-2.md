---
title: элемент <add> для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e7d68530ae1f0666fc4940ffe7605c3bf8dfe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119616"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="baa79-102">\<добавить элемент > для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="baa79-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="baa79-103">Добавляет настраиваемые параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="baa79-103">Adds custom application settings.</span></span> <span data-ttu-id="baa79-104">Каждый **\<добавляемый тег >** содержит пару "ключ-значение".</span><span class="sxs-lookup"><span data-stu-id="baa79-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="baa79-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="baa79-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="baa79-106">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="baa79-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="baa79-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="baa79-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="baa79-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baa79-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="baa79-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="baa79-109">Attributes</span></span>

| <span data-ttu-id="baa79-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="baa79-110">Attribute</span></span> | <span data-ttu-id="baa79-111">Описание</span><span class="sxs-lookup"><span data-stu-id="baa79-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="baa79-112">**key**</span><span class="sxs-lookup"><span data-stu-id="baa79-112">**key**</span></span>   | <span data-ttu-id="baa79-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="baa79-113">Required attribute.</span></span><br><br><span data-ttu-id="baa79-114">Задает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="baa79-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="baa79-115">**value**</span><span class="sxs-lookup"><span data-stu-id="baa79-115">**value**</span></span> | <span data-ttu-id="baa79-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="baa79-116">Required attribute.</span></span><br><br><span data-ttu-id="baa79-117">Задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="baa79-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="baa79-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="baa79-118">Parent element</span></span>

| <span data-ttu-id="baa79-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="baa79-119">Element</span></span> | <span data-ttu-id="baa79-120">Описание</span><span class="sxs-lookup"><span data-stu-id="baa79-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="baa79-121"> **\<sectionName >** Дерев</span><span class="sxs-lookup"><span data-stu-id="baa79-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="baa79-122">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="baa79-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="baa79-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="baa79-123">Child elements</span></span>

<span data-ttu-id="baa79-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="baa79-124">None</span></span>

## <a name="example"></a><span data-ttu-id="baa79-125">Пример</span><span class="sxs-lookup"><span data-stu-id="baa79-125">Example</span></span>

<span data-ttu-id="baa79-126">В следующем примере показано, как определить пользовательский раздел конфигурации и использовать элемент **\<add >** , чтобы поместить параметры в раздел:</span><span class="sxs-lookup"><span data-stu-id="baa79-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="baa79-127">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="baa79-127">Configuration file</span></span>

<span data-ttu-id="baa79-128">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="baa79-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="baa79-129">См. также</span><span class="sxs-lookup"><span data-stu-id="baa79-129">See also</span></span>

- [<span data-ttu-id="baa79-130">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="baa79-130">Configuration file schema for the .NET Framework</span></span>](index.md)
