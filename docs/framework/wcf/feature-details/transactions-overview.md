---
title: "Общие сведения о транзакциях Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2be5e7622c51da37c0f39c12258f50b74483fa53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a>Общие сведения о транзакциях Windows Communication Foundation
Транзакции обеспечивают способ группировки набора действий или операций в одну неделимую единицу выполнения. Транзакция является коллекцией операций с перечисленными ниже свойствами.  
  
-   Атомарность. Благодаря данному свойству все обновления, завершенные в отдельной транзакции, либо фиксируются и становятся стабильными, либо отменяются и возвращаются к предыдущему состоянию с помощью отката.  
  
-   Согласованность. Данное свойство гарантирует, что все изменения, внесенные при транзакции, представляют собой трансформацию из одного состояния в другое. Например, транзакция, передающая деньги с текущего счета на сберегательный счет, не изменяет общее количество денег на банковском счете.  
  
-   Изоляция. Данное свойство предохраняет транзакцию от просмотра несохраненных изменений, относящихся к другим параллельным транзакциям. Изоляция обеспечивает отвлечение параллелизма, а также невозможность непредвиденного влияния одной транзакции на выполнение другой транзакции.  
  
-   Устойчивость. Данное свойство обозначает, что при однократной фиксации обновления в управляемых ресурсах (такие как запись базы данных) станут устойчивыми к сбоям.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивает богатый набор функций, позволяющих создавать распределенные транзакции в приложении веб-службы.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует поддержку для протокола WS-AtomicTransaction (WS-AT), который позволяет приложениям [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передавать транзакции во взаимодействующие приложения, такие как взаимодействующие веб-службы, созданные с использованием сторонней технологии. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также реализует поддержку для протокола OLE transactions, который может быть использован в сценариях, в которых не требуется функциональность взаимодействия приложений для обеспечения потока транзакций.  
  
 Для настройки привязок можно использовать файл конфигурации приложения, позволяющий включать или отключать передачу транзакций, а также задавать необходимый протокол транзакций для привязки. Кроме того, можно задать время ожидания транзакций на уровне службы с помощью файла конфигурации. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Включение потока транзакций](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).  
  
 Атрибуты транзакции в пространстве имен <xref:System.ServiceModel> позволяют выполнять перечисленные ниже действия.  
  
-   Настраивать время ожидания транзакций и фильтрацию уровня изоляции с помощью атрибута <xref:System.ServiceModel.ServiceBehaviorAttribute>.  
  
-   Включать функциональность транзакций и настраивать поведение при завершении транзакции с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
-   Для требования, разрешения или запрещения потока транзакций используйте атрибуты <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> метода контракта.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Атрибуты транзакции ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты транзакции ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [Включение потока транзакций](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
