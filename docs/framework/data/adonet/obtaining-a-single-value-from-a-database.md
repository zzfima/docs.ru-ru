---
title: "Получение одного значения из базы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 513310ddfb578f127ee70059dec386f207180907
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="3b851-102">Получение одного значения из базы данных</span><span class="sxs-lookup"><span data-stu-id="3b851-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="3b851-103">Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных.</span><span class="sxs-lookup"><span data-stu-id="3b851-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="3b851-104">Например, может потребоваться вернуть результат агрегатной функции, например COUNT (\*), SUM(Price) или AVG(Quantity).</span><span class="sxs-lookup"><span data-stu-id="3b851-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="3b851-105">**Команда** объект предоставляет возможность возвращать одиночные значения при помощи **ExecuteScalar** метод.</span><span class="sxs-lookup"><span data-stu-id="3b851-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="3b851-106">**ExecuteScalar** метод возвращает в виде скалярного значения, значение первого столбца первой строки результирующего набора.</span><span class="sxs-lookup"><span data-stu-id="3b851-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="3b851-107">В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение.</span><span class="sxs-lookup"><span data-stu-id="3b851-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="3b851-108">Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.</span><span class="sxs-lookup"><span data-stu-id="3b851-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3b851-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3b851-109">See Also</span></span>  
 [<span data-ttu-id="3b851-110">Команды и параметры</span><span class="sxs-lookup"><span data-stu-id="3b851-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="3b851-111">Выполнение команды</span><span class="sxs-lookup"><span data-stu-id="3b851-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="3b851-112">DbConnection, DbCommand и DbException</span><span class="sxs-lookup"><span data-stu-id="3b851-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="3b851-113">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3b851-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
