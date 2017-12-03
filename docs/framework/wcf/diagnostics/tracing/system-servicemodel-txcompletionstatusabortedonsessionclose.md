---
title: System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 695ebb2089147093601f2d51f11f11ca45861590
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodeltxcompletionstatusabortedonsessionclose"></a>System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
Указанная транзакция прервана, поскольку она была незавершенной на момент закрытия сеанса и атрибуту TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute задано значение "false".  
  
## <a name="description"></a>Описание  
 Трассируется, если текущий активный сеанс был закрыт, транзакция не была завершена и TransactionAutoCompleteOnSessionClose имеет значение `false`.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Эта трассировка указывает о потенциальной ошибке в приложении, наличие которой требуется проверить.  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
