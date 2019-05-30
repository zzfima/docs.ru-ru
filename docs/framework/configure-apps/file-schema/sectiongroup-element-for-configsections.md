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
ms.openlocfilehash: 750708483f9680745eef4531d86fa7ecaa329f51
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301197"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="5c30b-102">\<sectionGroup > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="5c30b-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="5c30b-103">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c30b-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="5c30b-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5c30b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5c30b-105">&nbsp;&nbsp;[ **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5c30b-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="5c30b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="5c30b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5c30b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c30b-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="5c30b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5c30b-108">Attribute</span></span>

|           | <span data-ttu-id="5c30b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="5c30b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5c30b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="5c30b-110">**name**</span></span>  | <span data-ttu-id="5c30b-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5c30b-111">Required attribute.</span></span><br><br><span data-ttu-id="5c30b-112">Задает имя группы раздела, который вы определяете.</span><span class="sxs-lookup"><span data-stu-id="5c30b-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5c30b-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="5c30b-113">Parent element</span></span>

|     | <span data-ttu-id="5c30b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5c30b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5c30b-115"> *\*\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="5c30b-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="5c30b-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="5c30b-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5c30b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5c30b-117">Child elements</span></span>

|     | <span data-ttu-id="5c30b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5c30b-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5c30b-119"> *\*\<раздел >** </span><span class="sxs-lookup"><span data-stu-id="5c30b-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="5c30b-120">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5c30b-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5c30b-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c30b-121">Remarks</span></span>

<span data-ttu-id="5c30b-122">Объявление группы разделов создает тег контейнера для разделов конфигурации и гарантирует отсутствие конфликтов имен с разделами конфигурации, определенными другим пользователем.</span><span class="sxs-lookup"><span data-stu-id="5c30b-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="5c30b-123">Можно вложить  **\<sectionGroup >** элементов друг с другом.</span><span class="sxs-lookup"><span data-stu-id="5c30b-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="5c30b-124">Пример</span><span class="sxs-lookup"><span data-stu-id="5c30b-124">Example</span></span>

<span data-ttu-id="5c30b-125">В следующем примере показано, как определения группы разделов и объявления разделов внутри группы:</span><span class="sxs-lookup"><span data-stu-id="5c30b-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="5c30b-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="5c30b-126">Configuration file</span></span>

<span data-ttu-id="5c30b-127">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="5c30b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5c30b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5c30b-128">See also</span></span>

- [<span data-ttu-id="5c30b-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5c30b-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
