---
title: Элемент <configSections> для <configuration>
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155353"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="28b15-102">\<конфигурация> элемента для \<> конфигурации</span><span class="sxs-lookup"><span data-stu-id="28b15-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="28b15-103">Содержит раздел конфигурации и декларации пространства имен.</span><span class="sxs-lookup"><span data-stu-id="28b15-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="28b15-104">конфигурация &nbsp; &nbsp; [\*\* \<>\*\*](configuration-element.md) \*\* \<конфигурация>\*\*</span><span class="sxs-lookup"><span data-stu-id="28b15-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="28b15-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28b15-105">Attributes</span></span>

<span data-ttu-id="28b15-106">None</span><span class="sxs-lookup"><span data-stu-id="28b15-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="28b15-107">Родительский элемент</span><span class="sxs-lookup"><span data-stu-id="28b15-107">Parent element</span></span>

|     | <span data-ttu-id="28b15-108">Описание</span><span class="sxs-lookup"><span data-stu-id="28b15-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="28b15-109">**\<конфигурация>**</span><span class="sxs-lookup"><span data-stu-id="28b15-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="28b15-110">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28b15-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="28b15-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28b15-111">Child elements</span></span>

|     | <span data-ttu-id="28b15-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28b15-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="28b15-113">**\<раздел>**</span><span class="sxs-lookup"><span data-stu-id="28b15-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="28b15-114">Содержит декларацию раздела конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28b15-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="28b15-115">**\<разделГруппа>**</span><span class="sxs-lookup"><span data-stu-id="28b15-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="28b15-116">Определяет пространство имен для разделов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28b15-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="28b15-117">**\<удалить>**</span><span class="sxs-lookup"><span data-stu-id="28b15-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="28b15-118">Удаляет заранее определенный раздел или группу раздела.</span><span class="sxs-lookup"><span data-stu-id="28b15-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="28b15-119">**\<ясно>**</span><span class="sxs-lookup"><span data-stu-id="28b15-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="28b15-120">Очищает все ранее определенные разделы и группы разделов.</span><span class="sxs-lookup"><span data-stu-id="28b15-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="28b15-121">Remarks</span><span class="sxs-lookup"><span data-stu-id="28b15-121">Remarks</span></span>

<span data-ttu-id="28b15-122">Если этот элемент находится в файле конфигурации, он должен быть первым элементом элемента \*\* \<>конфигурации.\*\*</span><span class="sxs-lookup"><span data-stu-id="28b15-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="28b15-123">Пример</span><span class="sxs-lookup"><span data-stu-id="28b15-123">Example</span></span>

<span data-ttu-id="28b15-124">В следующем примере показано, как определить раздел конфигурации и определить параметры для этого раздела:</span><span class="sxs-lookup"><span data-stu-id="28b15-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="28b15-125">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="28b15-125">Configuration file</span></span>

<span data-ttu-id="28b15-126">Этот элемент может быть использован в файле конфигурации приложения, файле конфигурации машины *(Machine.config)* и файлах *Web.config,* которые не находятся на уровне каталога приложений.</span><span class="sxs-lookup"><span data-stu-id="28b15-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="28b15-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="28b15-127">See also</span></span>

- [<span data-ttu-id="28b15-128">Схема конфигурации файла для рамочного соглашения .NET</span><span class="sxs-lookup"><span data-stu-id="28b15-128">Configuration file schema for the .NET Framework</span></span>](index.md)
