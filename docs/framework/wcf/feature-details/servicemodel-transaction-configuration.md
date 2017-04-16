---
title: "Конфигурация транзакции ServiceModel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "транзакции [WCF], конфигурация ServiceModel"
ms.assetid: 5636067a-7fbd-4485-aaa2-8141c502acf3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Конфигурация транзакции ServiceModel
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предусмотрено три атрибута для настройки транзакций для службы: `transactionFlow`, `transactionProtocol` и `transactionTimeout`.  
  
## Настройка атрибута transactionFlow  
 Большинство заранее определенных привязок, предоставляемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], содержат атрибуты `transactionFlow` и `transactionProtocol`, чтобы можно было настроить привязку на прием входящих транзакций для конкретной конечной точки с использованием определенного протокола потока транзакций.Кроме того, вы можете использовать элемент `transactionFlow` и его атрибут `transactionProtocol` для построения вашей собственной пользовательской привязки.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о настройке элементов конфигурации см. в разделах [\<привязка\>](../../../../docs/framework/misc/binding.md) и [Схем конфигурации WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md).  
  
 Атрибут `transactionFlow` задает, разрешен ли поток транзакций для конечных точек службы, использующих данную привязку.  
  
## Настройка атрибута transactionProtocol  
 Атрибут `transactionProtocol` задает протокол транзакций, который должен использоваться конечными точками, использующими данную привязку.  
  
 Ниже приведен пример раздела конфигурации, настраивающий указанную привязку для поддержки потока транзакций, а также для использования протокола WS\-AtomicTransaction.  
  
```  
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
  
## Настройка атрибута transactionTimeout  
 Можно настроить `transactionTimeout` для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в элементе `behavior` файла конфигурации.В следующем коде показано, как это сделать.  
  
```  
<configuration>  
   <system.serviceModel>  
      <behaviors>  
         <behavior name="NewBehavior" transactionTimeout="00:01:00" /> <!-- 1 minute timeout -->  
      </behaviors>  
   </system.serviceModel>  
</configuration>  
```  
  
 Атрибут `transactionTimeout` задает период времени, в течение которого созданная в службе новая транзакция должна быть завершена.Он используется в качестве времени ожидания <xref:System.Transactions.TransactionScope> для любой операции, устанавливающей новую транзакцию; если применен атрибут <xref:System.ServiceModel.OperationBehaviorAttribute>, для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> устанавливается значение `true`.  
  
 Время ожидания задает промежуток времени от создания транзакции до завершения фазы 1 в протоколе двухфазной фиксации.  
  
 Если этот атрибут задан в разделе конфигурации `service`, необходимо применить по меньшей мере один метод соответствующей службы с атрибутом <xref:System.ServiceModel.OperationBehaviorAttribute>, в котором для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> задано значение `true`.  
  
 Обратите внимание, что для времени ожидания всегда используется меньшее из значений этого параметра конфигурации `transactionTimeout` и любого из свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.  
  
## См. также  
 [\<привязка\>](../../../../docs/framework/misc/binding.md)   
 [Схем конфигурации WCF](../../../../docs/framework/configure-apps/file-schema/wcf/index.md)