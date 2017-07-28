---
title: "Привязка безопасности сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Привязка безопасности сообщений
Данный раздел содержит образцы, которые демонстрируют привязку безопасности сообщений в службах Windows в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## В этом подразделе  
 [Безопасность сообщений с возможностью анонимного доступа](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 В этом образце показана реализация приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с использованием безопасности уровня сообщений, без проверки подлинности клиента, но с требованием проверки подлинности сервера с помощью сертификата X.509 для сервера.  
  
 [Сертификат безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS\-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.  
  
 [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS\-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.  
  
 [Безопасность сообщений с использованием механизмов Windows](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.