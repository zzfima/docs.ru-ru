---
title: Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
ms.date: 03/30/2017
ms.assetid: 2dbe34c5-57c7-4b64-9257-63021911d03c
ms.openlocfilehash: 22992b4dfad4b4867adda0fcbbd8ecc5eb67d87e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160152"
---
# <a name="microsofttransactionstransactionbridgevolatileoutcometimeout"></a>Microsoft.Transactions.TransactionBridge.VolatileOutcomeTimeout
Истекло время ожидания службой протокола WS-AT ответа на результативное сообщение от неустойчивого участника. При возвращении участника результат транзакции будет поставлен под сомнение.  
  
## <a name="description"></a>Описание  
 Трассируется, когда неустойчивый участник принял решение зафиксировать или прервать транзакцию, однако не ответил на сообщение Commit или Rollback в течение заданного времени.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Убедитесь, что все неустойчивые участники имеют возможность ответить в течение заданного времени. Период времени по умолчанию - 180 секунд.  Если этого недостаточно, увеличьте значение политики таймера `VolatileOutcomeDelay` для протокола WS-AT.  
  
## <a name="see-also"></a>См. также

- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
