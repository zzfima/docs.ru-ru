---
title: Количество сообщений из очереди, отклоненных за секунду
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916192"
---
# <a name="queued-rejected-messages-per-second"></a>Количество сообщений из очереди, отклоненных за секунду
Имя счетчика: В очереди сообщений, отклоненных за секунду.  
  
## <a name="description"></a>Описание  
 Количество сообщений, отклоненных транспортом очередей этой службы за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
