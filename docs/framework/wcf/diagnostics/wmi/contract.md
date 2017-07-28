---
title: "Контракт | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Контракт
Контракт  
  
## Синтаксис  
  
```  
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## Методы  
 Класс контракта не определяет никаких методов.  
  
## Свойства  
 Класс контракта имеет следующие свойства.  
  
### AppDomainId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор домена приложения, который размещает контракт.  
  
### Behaviors  
 Тип данных: массив Behavior  
  
 Тип доступа: только для чтения  
  
 Поведения, связанные с этим контрактом.  
  
### Name  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя контракта в WSDL.  
  
### Namespace  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Пространство имен элемента `portType` в WSDL.  
  
### Operations  
 Тип данных: массив Operation  
  
 Тип доступа: только для чтения  
  
 Операции данного контракта.  
  
### ProcessId  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Идентификатор процесса, который размещает контракт.  
  
### ref  
 Тип данных: Contract  
  
 Тип доступа: только для чтения  
  
 Тип обратного вызова, когда контракт является дуплексным.  
  
### SessionMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, требуется ли для контракта, чтобы связанная с ним привязка использовала сеансы канала.  
  
### Type  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип контракта.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ContractDescription>