---
title: "&lt;add&gt; для &lt;contractTypeNames&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bebea15e6d1f24c95905355dbced33aa9c5150f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="40635-102">&lt;add&gt; для &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="40635-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="40635-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="40635-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="40635-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="40635-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="40635-105">Следует отметить, что в [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="40635-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="40635-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="40635-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="40635-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="40635-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40635-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40635-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40635-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40635-109">Attributes and Elements</span></span>  
 <span data-ttu-id="40635-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40635-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40635-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40635-111">Attributes</span></span>  
  
|<span data-ttu-id="40635-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40635-112">Attribute</span></span>|<span data-ttu-id="40635-113">Описание</span><span class="sxs-lookup"><span data-stu-id="40635-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40635-114">имя</span><span class="sxs-lookup"><span data-stu-id="40635-114">name</span></span>|<span data-ttu-id="40635-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="40635-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="40635-116">namespace</span><span class="sxs-lookup"><span data-stu-id="40635-116">namespace</span></span>|<span data-ttu-id="40635-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="40635-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40635-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40635-118">Child Elements</span></span>  
 <span data-ttu-id="40635-119">Нет</span><span class="sxs-lookup"><span data-stu-id="40635-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40635-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40635-120">Parent Elements</span></span>  
  
|<span data-ttu-id="40635-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="40635-121">Element</span></span>|<span data-ttu-id="40635-122">Описание</span><span class="sxs-lookup"><span data-stu-id="40635-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40635-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="40635-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="40635-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="40635-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40635-125">См. также</span><span class="sxs-lookup"><span data-stu-id="40635-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
