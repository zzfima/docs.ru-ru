---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485624"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс TransactionFlowBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс TransactionFlowBindingElement имеет следующие свойства.  
  
### <a name="issuedtokens"></a>IssuedTokens  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает требование для заголовка выданных маркеров безопасности (IssuedTokens из WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Протокол транзакций, используемый службой для передачи транзакций.  
  
### <a name="transactions"></a>Транзакции  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, поддерживается ли входящая транзакция.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
