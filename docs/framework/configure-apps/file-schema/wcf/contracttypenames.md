---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: d8f2b600b700a19cf587a6c8c4cc3f0e851edbd9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261287"
---
# <a name="contracttypenames"></a><span data-ttu-id="b01c7-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="b01c7-101">\<contractTypeNames></span></span>
<span data-ttu-id="b01c7-102">Раздел конфигурации, в котором указан список имен типов контрактов. Это имена контрактов искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="b01c7-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="b01c7-103">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="b01c7-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="b01c7-104">Обратите внимание на то, что в Windows Communication Foundation (WCF), конечной точки поддерживает только один контракт.</span><span class="sxs-lookup"><span data-stu-id="b01c7-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="b01c7-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b01c7-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b01c7-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b01c7-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b01c7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b01c7-107">Syntax</span></span>  
  
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
              <add name="String"
                   namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b01c7-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b01c7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b01c7-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b01c7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b01c7-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b01c7-110">Attributes</span></span>  
 <span data-ttu-id="b01c7-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b01c7-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b01c7-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b01c7-112">Child Elements</span></span>  
  
|<span data-ttu-id="b01c7-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="b01c7-113">Element</span></span>|<span data-ttu-id="b01c7-114">Описание:</span><span class="sxs-lookup"><span data-stu-id="b01c7-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b01c7-115">\<add></span><span class="sxs-lookup"><span data-stu-id="b01c7-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="b01c7-116">Имя типа контракта - это свойство, относящееся к набору критериев, обычно используемых для поиска службы.</span><span class="sxs-lookup"><span data-stu-id="b01c7-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b01c7-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b01c7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b01c7-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="b01c7-118">Element</span></span>|<span data-ttu-id="b01c7-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="b01c7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b01c7-120">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="b01c7-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="b01c7-121">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="b01c7-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b01c7-122">Критерии могут быть сгруппированы в критерии поиска (с указанием какие службы вы ищете) и (в том, как долго должен длиться поиск данных) критерии прекращения поиска.</span><span class="sxs-lookup"><span data-stu-id="b01c7-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b01c7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b01c7-123">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
