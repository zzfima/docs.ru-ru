---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 4ec5cd19ccdc5c21a3caf426520d51442dc5ab3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938921"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="86d88-102">\<System. Runtime. Serialization ></span><span class="sxs-lookup"><span data-stu-id="86d88-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="86d88-103">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="86d88-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="86d88-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="86d88-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d88-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86d88-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86d88-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86d88-106">Attributes and Elements</span></span>  
 <span data-ttu-id="86d88-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86d88-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86d88-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86d88-108">Attributes</span></span>  
 <span data-ttu-id="86d88-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="86d88-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86d88-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86d88-110">Child Elements</span></span>  
  
|<span data-ttu-id="86d88-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="86d88-111">Element</span></span>|<span data-ttu-id="86d88-112">Описание</span><span class="sxs-lookup"><span data-stu-id="86d88-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86d88-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="86d88-113">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="86d88-114">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="86d88-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86d88-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86d88-115">Parent Elements</span></span>  
  
|<span data-ttu-id="86d88-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="86d88-116">Element</span></span>|<span data-ttu-id="86d88-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="86d88-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86d88-118">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="86d88-118">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="86d88-119">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="86d88-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86d88-120">См. также</span><span class="sxs-lookup"><span data-stu-id="86d88-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="86d88-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="86d88-121">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="86d88-122">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="86d88-122">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
