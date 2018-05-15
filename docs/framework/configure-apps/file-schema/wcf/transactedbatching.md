---
title: '&lt;transactedBatching&gt;'
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: f0cf0b78ddcbd3214e30a36ce7641d115275a265
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttransactedbatchinggt"></a><span data-ttu-id="ce407-102">&lt;transactedBatching&gt;</span><span class="sxs-lookup"><span data-stu-id="ce407-102">&lt;transactedBatching&gt;</span></span>
<span data-ttu-id="ce407-103">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="ce407-103">Specifies whether transaction batching is supported for receive operations.</span></span>  
  
 <span data-ttu-id="ce407-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ce407-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ce407-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="ce407-105">\<behaviors></span></span>  
<span data-ttu-id="ce407-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ce407-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="ce407-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="ce407-107">\<behavior></span></span>  
<span data-ttu-id="ce407-108">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="ce407-108">\<transactedBatching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce407-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce407-109">Syntax</span></span>  
  
```xml  
<transactedBatching maxBatchSize="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce407-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce407-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce407-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce407-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce407-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce407-112">Attributes</span></span>  
  
|<span data-ttu-id="ce407-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ce407-113">Attribute</span></span>|<span data-ttu-id="ce407-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ce407-114">Description</span></span>|  
|---------------|-----------------|  
|`maxBatchSize`|<span data-ttu-id="ce407-115">Целое число, указывающее максимальное число операций получения, которые могут быть объединены в одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="ce407-115">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="ce407-116">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="ce407-116">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce407-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce407-117">Child Elements</span></span>  
 <span data-ttu-id="ce407-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ce407-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce407-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce407-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ce407-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce407-120">Element</span></span>|<span data-ttu-id="ce407-121">Описание</span><span class="sxs-lookup"><span data-stu-id="ce407-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce407-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="ce407-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ce407-123">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ce407-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce407-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce407-124">Remarks</span></span>  
 <span data-ttu-id="ce407-125">Транзакция, настроенная на попытки объединения в один пакет нескольких операций получения.</span><span class="sxs-lookup"><span data-stu-id="ce407-125">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="ce407-126">Это позволяет избежать относительно высоких затрат ресурсов на создание и отправку транзакции для каждой операции получения.</span><span class="sxs-lookup"><span data-stu-id="ce407-126">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce407-127">Пример</span><span class="sxs-lookup"><span data-stu-id="ce407-127">Example</span></span>  
 <span data-ttu-id="ce407-128">В следующем примере показано, как добавить поведение объединения транзакций для службы в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce407-128">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce407-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ce407-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactedBatchingElement>  
 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
