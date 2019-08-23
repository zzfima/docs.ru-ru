---
title: <remove>элемент для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920951"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="ef9f1-102">\<Удаление элемента > для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="ef9f1-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="ef9f1-103">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="ef9f1-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ef9f1-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="ef9f1-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="ef9f1-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="ef9f1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="ef9f1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ef9f1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef9f1-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="ef9f1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ef9f1-108">Attribute</span></span>

|           | <span data-ttu-id="ef9f1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ef9f1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ef9f1-110">**key**</span><span class="sxs-lookup"><span data-stu-id="ef9f1-110">**key**</span></span>   | <span data-ttu-id="ef9f1-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-111">Required attribute.</span></span><br><br><span data-ttu-id="ef9f1-112">Задает имя удаляемого параметра.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ef9f1-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="ef9f1-113">Parent element</span></span>

| <span data-ttu-id="ef9f1-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef9f1-114">Element</span></span> | <span data-ttu-id="ef9f1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ef9f1-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="ef9f1-116">элемент  **>\<sectionName**</span><span class="sxs-lookup"><span data-stu-id="ef9f1-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="ef9f1-117">Определяет параметры для пользовательских разделов конфигурации, <xref:System.Configuration.NameValueSectionHandler> использующих <xref:System.Configuration.DictionarySectionHandler> классы и.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ef9f1-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef9f1-118">Child elements</span></span>

<span data-ttu-id="ef9f1-119">None</span><span class="sxs-lookup"><span data-stu-id="ef9f1-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="ef9f1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef9f1-120">Remarks</span></span>

<span data-ttu-id="ef9f1-121">Элемент  **\<Remove >** можно использовать для удаления из приложения параметров, определенных на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="ef9f1-122">Пример</span><span class="sxs-lookup"><span data-stu-id="ef9f1-122">Example</span></span>

<span data-ttu-id="ef9f1-123">В следующем примере показано,  **\<** как использовать элемент remove > в файле конфигурации приложения для удаления параметров, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="ef9f1-124">Следующий код файла конфигурации компьютера объявляет раздел  **\<мисектион >** и `key1` добавляет в него `key2`два параметра:</span><span class="sxs-lookup"><span data-stu-id="ef9f1-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="ef9f1-125">Следующий код файла конфигурации приложения удаляет `key2` параметр из  **\<мисектион >** :</span><span class="sxs-lookup"><span data-stu-id="ef9f1-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ef9f1-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ef9f1-126">Configuration file</span></span>

<span data-ttu-id="ef9f1-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="ef9f1-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef9f1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ef9f1-128">See also</span></span>

- [<span data-ttu-id="ef9f1-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ef9f1-129">Configuration file schema for the .NET Framework</span></span>](index.md)
