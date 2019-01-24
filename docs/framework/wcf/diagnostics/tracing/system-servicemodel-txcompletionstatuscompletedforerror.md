---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: e36126dcdfcc87a410d200cdf23aac670dc2b5e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596516"
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
