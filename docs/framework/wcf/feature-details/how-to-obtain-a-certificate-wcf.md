---
title: "Как получить сертификат (WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сертификаты [WCF], получение"
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как получить сертификат (WCF)
Чтобы воспользоваться какими\-либо функциями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые используют сертификаты X.509, сначала нужно получить сертификаты.  
  
### Получение сертификата X.509  
  
1.  Выберите один из следующих вариантов.  
  
    -   Приобретите сертификат в центре сертификации, например VeriSign, Inc.  
  
    -   Создайте собственную службу сертификатов и настройте ее так, чтобы центр сертификации подписывал сертификаты.  [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], Windows 2000 Server, Windows 2000 Server Datacenter и Windows 2000 Datacenter Server включают службы сертификатов, поддерживающие инфраструктуру открытых ключей \(PKI\).  В Windows Server 2008 используйте роль [служб сертификации Active Directory](http://go.microsoft.com/fwlink/?LinkID=153483) для управления центром сертификации.  
  
    -   Создайте собственную службу сертификатов и не настраивайте подпись сертификатов.  
  
    > [!NOTE]
    >  Независимо от того, какой способ выбран, получатель запроса SOAP, который содержит сертификат X.509, должен доверять сертификату X.509.  Это означает, что сертификат X.509 или издатель в цепи сертификатов находится в хранилище сертификатов "Доверенные лица" и сертификат X.509 не помещен в хранилище ненадежных сертификатов.  
  
## См. также  
 [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Практическое руководство. Создание временных сертификатов для использования во время разработки](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)