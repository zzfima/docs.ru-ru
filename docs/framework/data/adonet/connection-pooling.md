---
title: Объединение подключений в пул
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: c431011cf57fd9ef79c2f0a099ab1080116c571f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786710"
---
# <a name="connection-pooling"></a><span data-ttu-id="b00b8-102">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="b00b8-102">Connection Pooling</span></span>
<span data-ttu-id="b00b8-103">На соединение с источником данных может требоваться значительное время.</span><span class="sxs-lookup"><span data-stu-id="b00b8-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="b00b8-104">Для снижения затрат на открытие подключений ADO.NET использует методику оптимизации, называемую *объединением соединений*, что сокращает затраты на многократное открытие и закрытие подключений.</span><span class="sxs-lookup"><span data-stu-id="b00b8-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="b00b8-105">Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.</span><span class="sxs-lookup"><span data-stu-id="b00b8-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b00b8-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b00b8-106">In This Section</span></span>  
 [<span data-ttu-id="b00b8-107">Объединение подключений в пул в SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b00b8-107">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="b00b8-108">Содержит общие сведения о группировании соединений и описание работы пула подключений в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b00b8-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="b00b8-109">Организация пулов соединений OLE DB, ODBC и Oracle</span><span class="sxs-lookup"><span data-stu-id="b00b8-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="b00b8-110">Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="b00b8-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b00b8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b00b8-111">See also</span></span>

- [<span data-ttu-id="b00b8-112">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b00b8-112">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="b00b8-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b00b8-113">ADO.NET Overview</span></span>](ado-net-overview.md)
