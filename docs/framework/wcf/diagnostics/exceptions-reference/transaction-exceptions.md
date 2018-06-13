---
title: Исключения при обработке транзакций
ms.date: 03/30/2017
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
ms.openlocfilehash: 85d8d043a5610743d6cbad4d950330ed4bedb502
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474835"
---
# <a name="transaction-exceptions"></a>Исключения при обработке транзакций
В этом разделе перечислены все исключения, вызываемые транзакции Windows Communication Foundation (WCF).  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|Сведения политики, импортируемые из метаданных, задают различные значения TransactionProtocol для различных операций. Поддерживается только одно значение TransactionProtocol для каждой конечной точки.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|TransactionAutoComplete не может иметь значение false, если InstanceContextMode службы имеет значение PerSession. Обнаружена ошибка в реализации заданных контракта и операции.|  
|SFxTransactionInvalidSetTransactionComplete|Метод OperationContext.SetTransactionComplete может вызываться в операции, только если TransactionAutoComplete имеет значение false, а TransactionScopeRequired имеет значение true. Это недопустимый сценарий, и текущая транзакция была завершена.|  
|TransactionFlowRequiredIssuedTokens|Для передачи транзакций требуется поддержка потока выданных маркеров.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|Настроенная версия Trust не поддерживает выданные маркеры. Используйте WSTrustFeb2005 или более позднюю версию.|
