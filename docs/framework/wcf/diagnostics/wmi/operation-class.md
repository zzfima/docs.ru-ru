---
title: "Класс Operation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Класс Operation
Операция  
  
## Синтаксис  
  
```  
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## Методы  
 Класс Operation не определяет никаких методов.  
  
## Свойства  
 Класс Operation имеет следующие свойства.  
  
### Действие  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Действие WS\-Addressing сообщения запроса.  
  
### AsyncPattern  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, что операция реализуется асинхронно с использованием пары методов `Begin` \[открыть\/закрыть угловые скобки\] и `End` \[открыть\/закрыть угловые скобки\] в контракте службы.  
  
### Поведения  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этой операцией.  
  
### IsCallback  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Истинно, если операция является операцией обратного вызова.  
  
### IsInitiating  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, реализует ли метод операцию, которая может инициировать сеанс на сервере.  
  
### IsOneWay  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, возвращает ли операция ответное сообщение.  
  
### IsTerminating  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Показывает, возвращает ли операция ответное сообщение.  
  
### MethodSignature  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Подпись метода операции.  
  
### Name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя операции.  
  
### ParameterTypes  
 Тип данных: массив строк  
  
 Тип доступа: только для чтения  
  
 Типы параметров операции.  
  
### ReplyAction  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение действия SOAP для ответного сообщения операции.  
  
### ReturnType  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Возвращаемый тип операции.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.OperationDescription>