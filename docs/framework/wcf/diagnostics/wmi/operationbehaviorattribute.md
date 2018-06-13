---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 4f731d146885265d9f956c182f1bebdba5db924b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486875"
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
 Тип доступа: только для чтения  
  
 Состояние функции автоматического удаления для параметров.  
  
### <a name="impersonation"></a>Олицетворение  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.  
  
### <a name="releaseinstancemode"></a>ReleaseInstanceMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, когда удалять объект в процессе вызова операции.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, требует ли операция транзакции.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
