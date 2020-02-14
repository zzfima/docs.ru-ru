---
title: Элемент <sectionGroup> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215261"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="a1d49-102">элемент \<sectionGroup > для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="a1d49-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="a1d49-103">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1d49-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="a1d49-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a1d49-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="a1d49-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a1d49-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="a1d49-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="a1d49-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a1d49-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1d49-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="a1d49-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a1d49-108">Attribute</span></span>

|           | <span data-ttu-id="a1d49-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a1d49-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="a1d49-110">**name**</span><span class="sxs-lookup"><span data-stu-id="a1d49-110">**name**</span></span>  | <span data-ttu-id="a1d49-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a1d49-111">Required attribute.</span></span><br><br><span data-ttu-id="a1d49-112">Указывает имя определяемой группы разделов.</span><span class="sxs-lookup"><span data-stu-id="a1d49-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="a1d49-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="a1d49-113">Parent element</span></span>

|     | <span data-ttu-id="a1d49-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a1d49-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a1d49-115"> **\<configSections >** Дерев</span><span class="sxs-lookup"><span data-stu-id="a1d49-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="a1d49-116">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="a1d49-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a1d49-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1d49-117">Child elements</span></span>

|     | <span data-ttu-id="a1d49-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a1d49-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a1d49-119"> **\<разделе >** </span><span class="sxs-lookup"><span data-stu-id="a1d49-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="a1d49-120">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1d49-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a1d49-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="a1d49-121">Remarks</span></span>

<span data-ttu-id="a1d49-122">Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными другими пользователями.</span><span class="sxs-lookup"><span data-stu-id="a1d49-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="a1d49-123">Элементы **\<sectionGroup >** можно вкладывать друг в друга.</span><span class="sxs-lookup"><span data-stu-id="a1d49-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="a1d49-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a1d49-124">Example</span></span>

<span data-ttu-id="a1d49-125">В следующем примере показано, как объявить группу разделов и объявить разделы в группе разделов:</span><span class="sxs-lookup"><span data-stu-id="a1d49-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="a1d49-126">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="a1d49-126">Configuration file</span></span>

<span data-ttu-id="a1d49-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="a1d49-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1d49-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="a1d49-128">See also</span></span>

- [<span data-ttu-id="a1d49-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a1d49-129">Configuration file schema for the .NET Framework</span></span>](index.md)
