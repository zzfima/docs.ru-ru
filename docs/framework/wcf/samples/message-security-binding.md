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
ms.openlocfilehash: ca1ce99fae09ef7d3c9ad3ea47984b671cadb27c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="message-security-binding"></a>Привязка безопасности сообщений
Данный раздел содержит образцы, которые демонстрируют привязку безопасности сообщений в службах Windows в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="in-this-section"></a>Содержание  
 [Анонимного обеспечения безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 В этом образце показана реализация приложения [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с использованием безопасности уровня сообщений, без проверки подлинности клиента, но с требованием проверки подлинности сервера с помощью сертификата X.509 для сервера.  
  
 [Сертификат безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-certificate.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.  
  
 [Имя пользователя для безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.  
  
 [Сообщение безопасности Windows](../../../../docs/framework/wcf/samples/message-security-windows.md)  
 В этом образце показывается, как настраивать привязку <xref:System.ServiceModel.WSHttpBinding> для использования безопасности на уровне сообщений с проверкой подлинности Windows.
