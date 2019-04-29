---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 79601308c66abe43dd5a7f72bd2a05b9d2346c2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963050"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс OperationBehaviorAttribute не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс OperationBehaviorAttribute имеет следующие свойства.  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Состояние возможности автоматического удаления для параметров.  
  
### <a name="impersonation"></a>Олицетворение  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Указывает, когда удалять объект в процессе вызова операции.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, требует ли операция транзакции.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.OperationBehaviorAttribute>
