---
title: Конфигурация транзакции ServiceModel
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel configuration
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
ms.openlocfilehash: d5bb81c618e3b27df32763948dbe56c9b37995e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188979"
---
# <a name="servicemodel-transaction-configuration"></a>Конфигурация транзакции ServiceModel
Windows Communication Foundation (WCF) предоставляет три атрибута для настройки транзакций для службы: `transactionFlow`, `transactionProtocol`, и `transactionTimeout`.  
  
## <a name="configuring-transactionflow"></a>Настройка атрибута transactionFlow  
 Большинство предопределенных привязок WCF предоставляет содержат `transactionFlow` и `transactionProtocol` атрибуты, чтобы можно было настроить привязку на прием входящих транзакций для конкретной конечной точки с помощью определенного протокола потока транзакций. Кроме того, вы можете использовать элемент `transactionFlow` и его атрибут `transactionProtocol` для сборки вашей собственной пользовательской привязки. Дополнительные сведения о настройке элементов конфигурации, см. в разделе [ \<привязки >](../../../../docs/framework/misc/binding.md) и [схема конфигурации WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
 Атрибут `transactionFlow` задает, разрешен ли поток транзакций для конечных точек службы, использующих данную привязку.  
  
## <a name="configuring-transactionprotocol"></a>Настройка атрибута transactionProtocol  
 Атрибут `transactionProtocol` задает протокол транзакций, который должен использоваться конечными точками, использующими данную привязку.  
  
 Ниже приведен пример раздела конфигурации, настраивающий указанную привязку для поддержки потока транзакций, а также для использования протокола WS-AtomicTransaction.  
  
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
  
## <a name="configuring-transactiontimeout"></a>Настройка атрибута transactionTimeout  
 Можно настроить `transactionTimeout` атрибут для вашей службы WCF на `behavior` элемент файла конфигурации. В следующем коде показано, как это сделать.  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 Атрибут `transactionTimeout` задает период времени, в течение которого созданная в службе новая транзакция должна быть завершена. Он используется в качестве времени ожидания <xref:System.Transactions.TransactionScope> для любой операции, устанавливающей новую транзакцию; если применен атрибут <xref:System.ServiceModel.OperationBehaviorAttribute>, для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> устанавливается значение `true`.  
  
 Время ожидания задает промежуток времени от создания транзакции до завершения фазы 1 в протоколе двухфазной фиксации.  
  
 Если этот атрибут задан в разделе конфигурации `service`, необходимо применить по меньшей мере один метод соответствующей службы с атрибутом <xref:System.ServiceModel.OperationBehaviorAttribute>, в котором для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> задано значение `true`.  
  
 Обратите внимание, что для времени ожидания всегда используется меньшее из значений этого параметра конфигурации `transactionTimeout` и любого из свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.  
  
## <a name="see-also"></a>См. также

- [\<Привязка >](../../../../docs/framework/misc/binding.md)
- [Схем конфигурации WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)
