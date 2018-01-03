---
title: "Объединение подключений в пул"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5082adda3c03bfbc40eafb174513a39fe17a3da8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="connection-pooling"></a><span data-ttu-id="ea654-102">Объединение подключений в пул</span><span class="sxs-lookup"><span data-stu-id="ea654-102">Connection Pooling</span></span>
<span data-ttu-id="ea654-103">На соединение с источником данных может требоваться значительное время.</span><span class="sxs-lookup"><span data-stu-id="ea654-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="ea654-104">Чтобы свести к минимуму затраты на открытие соединения, в ADO.NET используется техника *организация пулов соединений*, которая позволяет минимизировать затраты на часто открываемые и закрываемые соединения.</span><span class="sxs-lookup"><span data-stu-id="ea654-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="ea654-105">Пулы соединений обрабатываются для поставщиков данных .NET Framework по-разному.</span><span class="sxs-lookup"><span data-stu-id="ea654-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea654-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ea654-106">In This Section</span></span>  
 [<span data-ttu-id="ea654-107">Объединение подключений в пул в SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="ea654-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="ea654-108">Общие сведения о пулах соединений и описание принципов работы пулов соединений в [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea654-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ea654-109">Организация пулов соединений OLE DB, ODBC и Oracle</span><span class="sxs-lookup"><span data-stu-id="ea654-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="ea654-110">Описание пулов соединений для поставщика данных .NET Framework для OLE DB, поставщика данных .NET Framework для ODBC и поставщика данных .NET Framework для Oracle.</span><span class="sxs-lookup"><span data-stu-id="ea654-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea654-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ea654-111">See Also</span></span>  
 [<span data-ttu-id="ea654-112">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea654-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="ea654-113">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea654-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
