---
title: <remove> - элемент для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 9ceffd3194c7df41f12ac6cd6b589602965b4920
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279101"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="8b8be-102">\<Удалить > элемент для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="8b8be-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="8b8be-103">Удаляет предварительно определенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="8b8be-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="8b8be-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="8b8be-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="8b8be-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8b8be-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="8b8be-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="8b8be-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8b8be-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b8be-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="8b8be-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8b8be-108">Attribute</span></span>

|           | <span data-ttu-id="8b8be-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="8b8be-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8b8be-110">**name**</span><span class="sxs-lookup"><span data-stu-id="8b8be-110">**name**</span></span>  | <span data-ttu-id="8b8be-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8b8be-111">Required attribute.</span></span><br><br><span data-ttu-id="8b8be-112">Задает имя раздела или группы разделов.</span><span class="sxs-lookup"><span data-stu-id="8b8be-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8b8be-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="8b8be-113">Parent element</span></span>

|     | <span data-ttu-id="8b8be-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="8b8be-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8b8be-115">**\<configSections >** элемент</span><span class="sxs-lookup"><span data-stu-id="8b8be-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="8b8be-116">Содержит раздел конфигурации и пространства имен объявления.</span><span class="sxs-lookup"><span data-stu-id="8b8be-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8b8be-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8b8be-117">Child elements</span></span>

<span data-ttu-id="8b8be-118">Нет</span><span class="sxs-lookup"><span data-stu-id="8b8be-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8b8be-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b8be-119">Remarks</span></span>

<span data-ttu-id="8b8be-120">Можно использовать  **\<удалить >** элемент нужно удалить разделы и группы разделов из приложения, которые были определены на более высоком уровне в иерархии файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8b8be-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="8b8be-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8b8be-121">Example</span></span>

<span data-ttu-id="8b8be-122">В следующем примере показано, как использовать  **\<удалить >** элемент в файле конфигурации приложения для удаления раздела, ранее определенные в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="8b8be-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="8b8be-123">В коде следующего файла конфигурации компьютера объявляет разделе  **\<sampleSection >**:</span><span class="sxs-lookup"><span data-stu-id="8b8be-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="8b8be-124">В коде следующего файла конфигурации приложения удаляет  **\<sampleSection >** раздел.</span><span class="sxs-lookup"><span data-stu-id="8b8be-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="8b8be-125">После удаления приложения не удается получить параметры в  **\<sampleSection >**.</span><span class="sxs-lookup"><span data-stu-id="8b8be-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8b8be-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="8b8be-126">Configuration file</span></span>

<span data-ttu-id="8b8be-127">Этот элемент может использоваться в файле конфигурации приложения, файл конфигурации компьютера (*Machine.config*), и *Web.config* файлы, которые не на уровне каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="8b8be-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b8be-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8b8be-128">See also</span></span>

- [<span data-ttu-id="8b8be-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b8be-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
