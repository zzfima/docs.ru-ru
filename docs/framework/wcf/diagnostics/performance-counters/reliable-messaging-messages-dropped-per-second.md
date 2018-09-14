---
title: Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45518991"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a>Количество отброшенных сообщений, передаваемых по надежным каналам, в секунду
Имя счетчика: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>Описание  
 Общее количество надежных сообщений, которые были отклонены в данной службе в течение секунды.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
