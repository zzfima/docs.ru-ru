---
title: "&lt;Удалить&gt; элемент для &lt;configSections&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e6dfd1ac56070f55f30bd4bd093e1185486da295
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="7fd76-102">\<Удалите > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="7fd76-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="7fd76-103">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="7fd76-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="7fd76-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7fd76-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7fd76-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7fd76-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="7fd76-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалите >**</span><span class="sxs-lookup"><span data-stu-id="7fd76-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7fd76-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fd76-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="7fd76-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7fd76-108">Attribute</span></span>

|           | <span data-ttu-id="7fd76-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7fd76-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7fd76-110">**name**</span><span class="sxs-lookup"><span data-stu-id="7fd76-110">**name**</span></span>  | <span data-ttu-id="7fd76-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="7fd76-111">Required attribute.</span></span><br><br><span data-ttu-id="7fd76-112">Задает имя раздела или группы разделов.</span><span class="sxs-lookup"><span data-stu-id="7fd76-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7fd76-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="7fd76-113">Parent element</span></span>

|     | <span data-ttu-id="7fd76-114">Описание</span><span class="sxs-lookup"><span data-stu-id="7fd76-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7fd76-115">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="7fd76-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="7fd76-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="7fd76-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="7fd76-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7fd76-117">Child elements</span></span>

<span data-ttu-id="7fd76-118">Нет</span><span class="sxs-lookup"><span data-stu-id="7fd76-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7fd76-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="7fd76-119">Remarks</span></span>

<span data-ttu-id="7fd76-120">Можно использовать  **\<удалить >** элемента, который требуется удалить разделы и группы разделов из приложения, которые были определены на высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd76-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="7fd76-121">Пример</span><span class="sxs-lookup"><span data-stu-id="7fd76-121">Example</span></span>

<span data-ttu-id="7fd76-122">В следующем примере показано, как использовать  **\<удалить >** элемент в файле конфигурации приложения для удаления раздела, ранее определенные в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="7fd76-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="7fd76-123">В коде следующего файла конфигурации компьютера объявляется раздел  **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="7fd76-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="7fd76-124">В коде следующего файла конфигурации приложения удаляет  **\<sampleSection >** раздела.</span><span class="sxs-lookup"><span data-stu-id="7fd76-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="7fd76-125">После удаления приложение не может получить параметры в  **\<sampleSection >**.</span><span class="sxs-lookup"><span data-stu-id="7fd76-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7fd76-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="7fd76-126">Configuration file</span></span>

<span data-ttu-id="7fd76-127">Этот элемент может использоваться в файле конфигурации приложения, файле конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые находятся не на уровне папки приложения.</span><span class="sxs-lookup"><span data-stu-id="7fd76-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd76-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7fd76-128">See also</span></span>

[<span data-ttu-id="7fd76-129">Схема файла конфигурации для платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7fd76-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
