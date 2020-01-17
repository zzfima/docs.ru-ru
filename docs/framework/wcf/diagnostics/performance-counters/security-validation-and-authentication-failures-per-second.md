---
title: Количество сбоев при проверке безопасности и проверке подлинности в секунду
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 546d81b73e912915d265fb194de4ad9e45d55cea
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163921"
---
# <a name="security-validation-and-authentication-failures-per-second"></a>Количество сбоев при проверке безопасности и проверке подлинности в секунду
Имя счетчика: Security Validation and Authentication Failures Per Second.  
  
## <a name="description"></a>Описание  
 Значение этого счетчика увеличивается всякий раз, когда сообщение отклоняется из-за проблемы безопасности, не относящейся к счетчику "Security Calls Not Authorized". К таким проблемам относятся следующие.  
  
- Невозможно прочесть в этом сообщении маркер клиента.  
  
- Маркер клиента не прошел проверку подлинности (например, неправильный пароль).  
  
- Сбой при проверке подписи (например, сообщение было искажено).  
  
- Сообщение является копией предыдущего, что может свидетельствовать об атаке воспроизведения.  
  
- Произошел сбой при расшифровке.  
  
- В сообщении отсутствуют некоторые обязательные элементы (например, отсутствует отметка времени или зашифрованный блок данных).  
  
- Во время подтверждения TLSNEGO/SPNEGO произошли ошибки.  
  
 This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:  
  
 (N1-N0)/((D1-D0)/F)
