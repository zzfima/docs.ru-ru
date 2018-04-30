---
title: Конфигурация транзакции ServiceModel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 96cf83be06949160cf3efa73344e4a7680d24e09
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="servicemodel-transaction-configuration"></a><span data-ttu-id="59a8a-102">Конфигурация транзакции ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59a8a-102">ServiceModel Transaction Configuration</span></span>
<span data-ttu-id="59a8a-103">В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предусмотрено три атрибута для настройки транзакций для службы: `transactionFlow`, `transactionProtocol` и `transactionTimeout`.</span><span class="sxs-lookup"><span data-stu-id="59a8a-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides three attributes for configuring transactions for a service: `transactionFlow`, `transactionProtocol`, and `transactionTimeout`.</span></span>  
  
## <a name="configuring-transactionflow"></a><span data-ttu-id="59a8a-104">Настройка атрибута transactionFlow</span><span class="sxs-lookup"><span data-stu-id="59a8a-104">Configuring transactionFlow</span></span>  
 <span data-ttu-id="59a8a-105">Большинство заранее определенных привязок, предоставляемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], содержат атрибуты `transactionFlow` и `transactionProtocol`, чтобы можно было настроить привязку на прием входящих транзакций для конкретной конечной точки с использованием определенного протокола потока транзакций.</span><span class="sxs-lookup"><span data-stu-id="59a8a-105">Most of the predefined bindings [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides contain the `transactionFlow` and `transactionProtocol` attributes, so that you can configure the binding to accept incoming transactions for a specific endpoint using a specific transaction flow protocol.</span></span> <span data-ttu-id="59a8a-106">Кроме того, вы можете использовать элемент `transactionFlow` и его атрибут `transactionProtocol` для сборки вашей собственной пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="59a8a-106">In addition, you can use the `transactionFlow` element and its `transactionProtocol` attribute to build your own custom binding.</span></span> <span data-ttu-id="59a8a-107">Дополнительные сведения о настройке элементов конфигурации см. в разделе [ \<привязки >](../../../../docs/framework/misc/binding.md) и [схем конфигурации WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="59a8a-107">For more information about setting the configuration elements, see [\<binding>](../../../../docs/framework/misc/binding.md) and [WCF Configuration Schema](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).</span></span>  
  
 <span data-ttu-id="59a8a-108">Атрибут `transactionFlow` задает, разрешен ли поток транзакций для конечных точек службы, использующих данную привязку.</span><span class="sxs-lookup"><span data-stu-id="59a8a-108">The `transactionFlow` attribute specifies whether transaction flow is enabled for service endpoints that use the binding.</span></span>  
  
## <a name="configuring-transactionprotocol"></a><span data-ttu-id="59a8a-109">Настройка атрибута transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="59a8a-109">Configuring transactionProtocol</span></span>  
 <span data-ttu-id="59a8a-110">Атрибут `transactionProtocol` задает протокол транзакций, который должен использоваться конечными точками, использующими данную привязку.</span><span class="sxs-lookup"><span data-stu-id="59a8a-110">The `transactionProtocol` attribute specifies the transaction protocol to use with service endpoints that use the binding.</span></span>  
  
 <span data-ttu-id="59a8a-111">Ниже приведен пример раздела конфигурации, настраивающий указанную привязку для поддержки потока транзакций, а также для использования протокола WS-AtomicTransaction.</span><span class="sxs-lookup"><span data-stu-id="59a8a-111">The following is an example of a configuration section that configures the specified binding to support transaction flow, as well as a use the WS-AtomicTransaction protocol.</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding name="test"  
      closeTimeout="00:00:10"  
      openTimeout="00:00:20"   
      receiveTimeout="00:00:30"  
      sendTimeout="00:00:40"  
      transactionFlow="true"  
      transactionProtocol="WSAtomicTransactionOctober2004"  
      hostNameComparisonMode="WeakWildcard"  
      maxBufferSize="1001"  
      maxConnections="123"   
      maxReceivedMessageSize="1000">  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="configuring-transactiontimeout"></a><span data-ttu-id="59a8a-112">Настройка атрибута transactionTimeout</span><span class="sxs-lookup"><span data-stu-id="59a8a-112">Configuring transactionTimeout</span></span>  
 <span data-ttu-id="59a8a-113">Можно настроить `transactionTimeout` для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в элементе `behavior` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="59a8a-113">You can configure the `transactionTimeout` attribute for your [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in the `behavior` element of the configuration file.</span></span> <span data-ttu-id="59a8a-114">В следующем коде показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="59a8a-114">The following code demonstrates how to do this.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="59a8a-115">Атрибут `transactionTimeout` задает период времени, в течение которого созданная в службе новая транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="59a8a-115">The `transactionTimeout` attribute specifies the time period within which a new transaction created at the service must complete.</span></span> <span data-ttu-id="59a8a-116">Он используется в качестве времени ожидания <xref:System.Transactions.TransactionScope> для любой операции, устанавливающей новую транзакцию; если применен атрибут <xref:System.ServiceModel.OperationBehaviorAttribute>, для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> устанавливается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59a8a-116">It is used as the <xref:System.Transactions.TransactionScope> time-out for any operation that establishes a new transaction, and if <xref:System.ServiceModel.OperationBehaviorAttribute> is applied, the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="59a8a-117">Время ожидания задает промежуток времени от создания транзакции до завершения фазы 1 в протоколе двухфазной фиксации.</span><span class="sxs-lookup"><span data-stu-id="59a8a-117">The time-out specifies the duration of time from the creation of the transaction to the completion of phase 1 in the two-phase commit protocol.</span></span>  
  
 <span data-ttu-id="59a8a-118">Если этот атрибут задан в разделе конфигурации `service`, необходимо применить по меньшей мере один метод соответствующей службы с атрибутом <xref:System.ServiceModel.OperationBehaviorAttribute>, в котором для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="59a8a-118">If this attribute is set within a `service` configuration section, you should apply at least one method of the corresponding service with <xref:System.ServiceModel.OperationBehaviorAttribute>, in which the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property is set to `true`.</span></span>  
  
 <span data-ttu-id="59a8a-119">Обратите внимание, что для времени ожидания всегда используется меньшее из значений этого параметра конфигурации `transactionTimeout` и любого из свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="59a8a-119">Note that the time-out value used is the smaller value between this `transactionTimeout` configuration setting and any <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a8a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="59a8a-120">See Also</span></span>  
 [<span data-ttu-id="59a8a-121">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="59a8a-121">\<binding></span></span>](../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="59a8a-122">Схема конфигурации WCF</span><span class="sxs-lookup"><span data-stu-id="59a8a-122">WCF Configuration Schema</span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)
