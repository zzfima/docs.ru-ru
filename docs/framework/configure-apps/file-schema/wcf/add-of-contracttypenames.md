---
title: <add> из <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 856298cb0639cf19b941f326b5b9a25aa6663088
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091321"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="139f4-102">\<Добавить > из \<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="139f4-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="139f4-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="139f4-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="139f4-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="139f4-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="139f4-105">Обратите внимание на то, что в Windows Communication Foundation (WCF), конечной точки поддерживает только один контракт.</span><span class="sxs-lookup"><span data-stu-id="139f4-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="139f4-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="139f4-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="139f4-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="139f4-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="139f4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="139f4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="139f4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="139f4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="139f4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="139f4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="139f4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="139f4-111">Attributes</span></span>  
  
|<span data-ttu-id="139f4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="139f4-112">Attribute</span></span>|<span data-ttu-id="139f4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="139f4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="139f4-114">имя</span><span class="sxs-lookup"><span data-stu-id="139f4-114">name</span></span>|<span data-ttu-id="139f4-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="139f4-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="139f4-116">namespace</span><span class="sxs-lookup"><span data-stu-id="139f4-116">namespace</span></span>|<span data-ttu-id="139f4-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="139f4-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="139f4-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="139f4-118">Child Elements</span></span>  
 <span data-ttu-id="139f4-119">Нет</span><span class="sxs-lookup"><span data-stu-id="139f4-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="139f4-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="139f4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="139f4-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="139f4-121">Element</span></span>|<span data-ttu-id="139f4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="139f4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="139f4-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="139f4-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="139f4-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="139f4-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="139f4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="139f4-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
