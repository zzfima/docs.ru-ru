---
title: "ServiceSecurityAuditBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## Синтаксис  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## Методы  
 Класс ServiceSecurityAuditBehavior не определяет никаких методов.  
  
## Свойства  
 Класс ServiceSecurityAuditBehavior имеет следующие свойства.  
  
### AuditLogLocation  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Местоположение журнала аудита.  
  
### MessageAuthenticationAuditLevel  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.  
  
### ServiceAuthorizationAuditLevel  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Типы событий авторизации, записываемых в журнал аудита.  
  
### SuppressAuditFailure  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>