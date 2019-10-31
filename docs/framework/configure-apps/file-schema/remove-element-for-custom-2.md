---
title: элемент <remove> для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc1519a794e24e04074dd2a674ecc2c0f3666521
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118566"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="da356-102">\<удалить элемент > для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="da356-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="da356-103">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="da356-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="da356-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="da356-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="da356-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="da356-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="da356-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="da356-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="da356-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da356-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="da356-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da356-108">Attribute</span></span>

|           | <span data-ttu-id="da356-109">Описание</span><span class="sxs-lookup"><span data-stu-id="da356-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="da356-110">**key**</span><span class="sxs-lookup"><span data-stu-id="da356-110">**key**</span></span>   | <span data-ttu-id="da356-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="da356-111">Required attribute.</span></span><br><br><span data-ttu-id="da356-112">Задает имя удаляемого параметра.</span><span class="sxs-lookup"><span data-stu-id="da356-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="da356-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="da356-113">Parent element</span></span>

| <span data-ttu-id="da356-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="da356-114">Element</span></span> | <span data-ttu-id="da356-115">Описание</span><span class="sxs-lookup"><span data-stu-id="da356-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="da356-116"> **\<sectionName >** Дерев</span><span class="sxs-lookup"><span data-stu-id="da356-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="da356-117">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="da356-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="da356-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da356-118">Child elements</span></span>

<span data-ttu-id="da356-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="da356-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="da356-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="da356-120">Remarks</span></span>

<span data-ttu-id="da356-121">Элемент **\<удалить >** можно использовать для удаления из приложения параметров, определенных на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="da356-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="da356-122">Пример</span><span class="sxs-lookup"><span data-stu-id="da356-122">Example</span></span>

<span data-ttu-id="da356-123">В следующем примере показано использование элемента **\<Remove >** в файле конфигурации приложения для удаления параметров, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="da356-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="da356-124">Следующий код файла конфигурации компьютера объявляет раздел **\<мисектион >** и добавляет в него два параметра: `key1` и `key2`.</span><span class="sxs-lookup"><span data-stu-id="da356-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="da356-125">Следующий код файла конфигурации приложения удаляет параметр `key2` из **\<мисектион >** :</span><span class="sxs-lookup"><span data-stu-id="da356-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="da356-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="da356-126">Configuration file</span></span>

<span data-ttu-id="da356-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="da356-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="da356-128">См. также</span><span class="sxs-lookup"><span data-stu-id="da356-128">See also</span></span>

- [<span data-ttu-id="da356-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="da356-129">Configuration file schema for the .NET Framework</span></span>](index.md)
