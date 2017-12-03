---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 339ba8df7e782281fcec962ff6c6f01988122b3a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
При попытке повторного использования подключения в пуле произошел сбой. По истечении заданного промежутка времени выполнена еще одна попытка.  
  
## <a name="description"></a>Описание  
 Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка. Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно. Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
