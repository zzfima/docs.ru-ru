---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efc7208aa51cbf6abdb2fe151d48071c0aa95b5c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089051"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="e764d-102">\<удалить элемент > для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="e764d-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="e764d-103">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="e764d-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="e764d-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e764d-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="e764d-105">&nbsp;&nbsp;[ **\<configSections >** ](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="e764d-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="e764d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**</span><span class="sxs-lookup"><span data-stu-id="e764d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e764d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e764d-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="e764d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e764d-108">Attribute</span></span>

|           | <span data-ttu-id="e764d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e764d-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="e764d-110">**name**</span><span class="sxs-lookup"><span data-stu-id="e764d-110">**name**</span></span>  | <span data-ttu-id="e764d-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e764d-111">Required attribute.</span></span><br><br><span data-ttu-id="e764d-112">Указывает имя раздела или группы разделов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="e764d-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="e764d-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="e764d-113">Parent element</span></span>

|     | <span data-ttu-id="e764d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e764d-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="e764d-115"> **\<configSections >** Дерев</span><span class="sxs-lookup"><span data-stu-id="e764d-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="e764d-116">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="e764d-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e764d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e764d-117">Child elements</span></span>

<span data-ttu-id="e764d-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e764d-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e764d-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="e764d-119">Remarks</span></span>

<span data-ttu-id="e764d-120">Элемент **\<удалить >** можно использовать для удаления разделов и групп разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e764d-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="e764d-121">Пример</span><span class="sxs-lookup"><span data-stu-id="e764d-121">Example</span></span>

<span data-ttu-id="e764d-122">В следующем примере показано использование элемента **\<Remove >** в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e764d-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="e764d-123">В следующем коде файла конфигурации компьютера объявляется раздел **\<самплесектион >** :</span><span class="sxs-lookup"><span data-stu-id="e764d-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="e764d-124">В следующем коде файла конфигурации приложения удаляется раздел **\<самплесектион >** .</span><span class="sxs-lookup"><span data-stu-id="e764d-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="e764d-125">После удаления приложение не сможет получить параметры в **\<самплесектион >** .</span><span class="sxs-lookup"><span data-stu-id="e764d-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e764d-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e764d-126">Configuration file</span></span>

<span data-ttu-id="e764d-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="e764d-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e764d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e764d-128">See also</span></span>

- [<span data-ttu-id="e764d-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e764d-129">Configuration file schema for the .NET Framework</span></span>](index.md)
