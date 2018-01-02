---
title: '&lt;System.Runtime.Serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab66252ebc5b87c197b3e4ac7b6def9355e5f201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="c46db-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="c46db-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="c46db-103">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="c46db-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="c46db-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="c46db-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46db-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c46db-105">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c46db-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c46db-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c46db-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c46db-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c46db-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c46db-108">Attributes</span></span>  
 <span data-ttu-id="c46db-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c46db-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c46db-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c46db-110">Child Elements</span></span>  
  
|<span data-ttu-id="c46db-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="c46db-111">Element</span></span>|<span data-ttu-id="c46db-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="c46db-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c46db-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="c46db-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="c46db-114">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="c46db-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c46db-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c46db-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c46db-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="c46db-116">Element</span></span>|<span data-ttu-id="c46db-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="c46db-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c46db-118">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="c46db-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="c46db-119">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="c46db-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c46db-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c46db-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="c46db-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c46db-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="c46db-122">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="c46db-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
