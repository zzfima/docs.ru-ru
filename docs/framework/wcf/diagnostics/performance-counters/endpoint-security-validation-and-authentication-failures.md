---
title: "Конечная точка: количество сбоев при проверке безопасности и проверке подлинности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 7d1f05ddc4b0fcf93c87e69932f860f3c7e2ff85
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>Конечная точка: количество сбоев при проверке безопасности и проверке подлинности
Имя счетчика: Security Validation and Authentication Failures  
  
## <a name="description"></a>Описание  
 Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized". К таким проблемам относятся следующие.  
  
-   Невозможно прочесть в этом сообщении маркер клиента.  
  
-   Токен клиента не прошел проверку подлинности (неправильный пароль).  
  
-   Сбой при проверке подписи (сообщение было изменено).  
  
-   Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.  
  
-   Произошел сбой при расшифровке.  
  
-   В сообщении отсутствуют некоторые обязательные элементы (отметка времени или зашифрованный блок данных).  
  
-   Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.
