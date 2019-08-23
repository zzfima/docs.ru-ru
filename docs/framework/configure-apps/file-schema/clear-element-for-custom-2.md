---
title: <clear>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: fbb689db4abc5d59729d9a4d9807a02a0983d40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927710"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="70321-102">\<Очистка элемента > для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="70321-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="70321-103">Удаляет все ранее определенные параметры в разделе.</span><span class="sxs-lookup"><span data-stu-id="70321-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="70321-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="70321-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="70321-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="70321-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="70321-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**</span><span class="sxs-lookup"><span data-stu-id="70321-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="70321-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="70321-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="70321-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="70321-108">Attributes</span></span>

<span data-ttu-id="70321-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="70321-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="70321-110">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="70321-110">Parent element</span></span>

|     | <span data-ttu-id="70321-111">Описание</span><span class="sxs-lookup"><span data-stu-id="70321-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="70321-112">элемент  **>\<sectionName**</span><span class="sxs-lookup"><span data-stu-id="70321-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="70321-113">Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="70321-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="70321-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="70321-114">Child elements</span></span>

<span data-ttu-id="70321-115">None</span><span class="sxs-lookup"><span data-stu-id="70321-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="70321-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="70321-116">Remarks</span></span>

<span data-ttu-id="70321-117">С помощью  **\<элемента clear >** можно удалить из приложения все параметры, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="70321-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="70321-118">Пример</span><span class="sxs-lookup"><span data-stu-id="70321-118">Example</span></span>

<span data-ttu-id="70321-119">В этом примере определяются в файле конфигурации компьютера и файл конфигурации приложения и показано, как использовать **\<снимите>** элемент в файле конфигурации приложения для очистки разделов, определенных ранее в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="70321-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="70321-120">Следующий код файла конфигурации компьютера объявляет раздел  **\<мисектион >** :</span><span class="sxs-lookup"><span data-stu-id="70321-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="70321-121">Следующий код файла конфигурации приложения удаляет все параметры из  **\<мисектион >** .</span><span class="sxs-lookup"><span data-stu-id="70321-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="70321-122">Приложение не может получить параметры, которые были объявлены в, в  **\<разделе мисектион >** файла конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="70321-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="70321-123">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="70321-123">Configuration file</span></span>

<span data-ttu-id="70321-124">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="70321-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="70321-125">См. также</span><span class="sxs-lookup"><span data-stu-id="70321-125">See also</span></span>

- [<span data-ttu-id="70321-126">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70321-126">Configuration file schema for the .NET Framework</span></span>](index.md)
