---
title: "Конечная точка: количество сбоев при проверке безопасности и проверке подлинности в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f457a3067a4ada3ea226bf289c9c559ef5e35594
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>Конечная точка: количество сбоев при проверке безопасности и проверке подлинности в секунду
Имя счетчика: Security Validation and Authentication Failures Per Second  
  
## <a name="description"></a>Описание:  
 Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized". К таким проблемам относятся следующие.  
  
-   Невозможно прочесть в этом сообщении маркер клиента.  
  
-   Маркер клиента не прошел проверку подлинности (например, неправильный пароль).  
  
-   Сбой при проверке подписи (например, сообщение было искажено).  
  
-   Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.  
  
-   Произошел сбой при расшифровке.  
  
-   В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует метка времени или зашифрованный блок данных).  
  
-   Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле:  
  
 (N1-N0)/((D1-D0)/F)
