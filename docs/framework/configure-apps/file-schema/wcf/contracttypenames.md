---
title: '&lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a6923017f661cf463b4186e77e825195c6a9124d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="a1f51-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="a1f51-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="a1f51-103">Раздел конфигурации, в котором указан список имен типов контрактов. Это имена контрактов искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="a1f51-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a1f51-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="a1f51-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a1f51-105">Следует отметить, что в [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="a1f51-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="a1f51-106">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a1f51-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1f51-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a1f51-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f51-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1f51-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1f51-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a1f51-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a1f51-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a1f51-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1f51-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a1f51-111">Attributes</span></span>  
 <span data-ttu-id="a1f51-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a1f51-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a1f51-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1f51-113">Child Elements</span></span>  
  
|<span data-ttu-id="a1f51-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1f51-114">Element</span></span>|<span data-ttu-id="a1f51-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a1f51-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1f51-116">\<add></span><span class="sxs-lookup"><span data-stu-id="a1f51-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="a1f51-117">Имя типа контракта - это свойство, относящееся к набору критериев, обычно используемых для поиска службы.</span><span class="sxs-lookup"><span data-stu-id="a1f51-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1f51-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a1f51-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a1f51-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1f51-119">Element</span></span>|<span data-ttu-id="a1f51-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a1f51-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1f51-121">\<Критерии_поиска ></span><span class="sxs-lookup"><span data-stu-id="a1f51-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="a1f51-122">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="a1f51-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="a1f51-123">Критерии могут быть сгруппированы в критерии поиска (с указанием искомых служб, которые вы ищете) и критерии прекращения поиска (как долго поиска должно длиться).</span><span class="sxs-lookup"><span data-stu-id="a1f51-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1f51-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a1f51-124">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
