---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: f56751ea3f8bdc9ecbeff57db835e5fc2edbb73e
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148452"
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="2d04e-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="2d04e-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="2d04e-103">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="2d04e-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="2d04e-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2d04e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2d04e-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="2d04e-105">\<behaviors></span></span>  
<span data-ttu-id="2d04e-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2d04e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="2d04e-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2d04e-107">\<behavior></span></span>  
<span data-ttu-id="2d04e-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="2d04e-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d04e-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d04e-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d04e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2d04e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2d04e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2d04e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d04e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2d04e-112">Attributes</span></span>  
  
|<span data-ttu-id="2d04e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2d04e-113">Attribute</span></span>|<span data-ttu-id="2d04e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2d04e-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="2d04e-115">Целое число, указывающее максимальное число операций получения, которые могут быть объединены в одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="2d04e-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="2d04e-116">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="2d04e-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d04e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2d04e-117">Child Elements</span></span>  
 <span data-ttu-id="2d04e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2d04e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d04e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2d04e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2d04e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="2d04e-120">Element</span></span>|<span data-ttu-id="2d04e-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="2d04e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d04e-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2d04e-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2d04e-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2d04e-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d04e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d04e-124">Remarks</span></span>  
 <span data-ttu-id="2d04e-125">Транзакция, настроенная на попытки объединения в один пакет нескольких операций получения.</span><span class="sxs-lookup"><span data-stu-id="2d04e-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="2d04e-126">Это позволяет избежать относительно высоких затрат ресурсов на создание и отправку транзакции для каждой операции получения.</span><span class="sxs-lookup"><span data-stu-id="2d04e-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d04e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="2d04e-127">Example</span></span>  
 <span data-ttu-id="2d04e-128">В следующем примере показано, как добавить поведение объединения транзакций для службы в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2d04e-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
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
  
## <a name="see-also"></a><span data-ttu-id="2d04e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2d04e-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
