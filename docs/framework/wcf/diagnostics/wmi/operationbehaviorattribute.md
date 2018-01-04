---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63824ae2171053bee2af204e748a6fa811f2ba82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
