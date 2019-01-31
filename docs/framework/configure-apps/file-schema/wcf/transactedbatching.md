---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 1e8ce41a27bd328c861f2f376a89c57bcd035389
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281298"
---
# <a name="transactedbatching"></a><span data-ttu-id="7b4ba-101">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="7b4ba-101">\<transactedBatching></span></span>
<span data-ttu-id="7b4ba-102">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-102">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="7b4ba-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7b4ba-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b4ba-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="7b4ba-104">\<behaviors></span></span>  
<span data-ttu-id="7b4ba-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7b4ba-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="7b4ba-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7b4ba-106">\<behavior></span></span>  
<span data-ttu-id="7b4ba-107">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="7b4ba-107">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b4ba-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b4ba-108">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b4ba-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7b4ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7b4ba-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b4ba-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7b4ba-111">Attributes</span></span>  
  
|<span data-ttu-id="7b4ba-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7b4ba-112">Attribute</span></span>|<span data-ttu-id="7b4ba-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7b4ba-113">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="7b4ba-114">Целое число, указывающее максимальное число операций получения, которые могут быть объединены в одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="7b4ba-115">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-115">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b4ba-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7b4ba-116">Child Elements</span></span>  
 <span data-ttu-id="7b4ba-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b4ba-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7b4ba-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7b4ba-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="7b4ba-119">Element</span></span>|<span data-ttu-id="7b4ba-120">Описание</span><span class="sxs-lookup"><span data-stu-id="7b4ba-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b4ba-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="7b4ba-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7b4ba-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b4ba-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="7b4ba-123">Remarks</span></span>  
 <span data-ttu-id="7b4ba-124">Транзакция, настроенная на попытки объединения в один пакет нескольких операций получения.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="7b4ba-125">Это позволяет избежать относительно высоких затрат ресурсов на создание и отправку транзакции для каждой операции получения.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b4ba-126">Пример</span><span class="sxs-lookup"><span data-stu-id="7b4ba-126">Example</span></span>  
 <span data-ttu-id="7b4ba-127">В следующем примере показано, как добавить поведение объединения транзакций для службы в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7b4ba-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7b4ba-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7b4ba-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
