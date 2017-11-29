---
title: '&lt;transactedBatching&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edeb10a1a7fa540b3f3e6ef4bf1a4a820fbc1b4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="5eb59-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="5eb59-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="5eb59-103">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="5eb59-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="5eb59-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5eb59-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5eb59-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="5eb59-105">\<behaviors></span></span>  
<span data-ttu-id="5eb59-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5eb59-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="5eb59-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5eb59-107">\<behavior></span></span>  
<span data-ttu-id="5eb59-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="5eb59-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eb59-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5eb59-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5eb59-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5eb59-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5eb59-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5eb59-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5eb59-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5eb59-112">Attributes</span></span>  
  
|<span data-ttu-id="5eb59-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5eb59-113">Attribute</span></span>|<span data-ttu-id="5eb59-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5eb59-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="5eb59-115">Целое число, указывающее максимальное число операций получения, которые могут быть объединены в одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="5eb59-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="5eb59-116">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="5eb59-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5eb59-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5eb59-117">Child Elements</span></span>  
 <span data-ttu-id="5eb59-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5eb59-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5eb59-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5eb59-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5eb59-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="5eb59-120">Element</span></span>|<span data-ttu-id="5eb59-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5eb59-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5eb59-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5eb59-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5eb59-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5eb59-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5eb59-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="5eb59-124">Remarks</span></span>  
 <span data-ttu-id="5eb59-125">Транзакция, настроенная на попытки объединения в один пакет нескольких операций получения.</span><span class="sxs-lookup"><span data-stu-id="5eb59-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="5eb59-126">Это позволяет избежать относительно высоких затрат ресурсов на создание и отправку транзакции для каждой операции получения.</span><span class="sxs-lookup"><span data-stu-id="5eb59-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eb59-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5eb59-127">Example</span></span>  
 <span data-ttu-id="5eb59-128">В следующем примере показано, как добавить поведение объединения транзакций для службы в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5eb59-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
        </baseAddresses>  
      </host>  
  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />  
  
      <!-- the mex endpoint is explosed at http://localhost:8000/ServiceModelSamples/service/mex -->  
      <endpoint address="mex"  
                binding="mexHttpBinding"  
                contract="IMetadataExchange" />  
    </service>  
  </services>  
  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="endpointBehavior">  
        <transactedBatching maxBatchSize="10" />  
      </behavior>  
    </endpointBehaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
        <serviceMetadata httpGetEnabled="true" />  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eb59-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5eb59-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
