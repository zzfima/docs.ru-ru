---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: b67f51e634d1294830690dad8c8cffb1fc9a6cd2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399465"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="11719-102">\<System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="11719-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="11719-103">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="11719-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="11719-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="11719-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="11719-105">&nbsp;&nbsp; **\<System. Runtime. Serialization >**</span><span class="sxs-lookup"><span data-stu-id="11719-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11719-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11719-106">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11719-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="11719-107">Attributes and Elements</span></span>  
 <span data-ttu-id="11719-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="11719-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11719-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="11719-109">Attributes</span></span>  
 <span data-ttu-id="11719-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="11719-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="11719-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="11719-111">Child Elements</span></span>  
  
|<span data-ttu-id="11719-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="11719-112">Element</span></span>|<span data-ttu-id="11719-113">Описание</span><span class="sxs-lookup"><span data-stu-id="11719-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11719-114">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="11719-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="11719-115">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="11719-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="11719-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="11719-116">Parent Elements</span></span>  
  
|<span data-ttu-id="11719-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="11719-117">Element</span></span>|<span data-ttu-id="11719-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="11719-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11719-119">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="11719-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="11719-120">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="11719-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11719-121">См. также</span><span class="sxs-lookup"><span data-stu-id="11719-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="11719-122">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="11719-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="11719-123">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="11719-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
 