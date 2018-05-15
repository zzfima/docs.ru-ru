---
title: '&lt;Добавить&gt; элемент NameValueSectionHandler и DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
ms.openlocfilehash: aeb3e3a4be201369ca2df8d231498dd2400d3c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6ecfa-102">\<Добавить > элемент NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="6ecfa-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6ecfa-103">Добавляет пользовательские параметры приложения.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-103">Adds custom application settings.</span></span> <span data-ttu-id="6ecfa-104">Каждый  **\<Добавить >** тег содержит пару ключ значение.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="6ecfa-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6ecfa-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6ecfa-106">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="6ecfa-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="6ecfa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="6ecfa-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6ecfa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ecfa-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="6ecfa-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6ecfa-109">Attributes</span></span>

| <span data-ttu-id="6ecfa-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6ecfa-110">Attribute</span></span> | <span data-ttu-id="6ecfa-111">Описание</span><span class="sxs-lookup"><span data-stu-id="6ecfa-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6ecfa-112">**key**</span><span class="sxs-lookup"><span data-stu-id="6ecfa-112">**key**</span></span>   | <span data-ttu-id="6ecfa-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-113">Required attribute.</span></span><br><br><span data-ttu-id="6ecfa-114">Указывает имя параметра.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="6ecfa-115">**value**</span><span class="sxs-lookup"><span data-stu-id="6ecfa-115">**value**</span></span> | <span data-ttu-id="6ecfa-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-116">Required attribute.</span></span><br><br><span data-ttu-id="6ecfa-117">Задает значение параметра.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6ecfa-118">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="6ecfa-118">Parent element</span></span>

| <span data-ttu-id="6ecfa-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6ecfa-119">Element</span></span> | <span data-ttu-id="6ecfa-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6ecfa-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="6ecfa-121">**\<sectionName >** элемент</span><span class="sxs-lookup"><span data-stu-id="6ecfa-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="6ecfa-122">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6ecfa-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6ecfa-123">Child elements</span></span>

<span data-ttu-id="6ecfa-124">Нет</span><span class="sxs-lookup"><span data-stu-id="6ecfa-124">None</span></span>

## <a name="example"></a><span data-ttu-id="6ecfa-125">Пример</span><span class="sxs-lookup"><span data-stu-id="6ecfa-125">Example</span></span>

<span data-ttu-id="6ecfa-126">В следующем примере показано определение настраиваемого раздела конфигурации и использование  **\<Добавить >** элемент для задания параметров в разделе:</span><span class="sxs-lookup"><span data-stu-id="6ecfa-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="6ecfa-127">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="6ecfa-127">Configuration file</span></span>

<span data-ttu-id="6ecfa-128">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="6ecfa-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ecfa-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6ecfa-129">See also</span></span>

[<span data-ttu-id="6ecfa-130">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ecfa-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
