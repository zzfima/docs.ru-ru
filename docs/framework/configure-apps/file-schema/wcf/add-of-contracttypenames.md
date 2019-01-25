---
title: '&lt;add&gt; для &lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: cf9a1ae28b53b841ac5d8d85d31e1548e36369ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735731"
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="ba464-102">&lt;add&gt; для &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="ba464-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="ba464-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="ba464-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="ba464-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="ba464-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="ba464-105">Обратите внимание на то, что в Windows Communication Foundation (WCF), конечной точки поддерживает только один контракт.</span><span class="sxs-lookup"><span data-stu-id="ba464-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="ba464-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ba464-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="ba464-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ba464-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba464-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba464-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba464-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba464-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ba464-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba464-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba464-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba464-111">Attributes</span></span>  
  
|<span data-ttu-id="ba464-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba464-112">Attribute</span></span>|<span data-ttu-id="ba464-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ba464-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba464-114">имя</span><span class="sxs-lookup"><span data-stu-id="ba464-114">name</span></span>|<span data-ttu-id="ba464-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="ba464-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="ba464-116">namespace</span><span class="sxs-lookup"><span data-stu-id="ba464-116">namespace</span></span>|<span data-ttu-id="ba464-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="ba464-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba464-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba464-118">Child Elements</span></span>  
 <span data-ttu-id="ba464-119">Нет</span><span class="sxs-lookup"><span data-stu-id="ba464-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba464-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba464-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ba464-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba464-121">Element</span></span>|<span data-ttu-id="ba464-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ba464-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba464-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="ba464-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="ba464-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="ba464-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba464-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ba464-125">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
