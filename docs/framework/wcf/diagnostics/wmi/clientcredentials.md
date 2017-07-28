---
title: "ClientCredentials | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ClientCredentials
ClientCredentials  
  
## Синтаксис  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## Методы  
 Класс ClientCredentials не определяет никакие методы.  
  
## Свойства  
 Класс ClientCredentials имеет следующие свойства.  
  
### ClientCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Сертификат X.509, используемый клиентом для проверки подлинности службы.  
  
### HttpDigest  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Текущие учетные данные дайджеста HTTP.  
  
### IssuedToken  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Адрес конечной точки и привязка, используемые для связи с локальной службой маркеров безопасности.  
  
### Peer  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Учетные данные, используемые одноранговым узлом для подтверждения своей подлинности при подключении к другим узлам в сетке.  
  
### ServiceCertificate  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Сертификат X.509 службы.  
  
### SupportInteractive  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, определяющее, поддерживают ли учетные данные интерактивное согласование.  
  
### UserName  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя пользователя и пароль, используемые клиентом для подтверждения своей подлинности при подключении к службе.  
  
### Windows  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Учетные данные Windows, используемые клиентом для подтверждения своей подлинности при подключении к службе.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.Description.ClientCredentials>