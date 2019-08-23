---
title: Элемент <remove> для <configSections>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4ff9bb537a31e28dbd4b878c1bc04c96262f85ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927459"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="b4238-102">\<Удаление элемента > для \<configSections ></span><span class="sxs-lookup"><span data-stu-id="b4238-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="b4238-103">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="b4238-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="b4238-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b4238-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="b4238-105">&nbsp;&nbsp;[ **\<> configSections**](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b4238-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="b4238-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="b4238-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b4238-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4238-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="b4238-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b4238-108">Attribute</span></span>

|           | <span data-ttu-id="b4238-109">Описание</span><span class="sxs-lookup"><span data-stu-id="b4238-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="b4238-110">**name**</span><span class="sxs-lookup"><span data-stu-id="b4238-110">**name**</span></span>  | <span data-ttu-id="b4238-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b4238-111">Required attribute.</span></span><br><br><span data-ttu-id="b4238-112">Указывает имя раздела или группы разделов, которые нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="b4238-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="b4238-113">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="b4238-113">Parent element</span></span>

|     | <span data-ttu-id="b4238-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b4238-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b4238-115">элемент  **>\<configSections**</span><span class="sxs-lookup"><span data-stu-id="b4238-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="b4238-116">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b4238-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b4238-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b4238-117">Child elements</span></span>

<span data-ttu-id="b4238-118">None</span><span class="sxs-lookup"><span data-stu-id="b4238-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="b4238-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4238-119">Remarks</span></span>

<span data-ttu-id="b4238-120">Элемент  **\<Remove >** можно использовать для удаления разделов и групп разделов из приложения, которые были определены на более высоком уровне в иерархии файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b4238-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="b4238-121">Пример</span><span class="sxs-lookup"><span data-stu-id="b4238-121">Example</span></span>

<span data-ttu-id="b4238-122">В следующем примере показано,  **\<** как использовать элемент remove > в файле конфигурации приложения для удаления раздела, ранее определенного в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="b4238-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="b4238-123">Следующий код файла конфигурации компьютера объявляет раздел  **\<самплесектион >** :</span><span class="sxs-lookup"><span data-stu-id="b4238-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="b4238-124">В следующем коде файла конфигурации приложения удаляется  **\<раздел > самплесектион** .</span><span class="sxs-lookup"><span data-stu-id="b4238-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="b4238-125">После удаления приложение не сможет получить параметры в  **\<самплесектион >** .</span><span class="sxs-lookup"><span data-stu-id="b4238-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b4238-126">файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="b4238-126">Configuration file</span></span>

<span data-ttu-id="b4238-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="b4238-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b4238-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b4238-128">See also</span></span>

- [<span data-ttu-id="b4238-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b4238-129">Configuration file schema for the .NET Framework</span></span>](index.md)
