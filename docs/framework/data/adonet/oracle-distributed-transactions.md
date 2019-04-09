---
title: Распределенные транзакции Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116221"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="b201e-102">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="b201e-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="b201e-103">Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="b201e-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="b201e-104">Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений.</span><span class="sxs-lookup"><span data-stu-id="b201e-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="b201e-105">Автоматическое прикрепление к существующим транзакциям можно отменить, задав</span><span class="sxs-lookup"><span data-stu-id="b201e-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="b201e-106">в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="b201e-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b201e-107">См. также</span><span class="sxs-lookup"><span data-stu-id="b201e-107">See also</span></span>

- [<span data-ttu-id="b201e-108">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b201e-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="b201e-109">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="b201e-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
