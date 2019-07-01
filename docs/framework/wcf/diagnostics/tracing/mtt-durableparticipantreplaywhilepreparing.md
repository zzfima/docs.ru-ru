---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 93354fbdd0c1726280526ca07a8b3dd1c57c8a25
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486767"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение. Поэтому транзакция была прервана.  
  
## <a name="description"></a>Описание  
 Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки. Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.  
  
## <a name="troubleshooting"></a>Устранение неполадок

Такая ошибка может указывать, что постоянный участник (включая подчиненные диспетчеры транзакций) был восстановлен после сбоя; Тем не менее результат транзакции не известен и запрашивает его состояние.  
  
## <a name="see-also"></a>См. также

- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
