---
title: "Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6dc0763ef829c814b069488221ceb921e09b3d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Конечная точка: количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Описание  
 Общее количество сообщений системы надежного обмена сообщениями, которое было отброшено в данной конечной точке в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
