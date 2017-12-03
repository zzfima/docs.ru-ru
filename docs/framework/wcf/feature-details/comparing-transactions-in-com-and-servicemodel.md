---
title: "Сравнение транзакций в COM+ и ServiceModel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5229c872c4843df916cf538b7f2e88e451dc6b9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Сравнение транзакций в COM+ и ServiceModel
В этом разделе описывается, как моделировать поведение транзакционной службы COM+ с помощью атрибутов [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] пространства имен <xref:System.ServiceModel>.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Эмуляция COM+ с помощью атрибутов ServiceModel  
 В следующей таблице сравнивается перечисление <xref:System.EnterpriseServices.TransactionOption>, используемое для создания транзакции `EnterpriseServices`, и их корреляция с атрибутами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в пространстве имен <xref:System.ServiceModel>.  
  
|Атрибут COM+|Атрибуты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Обязательно|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `true`.|  
|Поддерживается|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `Required`.|  
|NotSupported|Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `false`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Disabled|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `NotSupported`.|
