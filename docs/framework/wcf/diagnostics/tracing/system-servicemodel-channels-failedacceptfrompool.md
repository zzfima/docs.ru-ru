---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: 59bba87095931c80a7ce347def2656a7a1f6f949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479322"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a>System.ServiceModel.Channels.FailedAcceptFromPool
При попытке повторного использования подключения в пуле произошел сбой. По истечении заданного промежутка времени выполнена еще одна попытка.  
  
## <a name="description"></a>Описание  
 Данная информационная трассировка показывает, что при попытке повторного использования подключения в пуле произошла ошибка. Ошибка могла произойти из-за несовместимости или неготовности подключения в пуле, либо того, что оно до сих пор активно. Дополнительные попытки повторного использования другого подключения в пуле предпринимаются по истечении заданного промежутка времени, и если не найдено ни одного используемого подключения, создается новое подключение.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
