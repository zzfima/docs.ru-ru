---
title: System.ServiceModel.Channels.PeerMaintainerActivity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef28d086-d7fb-4e81-82e9-45a54647783b
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3cde90bf5e9c57ff54378eaaf970aec219871a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
