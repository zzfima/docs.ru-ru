---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 12369f1053638583a3864fab396869d0e7045732
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918675"
---
# <a name="transactedbatching"></a><span data-ttu-id="0a238-101">\<Трансактедбатчинг ></span><span class="sxs-lookup"><span data-stu-id="0a238-101">\<transactedBatching></span></span>

<span data-ttu-id="0a238-102">Указывает, поддерживается ли объединение транзакций для операций получения.</span><span class="sxs-lookup"><span data-stu-id="0a238-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="0a238-103">\<системой. ServiceModel > </span><span class="sxs-lookup"><span data-stu-id="0a238-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="0a238-104">\<поведения > </span><span class="sxs-lookup"><span data-stu-id="0a238-104">\<behaviors></span></span>\
<span data-ttu-id="0a238-105">\<endpointBehaviors > </span><span class="sxs-lookup"><span data-stu-id="0a238-105">\<endpointBehaviors></span></span>\
<span data-ttu-id="0a238-106">\<> поведения </span><span class="sxs-lookup"><span data-stu-id="0a238-106">\<behavior></span></span>\
<span data-ttu-id="0a238-107">\<Трансактедбатчинг ></span><span class="sxs-lookup"><span data-stu-id="0a238-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="0a238-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a238-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0a238-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0a238-109">Attributes and Elements</span></span>

<span data-ttu-id="0a238-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0a238-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0a238-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0a238-111">Attributes</span></span>

|<span data-ttu-id="0a238-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0a238-112">Attribute</span></span>|<span data-ttu-id="0a238-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0a238-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="0a238-114">Целое число, указывающее максимальное число операций получения, которые могут быть объединены в одну транзакцию.</span><span class="sxs-lookup"><span data-stu-id="0a238-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="0a238-115">Значение по умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="0a238-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0a238-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0a238-116">Child Elements</span></span>

<span data-ttu-id="0a238-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="0a238-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0a238-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0a238-118">Parent Elements</span></span>

|<span data-ttu-id="0a238-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0a238-119">Element</span></span>|<span data-ttu-id="0a238-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0a238-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0a238-121">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0a238-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0a238-122">Задает поведение конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0a238-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0a238-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a238-123">Remarks</span></span>

<span data-ttu-id="0a238-124">Транзакция, настроенная на попытки объединения в один пакет нескольких операций получения.</span><span class="sxs-lookup"><span data-stu-id="0a238-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="0a238-125">Это позволяет избежать относительно высоких затрат ресурсов на создание и отправку транзакции для каждой операции получения.</span><span class="sxs-lookup"><span data-stu-id="0a238-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="0a238-126">Пример</span><span class="sxs-lookup"><span data-stu-id="0a238-126">Example</span></span>

<span data-ttu-id="0a238-127">В следующем примере показано, как добавить поведение объединения транзакций для службы в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a238-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
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

## <a name="see-also"></a><span data-ttu-id="0a238-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0a238-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
