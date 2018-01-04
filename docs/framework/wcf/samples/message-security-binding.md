---
title: "Привязка безопасности сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4570ce7-864e-461b-85d8-0f7bcc53c2c8
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f0c8b125d3fc313dca4140b871ccea8165329fda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-binding"></a>Привязка безопасности сообщений
Данный раздел содержит образцы, которые демонстрируют привязку безопасности сообщений в службах Windows в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="in-this-section"></a>В этом разделе  
 [Безопасность сообщений с возможностью анонимного доступа](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 В этом образце показана реализация приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с использованием безопасности уровня сообщений, без проверки подлинности клиента, но с требованием проверки подлинности сервера с помощью сертификата X.509 для сервера.  
  
 [Сертификат безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.  
  
 [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.  
  
 [Безопасность сообщений с использованием механизмов Windows](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.
