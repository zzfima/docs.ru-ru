---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa5394e874e35b80b01796642e18d69c71e867dc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
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
