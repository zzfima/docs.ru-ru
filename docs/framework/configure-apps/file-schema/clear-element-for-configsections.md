---
title: '&lt;Очистить&gt; элемент для &lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9439e2ac7634b242c9f847346f7dcf265d6ab419
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678009"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="568c1-102">\<Очистить > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="568c1-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="568c1-103">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="568c1-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="568c1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="568c1-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="568c1-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="568c1-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="568c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Очистить >**</span><span class="sxs-lookup"><span data-stu-id="568c1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="568c1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="568c1-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="568c1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="568c1-108">Attribute</span></span>

|           | <span data-ttu-id="568c1-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="568c1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="568c1-110">**name**</span><span class="sxs-lookup"><span data-stu-id="568c1-110">**name**</span></span>  | <span data-ttu-id="568c1-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="568c1-111">Required attribute.</span></span><br><br><span data-ttu-id="568c1-112">Задает имя раздела или группы разделов.</span><span class="sxs-lookup"><span data-stu-id="568c1-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="568c1-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="568c1-113">Parent element</span></span>

|     | <span data-ttu-id="568c1-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="568c1-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="568c1-115">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="568c1-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="568c1-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="568c1-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="568c1-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="568c1-117">Child elements</span></span>

<span data-ttu-id="568c1-118">Нет</span><span class="sxs-lookup"><span data-stu-id="568c1-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="568c1-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="568c1-119">Remarks</span></span>

<span data-ttu-id="568c1-120"> *\*\<Снимите >** элемент удаляет все разделы и группы разделов приложения, определенные ранее в текущем файле конфигурации или на более высоком уровне в иерархии файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="568c1-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="568c1-121">Пример</span><span class="sxs-lookup"><span data-stu-id="568c1-121">Example</span></span>

<span data-ttu-id="568c1-122">В этом примере определяются в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать  **\<снимите >** элемент в файле конфигурации приложения для очистки разделов, определенных ранее в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="568c1-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="568c1-123">В коде следующего файла конфигурации компьютера объявляются два раздела,  **\<sampleSection >** и  **\<anotherSampleSection >**, которые считываются перед приложения файл конфигурации:</span><span class="sxs-lookup"><span data-stu-id="568c1-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="568c1-124">В коде следующего файла конфигурации приложения Очистка всех ранее определенных разделов.</span><span class="sxs-lookup"><span data-stu-id="568c1-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="568c1-125">Приложение не может использовать или получить параметры в одном из разделов, которые были объявлены в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="568c1-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="568c1-126">Тем не менее, его можно использовать параметры из  **\<anotherSection >** потому, что он следует после  **\<снимите >** элемент.</span><span class="sxs-lookup"><span data-stu-id="568c1-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="568c1-127">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="568c1-127">Configuration file</span></span>

<span data-ttu-id="568c1-128">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="568c1-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="568c1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="568c1-129">See also</span></span>

- [<span data-ttu-id="568c1-130">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="568c1-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
