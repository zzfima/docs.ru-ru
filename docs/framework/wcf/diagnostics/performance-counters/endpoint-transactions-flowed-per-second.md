---
title: "Конечная точка: количество поступивших транзакций в секунду"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58d1bec0110d669258e8f003cb1e882207133a5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-transactions-flowed-per-second"></a>Конечная точка: количество поступивших транзакций в секунду
Имя счетчика: Transactions Flowed Per Second.  
  
## <a name="description"></a>Описание  
 Количество транзакций, поступивших в операции в этой конечной точке в секунду. Значение этого счетчика увеличивается каждый раз, когда в сообщении, отправленном в эту конечную точку, содержится идентификатор транзакции.  
  
 Этот счетчик является счетчиком производительности типа [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), значение которого вычисляется по следующей формуле.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
