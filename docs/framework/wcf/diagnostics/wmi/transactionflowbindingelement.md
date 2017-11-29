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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
