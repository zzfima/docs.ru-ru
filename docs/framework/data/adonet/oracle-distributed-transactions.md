---
title: Распределенные транзакции Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 6f910f1dbbe448352c0edd5d1b80df659ac453d4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795145"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="47d08-102">Распределенные транзакции Oracle</span><span class="sxs-lookup"><span data-stu-id="47d08-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="47d08-103">Объект <xref:System.Data.OracleClient.OracleConnection> автоматически прикрепляется к существующей распределенной транзакции, если он определяет, что транзакция активна.</span><span class="sxs-lookup"><span data-stu-id="47d08-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="47d08-104">Автоматическое прикрепление к транзакции происходит при открытии соединения или его получении из пула соединений.</span><span class="sxs-lookup"><span data-stu-id="47d08-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="47d08-105">Автоматическое прикрепление к существующим транзакциям можно отменить, задав</span><span class="sxs-lookup"><span data-stu-id="47d08-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="47d08-106">в качестве параметра строки соединения для <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="47d08-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d08-107">См. также</span><span class="sxs-lookup"><span data-stu-id="47d08-107">See also</span></span>

- [<span data-ttu-id="47d08-108">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47d08-108">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="47d08-109">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="47d08-109">ADO.NET Overview</span></span>](ado-net-overview.md)
