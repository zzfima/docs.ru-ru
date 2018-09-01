---
title: Количество поступивших транзакций в секунду
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392940"
---
# <a name="transactions-flowed-per-second"></a>Количество поступивших транзакций в секунду
Имя счетчика: Количество поступивших транзакций в секунду  
  
## <a name="description"></a>Описание  
 Количество транзакций в операции в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправляемом в операцию, содержится идентификатор транзакции.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
