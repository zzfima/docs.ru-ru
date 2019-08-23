---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7dce5984882e48c3e62efc44ef00b6256d9eb64e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919530"
---
# <a name="client"></a><span data-ttu-id="f0cdd-101">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="f0cdd-101">\<client></span></span>
<span data-ttu-id="f0cdd-102">Элемент `client` определяет список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="f0cdd-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0cdd-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f0cdd-104">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="f0cdd-104">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0cdd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0cdd-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0cdd-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f0cdd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f0cdd-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0cdd-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f0cdd-108">Attributes</span></span>  
 <span data-ttu-id="f0cdd-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f0cdd-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f0cdd-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f0cdd-110">Child Elements</span></span>  
  
|<span data-ttu-id="f0cdd-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0cdd-111">Element</span></span>|<span data-ttu-id="f0cdd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f0cdd-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0cdd-113">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="f0cdd-113">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="f0cdd-114">Содержит коллекцию элементов конечных точек, указывающую конечные точки, к которым может подключиться данный клиент.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-114">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="f0cdd-115">\<> метаданных</span><span class="sxs-lookup"><span data-stu-id="f0cdd-115">\<metadata></span></span>](metadata.md)|<span data-ttu-id="f0cdd-116">Содержит параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-116">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0cdd-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f0cdd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f0cdd-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0cdd-118">Element</span></span>|<span data-ttu-id="f0cdd-119">Описание</span><span class="sxs-lookup"><span data-stu-id="f0cdd-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0cdd-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f0cdd-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="f0cdd-121">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f0cdd-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0cdd-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0cdd-122">Remarks</span></span>  
 <span data-ttu-id="f0cdd-123">В разделе `client` определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-123">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="f0cdd-124">Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-124">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="f0cdd-125">Она однозначно определяется сочетанием атрибутов `name` и `contract`.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-125">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="f0cdd-126">В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-126">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="f0cdd-127">Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-127">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="f0cdd-128">Кроме того, в данном разделе также задаются параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="f0cdd-128">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0cdd-129">Пример</span><span class="sxs-lookup"><span data-stu-id="f0cdd-129">Example</span></span>  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a><span data-ttu-id="f0cdd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f0cdd-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="f0cdd-131">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="f0cdd-131">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="f0cdd-132">Клиенты</span><span class="sxs-lookup"><span data-stu-id="f0cdd-132">Clients</span></span>](../../../wcf/feature-details/clients.md)
