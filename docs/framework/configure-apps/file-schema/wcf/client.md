---
title: "&lt;Клиент&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 260408bd168246b67830637ca53e78b78758b849
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientgt"></a><span data-ttu-id="849c3-102">&lt;Клиент&gt;</span><span class="sxs-lookup"><span data-stu-id="849c3-102">&lt;client&gt;</span></span>
<span data-ttu-id="849c3-103">Элемент `client` определяет список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="849c3-103">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
 <span data-ttu-id="849c3-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="849c3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="849c3-105">\<Клиент ></span><span class="sxs-lookup"><span data-stu-id="849c3-105">\<client></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="849c3-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="849c3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="849c3-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="849c3-107">Attributes and Elements</span></span>  
 <span data-ttu-id="849c3-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="849c3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="849c3-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="849c3-109">Attributes</span></span>  
 <span data-ttu-id="849c3-110">Нет</span><span class="sxs-lookup"><span data-stu-id="849c3-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="849c3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="849c3-111">Child Elements</span></span>  
  
|<span data-ttu-id="849c3-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="849c3-112">Element</span></span>|<span data-ttu-id="849c3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="849c3-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="849c3-114">\<Конечная точка ></span><span class="sxs-lookup"><span data-stu-id="849c3-114">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="849c3-115">Содержит коллекцию элементов конечных точек, указывающую конечные точки, к которым может подключиться данный клиент.</span><span class="sxs-lookup"><span data-stu-id="849c3-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="849c3-116">\<метаданные ></span><span class="sxs-lookup"><span data-stu-id="849c3-116">\<metadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|<span data-ttu-id="849c3-117">Содержит параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="849c3-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="849c3-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="849c3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="849c3-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="849c3-119">Element</span></span>|<span data-ttu-id="849c3-120">Описание</span><span class="sxs-lookup"><span data-stu-id="849c3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="849c3-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="849c3-121">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="849c3-122">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="849c3-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="849c3-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="849c3-123">Remarks</span></span>  
 <span data-ttu-id="849c3-124">В разделе `client` определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="849c3-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="849c3-125">Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт.</span><span class="sxs-lookup"><span data-stu-id="849c3-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="849c3-126">Она однозначно определяется сочетанием атрибутов `name` и `contract`.</span><span class="sxs-lookup"><span data-stu-id="849c3-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="849c3-127">В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом.</span><span class="sxs-lookup"><span data-stu-id="849c3-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="849c3-128">Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.</span><span class="sxs-lookup"><span data-stu-id="849c3-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="849c3-129">Кроме того, в данном разделе также задаются параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="849c3-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="849c3-130">Пример</span><span class="sxs-lookup"><span data-stu-id="849c3-130">Example</span></span>  
  
```xml  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## <a name="see-also"></a><span data-ttu-id="849c3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="849c3-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 [<span data-ttu-id="849c3-132">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="849c3-132">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="849c3-133">Клиенты</span><span class="sxs-lookup"><span data-stu-id="849c3-133">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
