---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 6cc8b80edb3206bb2ef3a8a1ffa34ab40af77612
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398149"
---
# <a name="client"></a><span data-ttu-id="caa0e-101">\<> клиента</span><span class="sxs-lookup"><span data-stu-id="caa0e-101">\<client></span></span>
<span data-ttu-id="caa0e-102">Элемент `client` определяет список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="caa0e-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>  
  
<span data-ttu-id="caa0e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="caa0e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="caa0e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="caa0e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="caa0e-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<> клиента**</span><span class="sxs-lookup"><span data-stu-id="caa0e-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa0e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caa0e-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caa0e-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="caa0e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="caa0e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="caa0e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caa0e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="caa0e-109">Attributes</span></span>  
 <span data-ttu-id="caa0e-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="caa0e-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="caa0e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="caa0e-111">Child Elements</span></span>  
  
|<span data-ttu-id="caa0e-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="caa0e-112">Element</span></span>|<span data-ttu-id="caa0e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="caa0e-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caa0e-114">\<> конечной точки</span><span class="sxs-lookup"><span data-stu-id="caa0e-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="caa0e-115">Содержит коллекцию элементов конечных точек, указывающую конечные точки, к которым может подключиться данный клиент.</span><span class="sxs-lookup"><span data-stu-id="caa0e-115">Contains a collection of endpoint elements, that specify the endpoints that this client can connect to.</span></span>|  
|[<span data-ttu-id="caa0e-116">\<> метаданных</span><span class="sxs-lookup"><span data-stu-id="caa0e-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="caa0e-117">Содержит параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="caa0e-117">Contains settings for processing metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="caa0e-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="caa0e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="caa0e-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="caa0e-119">Element</span></span>|<span data-ttu-id="caa0e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="caa0e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caa0e-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="caa0e-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="caa0e-122">Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="caa0e-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caa0e-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="caa0e-123">Remarks</span></span>  
 <span data-ttu-id="caa0e-124">В разделе `client` определяется список конечных точек, к которым может подключаться клиент.</span><span class="sxs-lookup"><span data-stu-id="caa0e-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="caa0e-125">Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт.</span><span class="sxs-lookup"><span data-stu-id="caa0e-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="caa0e-126">Она однозначно определяется сочетанием атрибутов `name` и `contract`.</span><span class="sxs-lookup"><span data-stu-id="caa0e-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="caa0e-127">В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом.</span><span class="sxs-lookup"><span data-stu-id="caa0e-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="caa0e-128">Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.</span><span class="sxs-lookup"><span data-stu-id="caa0e-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>  
  
 <span data-ttu-id="caa0e-129">Кроме того, в данном разделе также задаются параметры обработки метаданных.</span><span class="sxs-lookup"><span data-stu-id="caa0e-129">In addition, this section also specifies settings for processing metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caa0e-130">Пример</span><span class="sxs-lookup"><span data-stu-id="caa0e-130">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="caa0e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="caa0e-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="caa0e-132">Конфигурация клиента WCF</span><span class="sxs-lookup"><span data-stu-id="caa0e-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="caa0e-133">Клиенты</span><span class="sxs-lookup"><span data-stu-id="caa0e-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
