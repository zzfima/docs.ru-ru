---
title: Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45625514"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## <a name="description"></a>Описание  
 Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
