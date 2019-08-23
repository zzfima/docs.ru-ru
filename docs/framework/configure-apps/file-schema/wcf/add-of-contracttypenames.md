---
title: <add> из <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 24f1478b99aef909ae93f87a70be257e9ba10d7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926751"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="45203-102">\<Добавление > \<> контракттипенамес</span><span class="sxs-lookup"><span data-stu-id="45203-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="45203-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="45203-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="45203-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="45203-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="45203-105">Обратите внимание, что в Windows Communication Foundation (WCF) конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="45203-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="45203-106">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="45203-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="45203-107">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="45203-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45203-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45203-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45203-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="45203-109">Attributes and Elements</span></span>  
 <span data-ttu-id="45203-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="45203-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45203-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="45203-111">Attributes</span></span>  
  
|<span data-ttu-id="45203-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="45203-112">Attribute</span></span>|<span data-ttu-id="45203-113">Описание</span><span class="sxs-lookup"><span data-stu-id="45203-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45203-114">имя</span><span class="sxs-lookup"><span data-stu-id="45203-114">name</span></span>|<span data-ttu-id="45203-115">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="45203-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="45203-116">namespace</span><span class="sxs-lookup"><span data-stu-id="45203-116">namespace</span></span>|<span data-ttu-id="45203-117">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="45203-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45203-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="45203-118">Child Elements</span></span>  
 <span data-ttu-id="45203-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="45203-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45203-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="45203-120">Parent Elements</span></span>  
  
|<span data-ttu-id="45203-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="45203-121">Element</span></span>|<span data-ttu-id="45203-122">Описание</span><span class="sxs-lookup"><span data-stu-id="45203-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45203-123">\<Контракттипенамес ></span><span class="sxs-lookup"><span data-stu-id="45203-123">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="45203-124">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="45203-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45203-125">См. также</span><span class="sxs-lookup"><span data-stu-id="45203-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
