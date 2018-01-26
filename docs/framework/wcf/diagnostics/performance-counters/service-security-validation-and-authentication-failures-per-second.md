---
title: "Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 85e6dae6b8358799370079c52c3d04e7c3221b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a>Служба: количество сбоев при проверке безопасности и проверке подлинности в секунду
Имя счетчика: Security Validation and Authentication Failures Per Second.  
  
## <a name="description"></a>Описание:  
 Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized". К таким проблемам относятся следующие.  
  
-   Невозможно прочесть в этом сообщении маркер клиента.  
  
-   Маркер клиента не прошел проверку подлинности (например, неправильный пароль).  
  
-   Сбой при проверке подписи (например, сообщение было искажено).  
  
-   Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.  
  
-   Произошел сбой при расшифровке.  
  
-   В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).  
  
-   Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
