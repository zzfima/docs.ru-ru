---
title: Объединение подключений в пул
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 28a1036f377326b5f1fdfafa1eaffd8a47bc05bc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43876613"
---
# <a name="connection-pooling"></a><span data-ttu-id="533a1-102">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="533a1-102">Connection Pooling</span></span>
<span data-ttu-id="533a1-103">На соединение с источником данных может требоваться значительное время.</span><span class="sxs-lookup"><span data-stu-id="533a1-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="533a1-104">Чтобы свести к минимуму стоимость открытия соединения, в ADO.NET используется техника *организация пулов соединений*, который позволяет минимизировать затраты на часто открываемые и закрываемые соединения.</span><span class="sxs-lookup"><span data-stu-id="533a1-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="533a1-105">Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.</span><span class="sxs-lookup"><span data-stu-id="533a1-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="533a1-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="533a1-106">In This Section</span></span>  
 [<span data-ttu-id="533a1-107">Объединение подключений в пул в SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="533a1-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="533a1-108">Общие сведения о пулы соединений и Описание принципов работы пулов соединений в SQL Server.</span><span class="sxs-lookup"><span data-stu-id="533a1-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="533a1-109">Организация пулов соединений OLE DB, ODBC и Oracle</span><span class="sxs-lookup"><span data-stu-id="533a1-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="533a1-110">Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="533a1-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533a1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="533a1-111">See Also</span></span>  
 [<span data-ttu-id="533a1-112">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="533a1-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="533a1-113">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="533a1-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
