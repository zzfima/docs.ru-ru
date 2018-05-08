---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.date: 03/30/2017
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
ms.openlocfilehash: a7f353b00796c845f5686ca2926bbe7effe09e3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="systemservicemodelchannelspeermaintaineractivity"></a>System.ServiceModel.Channels.PeerMaintainerActivity
Модуль PeerMaintainer выполняет определенную операцию (подробности содержатся в теле сообщения трассировки).  
  
## <a name="description"></a>Описание  
 Эта трассировка возникает в ходе различных операций модуля обслуживания PeerMaintainer.  
  
 PeerMaintainer - это внутренний компонент узла PeerNode. Каждую минуту или каждые 32 полученных сообщения он отправляет соседним узлам сообщение LinkUtility со статистическими данными о том, сколько сообщений было принято/отправлено и сколько из них полезны (не дубликаты, не подделаны). Это позволяет определить значение LinkUtility определенного соседнего узла. Приблизительно каждые пять минут модуль обслуживания проверяет состояние соединений с соседними узлами. Если количество соединений с соседними узлами превышает идеальное число, модуль обслуживания урезает наименее полезные соединения. Если соединений недостаточно, модуль обслуживания приобретает новые соединения.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
