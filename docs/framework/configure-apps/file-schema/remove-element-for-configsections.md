---
title: '&lt;Удалить&gt; элемент для &lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 11a930120c375616d73faae68a6d6807c2f633cb
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307231"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="2a283-102">\<Удалить > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="2a283-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="2a283-103">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="2a283-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="2a283-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="2a283-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="2a283-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2a283-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="2a283-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="2a283-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="2a283-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a283-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="2a283-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2a283-108">Attribute</span></span>

|           | <span data-ttu-id="2a283-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2a283-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="2a283-110">**name**</span><span class="sxs-lookup"><span data-stu-id="2a283-110">**name**</span></span>  | <span data-ttu-id="2a283-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="2a283-111">Required attribute.</span></span><br><br><span data-ttu-id="2a283-112">Задает имя раздела или группы разделов.</span><span class="sxs-lookup"><span data-stu-id="2a283-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="2a283-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="2a283-113">Parent element</span></span>

|     | <span data-ttu-id="2a283-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2a283-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2a283-115">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="2a283-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="2a283-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="2a283-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="2a283-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2a283-117">Child elements</span></span>

<span data-ttu-id="2a283-118">Нет</span><span class="sxs-lookup"><span data-stu-id="2a283-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="2a283-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a283-119">Remarks</span></span>

<span data-ttu-id="2a283-120">Можно использовать  **\<удалить >** элемент нужно удалить разделы и группы разделов из приложения, которые были определены на более высоком уровне в иерархии файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2a283-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="2a283-121">Пример</span><span class="sxs-lookup"><span data-stu-id="2a283-121">Example</span></span>

<span data-ttu-id="2a283-122">В следующем примере показано, как использовать  **\<удалить >** элемент в файле конфигурации приложения для удаления раздела, ранее определенные в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a283-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="2a283-123">В коде следующего файла конфигурации компьютера объявляет разделе  **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="2a283-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="2a283-124">В коде следующего файла конфигурации приложения удаляет  **\<sampleSection >** раздел.</span><span class="sxs-lookup"><span data-stu-id="2a283-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="2a283-125">После удаления приложения не удается получить параметры в  **\<sampleSection >**.</span><span class="sxs-lookup"><span data-stu-id="2a283-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="2a283-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="2a283-126">Configuration file</span></span>

<span data-ttu-id="2a283-127">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="2a283-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a283-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2a283-128">See also</span></span>

[<span data-ttu-id="2a283-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2a283-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
