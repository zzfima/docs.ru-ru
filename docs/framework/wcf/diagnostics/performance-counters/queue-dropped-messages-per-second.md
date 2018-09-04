---
title: Количество удаленных из очереди сообщений в секунду
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528127"
---
# <a name="queue-dropped-messages-per-second"></a>Количество удаленных из очереди сообщений в секунду
Имя счетчика: Queued Messages Dropped Per Second.  
  
## <a name="description"></a>Описание  
 Количество сообщений, отброшенных транспортом очередей этой службы за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
