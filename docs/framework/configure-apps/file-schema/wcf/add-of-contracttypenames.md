---
title: <add> из <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: fa67d2ec21494bb3d84861f4c2e2e39151aac28f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55253723"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="3d8cc-102">\<Добавить > из \<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="3d8cc-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3d8cc-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3d8cc-105">Обратите внимание на то, что в Windows Communication Foundation (WCF), конечной точки поддерживает только один контракт.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="3d8cc-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3d8cc-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d8cc-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8cc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d8cc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d8cc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3d8cc-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d8cc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3d8cc-111">Attributes</span></span>  
  
|<span data-ttu-id="3d8cc-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3d8cc-112">Attribute</span></span>|<span data-ttu-id="3d8cc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8cc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d8cc-114">имя</span><span class="sxs-lookup"><span data-stu-id="3d8cc-114">name</span></span>|<span data-ttu-id="3d8cc-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="3d8cc-116">namespace</span><span class="sxs-lookup"><span data-stu-id="3d8cc-116">namespace</span></span>|<span data-ttu-id="3d8cc-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d8cc-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-118">Child Elements</span></span>  
 <span data-ttu-id="3d8cc-119">Нет</span><span class="sxs-lookup"><span data-stu-id="3d8cc-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d8cc-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3d8cc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d8cc-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="3d8cc-121">Element</span></span>|<span data-ttu-id="3d8cc-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="3d8cc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d8cc-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="3d8cc-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="3d8cc-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="3d8cc-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d8cc-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3d8cc-125">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
