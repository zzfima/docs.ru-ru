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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a47417ded6e0917fadf2134eed5997d9d3b3d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="996b7-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="996b7-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="996b7-103">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="996b7-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="996b7-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="996b7-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="996b7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="996b7-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="996b7-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="996b7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="996b7-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="996b7-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="996b7-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="996b7-108">Attributes</span></span>  
 <span data-ttu-id="996b7-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="996b7-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="996b7-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="996b7-110">Child Elements</span></span>  
  
|<span data-ttu-id="996b7-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="996b7-111">Element</span></span>|<span data-ttu-id="996b7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="996b7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="996b7-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="996b7-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="996b7-114">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="996b7-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="996b7-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="996b7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="996b7-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="996b7-116">Element</span></span>|<span data-ttu-id="996b7-117">Описание</span><span class="sxs-lookup"><span data-stu-id="996b7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="996b7-118">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="996b7-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="996b7-119">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="996b7-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="996b7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="996b7-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="996b7-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="996b7-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="996b7-122">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="996b7-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
