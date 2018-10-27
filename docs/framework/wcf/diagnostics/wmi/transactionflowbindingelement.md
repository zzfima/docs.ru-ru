---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 027ace6ea9fc2a0e5ce63efa84e1a49c0ed2cd0a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188031"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
