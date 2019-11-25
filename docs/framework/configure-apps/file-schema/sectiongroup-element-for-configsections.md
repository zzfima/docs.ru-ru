---
title: Элемент <sectionGroup> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 746a997e162b0fd370a249b8d039be623b57d77f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089005"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="c8953-102">элемент \<sectionGroup > для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="c8953-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="c8953-103">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8953-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="c8953-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8953-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="c8953-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="c8953-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="c8953-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="c8953-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c8953-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8953-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="c8953-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8953-108">Attribute</span></span>

|           | <span data-ttu-id="c8953-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c8953-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c8953-110">**name**</span><span class="sxs-lookup"><span data-stu-id="c8953-110">**name**</span></span>  | <span data-ttu-id="c8953-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="c8953-111">Required attribute.</span></span><br><br><span data-ttu-id="c8953-112">Указывает имя определяемой группы разделов.</span><span class="sxs-lookup"><span data-stu-id="c8953-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c8953-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="c8953-113">Parent element</span></span>

|     | <span data-ttu-id="c8953-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c8953-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8953-115"> **\<configSections >** Дерев</span><span class="sxs-lookup"><span data-stu-id="c8953-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="c8953-116">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="c8953-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c8953-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8953-117">Child elements</span></span>

|     | <span data-ttu-id="c8953-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c8953-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8953-119"> **\<разделе >** </span><span class="sxs-lookup"><span data-stu-id="c8953-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="c8953-120">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8953-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c8953-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="c8953-121">Remarks</span></span>

<span data-ttu-id="c8953-122">Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="c8953-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="c8953-123">Элементы **\<sectionGroup >** можно вкладывать друг в друга.</span><span class="sxs-lookup"><span data-stu-id="c8953-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="c8953-124">Пример</span><span class="sxs-lookup"><span data-stu-id="c8953-124">Example</span></span>

<span data-ttu-id="c8953-125">В следующем примере показано, как объявить группу разделов и объявить разделы в группе разделов:</span><span class="sxs-lookup"><span data-stu-id="c8953-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c8953-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c8953-126">Configuration file</span></span>

<span data-ttu-id="c8953-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="c8953-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8953-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c8953-128">See also</span></span>

- [<span data-ttu-id="c8953-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c8953-129">Configuration file schema for the .NET Framework</span></span>](index.md)
