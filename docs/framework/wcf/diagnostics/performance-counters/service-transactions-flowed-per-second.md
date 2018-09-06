---
title: 'Служба: количество поступивших транзакций в секунду'
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: cb41abe74568c3e9641443b81fce3fb6eb6e41bf
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874944"
---
# <a name="service-transactions-flowed-per-second"></a>Служба: количество поступивших транзакций в секунду
Имя счетчика: Transactions Flowed Per Second.  
  
## <a name="description"></a>Описание  
 Количество транзакций в операциях для данной службы в секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
