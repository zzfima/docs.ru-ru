---
title: Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187128"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a>Количество надежных сеансов обмена сообщениями, в которых произошел сбой, в секунду
Имя счетчика: Reliable Messaging Sessions Faulted Per Second.  
  
## <a name="description"></a>Описание  
 Количество надежных сессий обмена сообщениями этой службы, в которых произошел сбой в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
