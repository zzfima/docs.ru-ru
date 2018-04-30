---
title: Модели транзакций
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c68a23e9ee86050a9db4c63c8c97d017794bce8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="transaction-models"></a>Модели транзакций
В этом разделе описывается связь между моделями программирования транзакций и компонентами инфраструктуры, предоставляемыми корпорацией Microsoft.  
  
 При использовании транзакций в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] важно понимать, что выбор производится не между различными транзакционными моделями, а между различными уровнями интегрированной и согласованной модели.  
  
 В следующих подразделах рассматриваются три основных компонента транзакции.  
  
## <a name="windows-communication-foundation-transactions"></a>Транзакции Windows Communication Foundation  
 Поддержка транзакций в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет создавать транзакционные службы. Кроме того, благодаря поддержке протокола WS-AtomicTransaction (WS-AT) приложения могут направлять транзакции веб-службам, созданным как с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], так и с помощью технологий независимых разработчиков.  
  
 В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] функции транзакций [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляют атрибуты и конфигурацию для декларативного задания способа и момента создания, передачи и синхронизации транзакций на уровне инфраструктуры.  
  
## <a name="systemtransactions-transactions"></a>Транзакции System.Transactions  
 Пространство имен <xref:System.Transactions> предоставляет как модель явного программирования, основанную на классе <xref:System.Transactions.Transaction>, так и модель неявного программирования, использующая класс <xref:System.Transactions.TransactionScope>, в котором транзакции автоматически управляются инфраструктурой.  
  
 Дополнительные сведения о создании приложения с поддержкой транзакций с помощью этих двух моделях см. в разделе [Создание транзакционного приложения](http://go.microsoft.com/fwlink/?LinkId=94947).  
  
 В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] пространство имен <xref:System.Transactions> предоставляет модель программирования для создания транзакций в клиентском приложении и для явного взаимодействия с транзакциями, когда это необходимо, в пределах службы.  
  
## <a name="msdtc-transactions"></a>Транзакции MSDTC  
 Координатор распределенных транзакций (Майкрософт) (MSDTC) представляет собой диспетчер транзакций, обеспечивающий поддержку распределенных транзакций.  
  
 Дополнительные сведения см. в разделе [Справочник по программированию DTC](http://go.microsoft.com/fwlink/?LinkId=94948).  
  
 В службе или приложении [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSDTC обеспечивает инфраструктуру для координации транзакций, созданных в клиенте или службе.
