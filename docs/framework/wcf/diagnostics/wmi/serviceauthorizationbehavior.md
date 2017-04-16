---
title: "ServiceAuthorizationBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## Синтаксис  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## Методы  
 Класс ServiceAuthorizationBehavior не определяет никаких методов.  
  
## Свойства  
 Класс ServiceAuthorizationBehavior имеет следующие свойства.  
  
### ImpersonateCallerForAllOperations  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.  
  
### PrincipalPermissionMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Участник, используемый для выполнения операций на сервере.  
  
### RoleProvider  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя поставщика ролей ASP.NET.  
  
### ServiceAuthorizationManager  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Диспетчер авторизации, используемый для пользовательской авторизации.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>