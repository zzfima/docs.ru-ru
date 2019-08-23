---
title: Элемент <sectionGroup> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4e28e8ccea1090e6a5704b541e09dc11681278ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920653"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="cc4e1-102">\<элемент sectionGroup > для \<> configSections</span><span class="sxs-lookup"><span data-stu-id="cc4e1-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="cc4e1-103">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="cc4e1-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="cc4e1-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="cc4e1-105">&nbsp;&nbsp;[ **\<> configSections**](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="cc4e1-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="cc4e1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="cc4e1-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc4e1-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="cc4e1-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cc4e1-108">Attribute</span></span>

|           | <span data-ttu-id="cc4e1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="cc4e1-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="cc4e1-110">**name**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-110">**name**</span></span>  | <span data-ttu-id="cc4e1-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-111">Required attribute.</span></span><br><br><span data-ttu-id="cc4e1-112">Указывает имя определяемой группы разделов.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="cc4e1-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="cc4e1-113">Parent element</span></span>

|     | <span data-ttu-id="cc4e1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cc4e1-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cc4e1-115">элемент  **>\<configSections**</span><span class="sxs-lookup"><span data-stu-id="cc4e1-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="cc4e1-116">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cc4e1-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cc4e1-117">Child elements</span></span>

|     | <span data-ttu-id="cc4e1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="cc4e1-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="cc4e1-119"> **\<раздел >** </span><span class="sxs-lookup"><span data-stu-id="cc4e1-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="cc4e1-120">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cc4e1-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc4e1-121">Remarks</span></span>

<span data-ttu-id="cc4e1-122">Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="cc4e1-123">Элементы  **\<sectionGroup >** можно вкладывать друг в друга.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="cc4e1-124">Пример</span><span class="sxs-lookup"><span data-stu-id="cc4e1-124">Example</span></span>

<span data-ttu-id="cc4e1-125">В следующем примере показано, как объявить группу разделов и объявить разделы в группе разделов:</span><span class="sxs-lookup"><span data-stu-id="cc4e1-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="cc4e1-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="cc4e1-126">Configuration file</span></span>

<span data-ttu-id="cc4e1-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="cc4e1-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc4e1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cc4e1-128">See also</span></span>

- [<span data-ttu-id="cc4e1-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc4e1-129">Configuration file schema for the .NET Framework</span></span>](index.md)
