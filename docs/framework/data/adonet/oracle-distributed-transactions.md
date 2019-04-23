---
title: Распределенные транзакции Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116221"
---
# <a name="oracle-distributed-transactions"></a>Распределенные транзакции Oracle
Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна. Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений. Автоматическое прикрепление к существующим транзакциям можно отменить, задав  
  
```  
Enlist=false  
```  
  
 в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.  
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
