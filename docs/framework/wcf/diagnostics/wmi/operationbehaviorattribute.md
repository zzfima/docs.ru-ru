---
title: "OperationBehaviorAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## Синтаксис  
  
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
  
## Методы  
 Класс OperationBehaviorAttribute не определяет никаких методов.  
  
## Свойства  
 Класс OperationBehaviorAttribute имеет следующие свойства.  
  
### AutoDisposeParameters  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Состояние функции автоматического удаления для параметров.  
  
### Impersonation  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает уровень олицетворения вызывающей стороны, который поддерживает операция.  
  
### ReleaseInstanceMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, когда удалять объект в процессе вызова операции.  
  
### TransactionAutoComplete  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, следует ли автоматически фиксировать текущую транзакцию при отсутствии необработанных исключений.  
  
### TransactionScopeRequired  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, требует ли операция транзакции.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.OperationBehaviorAttribute>