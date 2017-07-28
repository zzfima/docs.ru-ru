---
title: "ServiceCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceCredentials
ServiceCredentials  
  
## Синтаксис  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## Методы  
 Класс ServiceCredentials не определяет никаких методов.  
  
## Свойства  
 Класс ServiceCredentials имеет следующие свойства.  
  
### ClientCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности сертификата клиента и подготовки для этой службы.  
  
### IssuedTokenAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности текущего выданного маркера для этой службы.  
  
### Peer  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Текущие параметры проверки подлинности учетных данных и подготовки для использования конечными точками однорангового транспорта.  
  
### SecureConversationAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает текущие параметры безопасного обмена данными.  
  
### ServiceCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Сертификат, связанный с этой службой.  
  
### UserNameAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки имени пользователя и пароля для данной службы.  
  
### WindowsAuthentication  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры проверки подлинности Windows для этой службы.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceCredentials>