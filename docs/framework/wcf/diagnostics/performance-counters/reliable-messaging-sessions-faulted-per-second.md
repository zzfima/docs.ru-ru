---
title: "Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c176adceb2404037d22a1e9ad3cebae1a8ce83e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## <a name="description"></a>Описание  
 Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
