---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214826"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="60e34-102">Элемент > \<configSections для \<конфигурации ></span><span class="sxs-lookup"><span data-stu-id="60e34-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="60e34-103">Содержит раздел конфигурации и объявления пространств имен.</span><span class="sxs-lookup"><span data-stu-id="60e34-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="60e34-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="60e34-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="60e34-105">&nbsp;&nbsp; **\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="60e34-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="60e34-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="60e34-106">Attributes</span></span>

<span data-ttu-id="60e34-107">Нет</span><span class="sxs-lookup"><span data-stu-id="60e34-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="60e34-108">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="60e34-108">Parent element</span></span>

|     | <span data-ttu-id="60e34-109">Описание</span><span class="sxs-lookup"><span data-stu-id="60e34-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="60e34-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="60e34-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="60e34-111">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60e34-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="60e34-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="60e34-112">Child elements</span></span>

|     | <span data-ttu-id="60e34-113">Описание</span><span class="sxs-lookup"><span data-stu-id="60e34-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="60e34-114"> **\<разделе >** </span><span class="sxs-lookup"><span data-stu-id="60e34-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="60e34-115">Содержит объявление раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="60e34-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="60e34-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="60e34-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="60e34-117">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="60e34-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="60e34-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="60e34-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="60e34-119">Удаляет предопределенный раздел или группу разделов.</span><span class="sxs-lookup"><span data-stu-id="60e34-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="60e34-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="60e34-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="60e34-121">Удаляет все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="60e34-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="60e34-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="60e34-122">Remarks</span></span>

<span data-ttu-id="60e34-123">Если этот элемент находится в файле конфигурации, он должен быть первым дочерним элементом элемента **конфигурации\<>** .</span><span class="sxs-lookup"><span data-stu-id="60e34-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="60e34-124">Пример</span><span class="sxs-lookup"><span data-stu-id="60e34-124">Example</span></span>

<span data-ttu-id="60e34-125">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="60e34-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
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

## <a name="configuration-file"></a><span data-ttu-id="60e34-126">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="60e34-126">Configuration file</span></span>

<span data-ttu-id="60e34-127">Этот элемент можно использовать в файле конфигурации приложения, файле конфигурации компьютера (*Machine. config*) и файлах *Web. config* , которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="60e34-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="60e34-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="60e34-128">See also</span></span>

- [<span data-ttu-id="60e34-129">Схема файла конфигурации для .NET Framework</span><span class="sxs-lookup"><span data-stu-id="60e34-129">Configuration file schema for the .NET Framework</span></span>](index.md)
