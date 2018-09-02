---
title: Количество прерванных операций с поддержкой транзакций в секунду
ms.date: 03/30/2017
ms.assetid: 19fc993f-2b3d-4898-852e-3b98ec2153a5
ms.openlocfilehash: 6369fea6def5ebb6b62274caed31d5fb63b3b0e1
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417486"
---
# <a name="transacted-operations-aborted-per-second"></a>Количество прерванных операций с поддержкой транзакций в секунду
Имя счетчика: Количество прерванных операций с поддержкой транзакций в секунду.  
  
## <a name="description"></a>Описание:  
 Количество транзакционных операций, прерванных в этой службе за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
