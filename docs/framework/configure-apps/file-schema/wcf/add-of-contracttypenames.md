---
title: <add> из <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850533"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="90d15-102">\<Добавление > \<> контракттипенамес</span><span class="sxs-lookup"><span data-stu-id="90d15-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="90d15-103">Элемент конфигурации, указывающий имя контракта искомых служб, а также критерии, обычно используемые при поиске служб.</span><span class="sxs-lookup"><span data-stu-id="90d15-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="90d15-104">Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, совпадающих со ВСЕМИ контрактами.</span><span class="sxs-lookup"><span data-stu-id="90d15-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="90d15-105">Обратите внимание, что в Windows Communication Foundation (WCF) конечная точка может поддерживать только один контракт.</span><span class="sxs-lookup"><span data-stu-id="90d15-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="90d15-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="90d15-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="90d15-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="90d15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Динамицендпоинт >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="90d15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Стандардендпоинт >** </span><span class="sxs-lookup"><span data-stu-id="90d15-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="90d15-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Дисковериклиентсеттингс >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="90d15-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<findCriteria >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="90d15-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Контракттипенамес >** ](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="90d15-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="90d15-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="90d15-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d15-115">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90d15-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90d15-116">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="90d15-116">Attributes and Elements</span></span>  
 <span data-ttu-id="90d15-117">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="90d15-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90d15-118">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="90d15-118">Attributes</span></span>  
  
|<span data-ttu-id="90d15-119">Атрибут</span><span class="sxs-lookup"><span data-stu-id="90d15-119">Attribute</span></span>|<span data-ttu-id="90d15-120">Описание</span><span class="sxs-lookup"><span data-stu-id="90d15-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90d15-121">имя</span><span class="sxs-lookup"><span data-stu-id="90d15-121">name</span></span>|<span data-ttu-id="90d15-122">Строка, в которой указано имя типа контракта.</span><span class="sxs-lookup"><span data-stu-id="90d15-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="90d15-123">namespace</span><span class="sxs-lookup"><span data-stu-id="90d15-123">namespace</span></span>|<span data-ttu-id="90d15-124">Строка, в которой указано пространство имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="90d15-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90d15-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="90d15-125">Child Elements</span></span>  
 <span data-ttu-id="90d15-126">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="90d15-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90d15-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="90d15-127">Parent Elements</span></span>  
  
|<span data-ttu-id="90d15-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="90d15-128">Element</span></span>|<span data-ttu-id="90d15-129">Описание</span><span class="sxs-lookup"><span data-stu-id="90d15-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90d15-130">\<Контракттипенамес ></span><span class="sxs-lookup"><span data-stu-id="90d15-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="90d15-131">Коллекция имен типа контракта.</span><span class="sxs-lookup"><span data-stu-id="90d15-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90d15-132">См. также</span><span class="sxs-lookup"><span data-stu-id="90d15-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
