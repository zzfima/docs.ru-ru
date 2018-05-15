---
title: '&lt;Удалить&gt; элемент NameValueSectionHandler и DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 61f1c98d3f12b5aa1d25595ca28328602683b073
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="c9f9e-102">\<Удалите > элемент NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="c9f9e-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="c9f9e-103">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="c9f9e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="c9f9e-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="c9f9e-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="c9f9e-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="c9f9e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалите >**</span><span class="sxs-lookup"><span data-stu-id="c9f9e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c9f9e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9f9e-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="c9f9e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9f9e-108">Attribute</span></span>

|           | <span data-ttu-id="c9f9e-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c9f9e-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c9f9e-110">**key**</span><span class="sxs-lookup"><span data-stu-id="c9f9e-110">**key**</span></span>   | <span data-ttu-id="c9f9e-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-111">Required attribute.</span></span><br><br><span data-ttu-id="c9f9e-112">Задает имя удаляемого параметра.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c9f9e-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="c9f9e-113">Parent element</span></span>

| <span data-ttu-id="c9f9e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9f9e-114">Element</span></span> | <span data-ttu-id="c9f9e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c9f9e-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="c9f9e-116">**\<sectionName >** элемент</span><span class="sxs-lookup"><span data-stu-id="c9f9e-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="c9f9e-117">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c9f9e-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9f9e-118">Child elements</span></span>

<span data-ttu-id="c9f9e-119">Нет</span><span class="sxs-lookup"><span data-stu-id="c9f9e-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="c9f9e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9f9e-120">Remarks</span></span>

<span data-ttu-id="c9f9e-121">Можно использовать  **\<удалить >** элемента для удаления параметров приложения, которые были определены на высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="c9f9e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="c9f9e-122">Example</span></span>

<span data-ttu-id="c9f9e-123">В следующем примере показано, как использовать  **\<удалить >** элемент в файле конфигурации приложения для удаления параметров, определенных ранее в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="c9f9e-124">В коде следующего файла конфигурации компьютера объявляется раздел  **\<mySection >** и добавляются два параметра `key1` и `key2`, к нему:</span><span class="sxs-lookup"><span data-stu-id="c9f9e-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="c9f9e-125">В коде следующего файла конфигурации приложения удаляет `key2` из  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="c9f9e-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c9f9e-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c9f9e-126">Configuration file</span></span>

<span data-ttu-id="c9f9e-127">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="c9f9e-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9f9e-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c9f9e-128">See also</span></span>

[<span data-ttu-id="c9f9e-129">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c9f9e-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
