---
title: "Исключения при обработке транзакций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5896f1f7e15fa7ed86f80bbd7c06ae77faded90
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-exceptions"></a>Исключения при обработке транзакций
В этом разделе перечислены все исключения, создаваемые транзакцией [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Сведения политики, импортируемые из метаданных, задают различные значения TransactionProtocol для различных операций. Поддерживается только одно значение TransactionProtocol для каждой конечной точки.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete не может иметь значение false, если InstanceContextMode службы имеет значение PerSession. Обнаружена ошибка в реализации заданных контракта и операции.|  
|SFxTransactionInvalidSetTransactionComplete|Метод OperationContext.SetTransactionComplete может вызываться в операции, только если TransactionAutoComplete имеет значение false, а TransactionScopeRequired имеет значение true. Это недопустимый сценарий, и текущая транзакция была завершена.|  
|TransactionFlowRequiredIssuedTokens|Для передачи транзакций требуется поддержка потока выданных маркеров.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Настроенная версия Trust не поддерживает выданные маркеры. Используйте WSTrustFeb2005 или более позднюю версию.|
