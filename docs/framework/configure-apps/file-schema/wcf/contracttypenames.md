---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855453"
---
# <a name="contracttypenames"></a><span data-ttu-id="c97f8-101">\<Контракттипенамес ></span><span class="sxs-lookup"><span data-stu-id="c97f8-101">\<contractTypeNames></span></span>
<span data-ttu-id="c97f8-102">Раздел конфигурации, в котором указан список имен типов контрактов. Это имена контрактов искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="c97f8-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="c97f8-103">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="c97f8-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="c97f8-104">Обратите внимание, что в Windows Communication Foundation (WCF) конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="c97f8-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="c97f8-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c97f8-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c97f8-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="c97f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Динамицендпоинт >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="c97f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Стандардендпоинт >** </span><span class="sxs-lookup"><span data-stu-id="c97f8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="c97f8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Дисковериклиентсеттингс >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="c97f8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<findCriteria >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="c97f8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="c97f8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Контракттипенамес >**</span><span class="sxs-lookup"><span data-stu-id="c97f8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c97f8-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c97f8-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c97f8-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c97f8-114">Attributes and Elements</span></span>  
 <span data-ttu-id="c97f8-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c97f8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c97f8-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c97f8-116">Attributes</span></span>  
 <span data-ttu-id="c97f8-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="c97f8-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c97f8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c97f8-118">Child Elements</span></span>  
  
|<span data-ttu-id="c97f8-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="c97f8-119">Element</span></span>|<span data-ttu-id="c97f8-120">Описание</span><span class="sxs-lookup"><span data-stu-id="c97f8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c97f8-121">\<add></span><span class="sxs-lookup"><span data-stu-id="c97f8-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="c97f8-122">Имя типа контракта - это свойство, относящееся к набору критериев, обычно используемых для поиска службы.</span><span class="sxs-lookup"><span data-stu-id="c97f8-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c97f8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c97f8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c97f8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="c97f8-124">Element</span></span>|<span data-ttu-id="c97f8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="c97f8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c97f8-126">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="c97f8-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="c97f8-127">Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.</span><span class="sxs-lookup"><span data-stu-id="c97f8-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="c97f8-128">Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).</span><span class="sxs-lookup"><span data-stu-id="c97f8-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c97f8-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c97f8-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
