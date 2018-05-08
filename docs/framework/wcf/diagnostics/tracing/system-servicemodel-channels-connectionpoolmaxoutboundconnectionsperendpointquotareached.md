---
title: Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
ms.date: 03/30/2017
ms.assetid: 1b9f5139-e122-4716-9ef7-2f38e1813993
ms.openlocfilehash: 9dd2ba5a3e94ff794d4b8a8775944355b105f790
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="microsofttransactionstransactionbridgeenlisttransactionfailure"></a>Microsoft.Transactions.TransactionBridge.EnlistTransactionFailure
Службе протокола WS-AT не удалось включить в список транзакцию, используя предоставленный контекст координации.  
  
## <a name="description"></a>Описание  
 Регистрируется, если координатору MSDTC не удалось включить в список транзакцию для заданного протокола 2pc.  Это может произойти, если транзакция больше не существует, включение в список уже запрещено или если уже имеется слишком много перечислений.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
