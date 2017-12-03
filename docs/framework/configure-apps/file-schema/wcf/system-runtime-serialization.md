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
ms.openlocfilehash: 8a6eb2b152f2ab11bbe0e08ff1ad22f94d45057e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="e1fde-102">&lt;System.Runtime.Serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="e1fde-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="e1fde-103">Представляет корневой элемент для раздела пространства имен <xref:System.Runtime.Serialization> и содержит элементы для установки параметров <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e1fde-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="e1fde-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="e1fde-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1fde-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1fde-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1fde-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1fde-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e1fde-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1fde-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1fde-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1fde-108">Attributes</span></span>  
 <span data-ttu-id="e1fde-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1fde-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1fde-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1fde-110">Child Elements</span></span>  
  
|<span data-ttu-id="e1fde-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1fde-111">Element</span></span>|<span data-ttu-id="e1fde-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e1fde-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1fde-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="e1fde-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="e1fde-114">Включает добавление известных типов при десериализации.</span><span class="sxs-lookup"><span data-stu-id="e1fde-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1fde-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1fde-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e1fde-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1fde-116">Element</span></span>|<span data-ttu-id="e1fde-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e1fde-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1fde-118">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="e1fde-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="e1fde-119">Элемент конфигурации верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="e1fde-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1fde-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e1fde-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="e1fde-121">Использование контрактов данных</span><span class="sxs-lookup"><span data-stu-id="e1fde-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="e1fde-122">Известные типы контрактов данных</span><span class="sxs-lookup"><span data-stu-id="e1fde-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
