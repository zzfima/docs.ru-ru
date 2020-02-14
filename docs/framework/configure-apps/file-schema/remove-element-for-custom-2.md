---
title: элемент <remove> для NameValueSectionHandler и DictionarySectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214759"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="9bfbc-102">\<удалить элемент > для NameValueSectionHandler и DictionarySectionHandler</span><span class="sxs-lookup"><span data-stu-id="9bfbc-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="9bfbc-103">Удаляет ранее определенный параметр.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="9bfbc-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9bfbc-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="9bfbc-105">&nbsp;&nbsp;[ **\<sectionName >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="9bfbc-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="9bfbc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="9bfbc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9bfbc-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bfbc-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="9bfbc-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9bfbc-108">Attribute</span></span>

|           | <span data-ttu-id="9bfbc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9bfbc-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9bfbc-110">**key**</span><span class="sxs-lookup"><span data-stu-id="9bfbc-110">**key**</span></span>   | <span data-ttu-id="9bfbc-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-111">Required attribute.</span></span><br><br><span data-ttu-id="9bfbc-112">Задает имя удаляемого параметра.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9bfbc-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="9bfbc-113">Parent element</span></span>

| <span data-ttu-id="9bfbc-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="9bfbc-114">Element</span></span> | <span data-ttu-id="9bfbc-115">Описание</span><span class="sxs-lookup"><span data-stu-id="9bfbc-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="9bfbc-116"> **\<sectionName >** Дерев</span><span class="sxs-lookup"><span data-stu-id="9bfbc-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="9bfbc-117">Определяет параметры для пользовательских разделов конфигурации, использующих классы <xref:System.Configuration.NameValueSectionHandler> и <xref:System.Configuration.DictionarySectionHandler>.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9bfbc-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9bfbc-118">Child elements</span></span>

<span data-ttu-id="9bfbc-119">Нет</span><span class="sxs-lookup"><span data-stu-id="9bfbc-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="9bfbc-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="9bfbc-120">Remarks</span></span>

<span data-ttu-id="9bfbc-121">Элемент **\<удалить >** можно использовать для удаления из приложения параметров, определенных на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="9bfbc-122">Пример</span><span class="sxs-lookup"><span data-stu-id="9bfbc-122">Example</span></span>

<span data-ttu-id="9bfbc-123">В следующем примере показано использование элемента **\<Remove >** в файле конфигурации приложения для удаления параметров, ранее определенных в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="9bfbc-124">Следующий код файла конфигурации компьютера объявляет раздел **\<мисектион >** и добавляет в него два параметра: `key1` и `key2`.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="9bfbc-125">Следующий код файла конфигурации приложения удаляет параметр `key2` из **\<мисектион >** :</span><span class="sxs-lookup"><span data-stu-id="9bfbc-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="9bfbc-126">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="9bfbc-126">Configuration file</span></span>

<span data-ttu-id="9bfbc-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="9bfbc-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bfbc-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="9bfbc-128">See also</span></span>

- [<span data-ttu-id="9bfbc-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bfbc-129">Configuration file schema for the .NET Framework</span></span>](index.md)
