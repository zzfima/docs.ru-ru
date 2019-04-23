---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 591e1a1dcb6746d79ff5eceba7e74e890f327354
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112662"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a>System.ServiceModel.TxCompletionStatusCompletedForError
Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.  
  
## <a name="description"></a>Описание  
 Трассируется, если при попытке завершить текущую транзакцию возникает ошибка. Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.  
  
## <a name="see-also"></a>См. также

- [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
