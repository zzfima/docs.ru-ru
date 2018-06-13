---
title: '&lt;add&gt; для &lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 159ab5a40a69c075b648a0c161babe604d13377b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750197"
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="a6168-102">&lt;add&gt; для &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="a6168-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="a6168-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="a6168-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a6168-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="a6168-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a6168-105">Обратите внимание, что в Windows Communication Foundation (WCF), конечная точка поддерживает только один контракт.</span><span class="sxs-lookup"><span data-stu-id="a6168-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="a6168-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a6168-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6168-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a6168-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6168-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6168-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6168-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6168-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6168-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a6168-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6168-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6168-111">Attributes</span></span>  
  
|<span data-ttu-id="a6168-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a6168-112">Attribute</span></span>|<span data-ttu-id="a6168-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a6168-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6168-114">имя</span><span class="sxs-lookup"><span data-stu-id="a6168-114">name</span></span>|<span data-ttu-id="a6168-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a6168-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="a6168-116">namespace</span><span class="sxs-lookup"><span data-stu-id="a6168-116">namespace</span></span>|<span data-ttu-id="a6168-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a6168-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6168-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6168-118">Child Elements</span></span>  
 <span data-ttu-id="a6168-119">Нет</span><span class="sxs-lookup"><span data-stu-id="a6168-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6168-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6168-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a6168-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6168-121">Element</span></span>|<span data-ttu-id="a6168-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a6168-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6168-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="a6168-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="a6168-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="a6168-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6168-125">См. также</span><span class="sxs-lookup"><span data-stu-id="a6168-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
