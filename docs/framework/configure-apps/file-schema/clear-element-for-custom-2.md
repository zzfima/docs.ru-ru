---
title: '&lt;Очистить&gt; элемент NameValueSectionHandler и DictionarySectionHandler'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: guardrex
ms.author: mairaw
ms.openlocfilehash: a1cbd682faa4c60e50bc3b73b58ef226dd599da2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358239"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="e7247-102">\<Очистить > элемент NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="e7247-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="e7247-103">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="e7247-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="e7247-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e7247-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e7247-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="e7247-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="e7247-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Очистить >**</span><span class="sxs-lookup"><span data-stu-id="e7247-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e7247-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7247-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="e7247-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7247-108">Attributes</span></span>

<span data-ttu-id="e7247-109">Нет</span><span class="sxs-lookup"><span data-stu-id="e7247-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e7247-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="e7247-110">Parent element</span></span>

|     | <span data-ttu-id="e7247-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e7247-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="e7247-112">**\<sectionName >** элемент</span><span class="sxs-lookup"><span data-stu-id="e7247-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="e7247-113">Определяет параметры для пользовательских разделов конфигурации, использующие <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler> классы.</span><span class="sxs-lookup"><span data-stu-id="e7247-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e7247-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7247-114">Child elements</span></span>

<span data-ttu-id="e7247-115">Нет</span><span class="sxs-lookup"><span data-stu-id="e7247-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e7247-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7247-116">Remarks</span></span>

<span data-ttu-id="e7247-117">Можно использовать  **\<снимите >** элемента, который требуется удалить все параметры из приложения, которые были определены на высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e7247-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="e7247-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e7247-118">Example</span></span>

<span data-ttu-id="e7247-119">В этом примере определяется в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать  **\<снимите >** элемент в файле конфигурации приложения для очистки разделов, ранее определенные в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e7247-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="e7247-120">В коде следующего файла конфигурации компьютера объявляется раздел  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="e7247-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="e7247-121">В коде следующего файла конфигурации приложения удаляет все параметры из  **\<mySection >**.</span><span class="sxs-lookup"><span data-stu-id="e7247-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="e7247-122">Приложение не может получить какие-либо параметры, которые были объявлены в в  **\<mySection >** раздела в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e7247-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e7247-123">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e7247-123">Configuration file</span></span>

<span data-ttu-id="e7247-124">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="e7247-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7247-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e7247-125">See also</span></span>

[<span data-ttu-id="e7247-126">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e7247-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
