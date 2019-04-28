---
title: Сравнение транзакций в COM+ и ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857874"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Сравнение транзакций в COM+ и ServiceModel
Здесь описывается, как моделировать поведение транзакционной службы COM + с помощью Windows Communication Foundation (WCF) атрибутов <xref:System.ServiceModel> предоставляет пространство имен.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Эмуляция COM+ с помощью атрибутов ServiceModel  
 В следующей таблице сравниваются <xref:System.EnterpriseServices.TransactionOption> перечисление, используемое для создания `EnterpriseServices` транзакций и их корреляция с атрибутами WCF <xref:System.ServiceModel> предоставляет пространство имен.  
  
|Атрибут COM+|Атрибуты WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Обязательно|Параметру <xref:System.ServiceModel.TransactionFlowAttribute> задается значение <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `true`.|  
|Поддерживается|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `Required`.|  
|NotSupported|Свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `false`.<br /><br /> Атрибут `TransactionFlow` в элементе привязки имеет значение `false`.|  
|Отключено|Прямого эквивалента не существует. В общем случае необходимо принимать поведение, заданное для `NotSupported`.|
