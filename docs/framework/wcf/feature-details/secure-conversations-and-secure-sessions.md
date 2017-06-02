---
title: "Безопасные диалоги и безопасные сеансы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 48cb104a-532d-40ae-aa57-769dae103fda
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Безопасные диалоги и безопасные сеансы
Функцией [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] является возможность установления безопасных сеансов между двумя конечными точками, проверяющими подлинность друг друга и согласующими процесс шифрования и цифровой подписи.Например, конечная точка службы может требовать, чтобы клиентская конечная точка передавала для проверки подлинности маркер безопасности, основанный на сертификате X.509.После завершения проверки подлинности клиента конечная точка службы возвращает клиенту маркер контекста безопасности \(SCT\), который затем используется для обеспечения безопасности всех последующих сообщений в сеансе.Установление такого безопасного сеанса повышает эффективность набора сообщений, которыми обмениваются эти две конечные точки, так как маркер SCT имеет симметричный ключ.При создании цифровой подписи или шифровании набора данных асимметричные ключи, на которых основаны сертификаты X.509, требуют значительно большей вычислительной мощности, чем симметричные ключи.  
  
 Политика начальной загрузки \(определенная в разделе 6.2.7 стандарта [WS\-SecurityPolicy](http://go.microsoft.com/fwlink/?LinkId=99817)\) содержит утверждения безопасности сообщений, используемые для обеспечения безопасности канала и проверки подлинности клиента до обмена маркерами RST\/SCT и RSTR\/SCT.Определенные стандартные привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] обладают свойством `Security.Message.EstablishSecurityContext`, управляющим использованием безопасного диалога.При использовании пользовательских привязок начальная загрузка указывается путем вложения элементов безопасной привязки, либо с помощью элемента [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> в файле конфигурации, либо путем вызова метода в коде.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] сеансах см. в разделе [Использование сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
## См. также  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)   
 [Как создать службу, для которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)