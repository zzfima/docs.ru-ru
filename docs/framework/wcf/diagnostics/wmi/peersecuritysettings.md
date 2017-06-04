---
title: "PeerSecuritySettings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# PeerSecuritySettings
PeerSecuritySettings  
  
## Синтаксис  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## Методы  
 Класс PeerSecuritySettings не определяет никаких методов.  
  
## Свойства  
 Класс PeerSecuritySettings имеет следующие свойства.  
  
### Mode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.  
  
### Transport  
 Тип данных: PeerTransportSecuritySettings  
  
 Тип доступа: только для чтения  
  
 Параметры безопасности транспорта.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.PeerSecuritySettings>