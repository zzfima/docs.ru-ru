---
title: "&lt;sectionGroup&gt; элемент для &lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 654a6e639a24120e1e0c993ebe36f14e75b46a12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="8501b-102">\<sectionGroup > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="8501b-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="8501b-103">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8501b-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="8501b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8501b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8501b-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8501b-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="8501b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="8501b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8501b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8501b-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="8501b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8501b-108">Attribute</span></span>

|           | <span data-ttu-id="8501b-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8501b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8501b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="8501b-110">**name**</span></span>  | <span data-ttu-id="8501b-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8501b-111">Required attribute.</span></span><br><br><span data-ttu-id="8501b-112">Указывает имя группы разделов, который вы определяете.</span><span class="sxs-lookup"><span data-stu-id="8501b-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8501b-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="8501b-113">Parent element</span></span>

|     | <span data-ttu-id="8501b-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="8501b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8501b-115">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="8501b-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="8501b-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="8501b-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8501b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8501b-117">Child elements</span></span>

|     | <span data-ttu-id="8501b-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="8501b-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8501b-119">**\<раздел >**</span><span class="sxs-lookup"><span data-stu-id="8501b-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="8501b-120">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8501b-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8501b-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="8501b-121">Remarks</span></span>

<span data-ttu-id="8501b-122">Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными пользователем или процессом.</span><span class="sxs-lookup"><span data-stu-id="8501b-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="8501b-123">Можно вложить  **\<sectionGroup >** элементов друг в друге.</span><span class="sxs-lookup"><span data-stu-id="8501b-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="8501b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="8501b-124">Example</span></span>

<span data-ttu-id="8501b-125">Приведенный ниже показан способ определения группы разделов и объявления разделов внутри группы.</span><span class="sxs-lookup"><span data-stu-id="8501b-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="8501b-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="8501b-126">Configuration file</span></span>

<span data-ttu-id="8501b-127">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="8501b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8501b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8501b-128">See also</span></span>

[<span data-ttu-id="8501b-129">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8501b-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
