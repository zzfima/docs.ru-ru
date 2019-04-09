---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.date: 03/30/2017
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
ms.openlocfilehash: 2de1aa51d58d9d86f953e027fd3f7f172e3887d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097568"
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
Согласование протокола OleTransactions невозможно завершить для заданного контекста координации.  
  
## <a name="description"></a>Описание  
 Трассируется, если входящая транзакция с информацией OleTx не может использовать прикрепленную информацию OleTx и вместо этого использует WS-AT.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Показывает возможную проблему обмена данными MSDTC RPC между компьютерами. Появление большого количества таких трассировок в журнале может привести к значительному снижению производительности.  Если информация OleTx не требуется, установите `OleTxUpgradeEnabled` на значение 0 в конфигурации реестра WS-AT.  
  
## <a name="see-also"></a>См. также

- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
