---
title: Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
ms.date: 03/30/2017
ms.assetid: c3468e23-49a9-4a84-972d-a79a658851b3
ms.openlocfilehash: 968444947714315bae902d3d038129c5b8a04cf2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082520"
---
# <a name="microsofttransactionstransactionbridgecreatetransactionfailure"></a>Microsoft.Transactions.TransactionBridge.CreateTransactionFailure
Невозможно создать транзакцию.  
  
## <a name="description"></a>Описание  
 Данная трассировка создается, если MSDTC не может создать транзакцию. Это может быть вызвано недостаточным объемом ресурсов, отсутствием места в журнале или другими ошибками.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Проверьте строку состояния в сообщении трассировки и определите, имеются ли элементы, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также

- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
