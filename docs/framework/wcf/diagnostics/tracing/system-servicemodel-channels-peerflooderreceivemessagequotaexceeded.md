---
title: System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
ms.date: 03/30/2017
ms.assetid: b8371d0a-843e-440b-b86a-6996db131cb0
ms.openlocfilehash: 3ce6b3021f47708c222c3ec5a88d474d17106748
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500997"
---
# <a name="systemservicemodelchannelspeerflooderreceivemessagequotaexceeded"></a>System.ServiceModel.Channels.PeerFlooderReceiveMessageQuotaExceeded
Скорость получения входящих сообщений слишком высока.  
  
## <a name="description"></a>Описание  
 Эта трассировка возникает при попытке обработки входящих сообщений. Не удалось перенаправить сообщение конкретному соседнему узлу, так как была превышена квота, заданная для этого узла. Это происходит, если соседнему узлу, который не отвечает, не удается очистить журнал ожидания сообщений для этого узла.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Необходимо снизить частоту отправки сообщений в этой сетке.  
  
## <a name="see-also"></a>См. также
- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
