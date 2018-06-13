---
title: Количество экземпляров в секунду
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: c955d2cd0d87c89f412892e7088285f2db27ff42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471872"
---
# <a name="instances-per-second"></a>Количество экземпляров в секунду
Имя счетчика: Instances Created Per Second.  
  
## <a name="description"></a>Описание  
 Общее количество экземпляров службы, создаваемых за секунду.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
