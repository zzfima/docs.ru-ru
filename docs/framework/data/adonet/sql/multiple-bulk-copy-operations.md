---
title: Несколько операций массового копирования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: 7ba9938352b4ec5e2fe86af1173c09917e266ec2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693841"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="5fe5b-102">Несколько операций массового копирования</span><span class="sxs-lookup"><span data-stu-id="5fe5b-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="5fe5b-103">Несколько операций массового копирования можно выполнять при помощи одного экземпляра класса <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="5fe5b-104">Если параметры операции изменяются между копии (например, имя целевой таблицы), необходимо обновить их до последующих вызовов к любому из **WriteToServer** методы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="5fe5b-105">Значения всех свойств, если они не были явно изменены, остаются такими же, какие они были в предыдущей операции массового копирования для данного экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fe5b-106">Выполнение нескольких операций массового копирования при помощи одного экземпляра объекта <xref:System.Data.SqlClient.SqlBulkCopy> обычно более эффективно, чем использование отдельного экземпляра для каждой операции.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="5fe5b-107">При выполнении нескольких операций массового копирования с помощью одного объекта <xref:System.Data.SqlClient.SqlBulkCopy> нет ограничений в отношении того, отличается ли исходная и целевая информация в каждой операции или является одинаковой.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="5fe5b-108">Однако каждый раз при записи на сервер необходимо проверять, что сведения ассоциирования столбцов заданы правильно.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5fe5b-109">Этот пример не будет работать, пока вы не создадите рабочие таблицы, как описано в разделе [Установка примера массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="5fe5b-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="5fe5b-110">Этот код предоставляется для демонстрации синтаксиса использования **SqlBulkCopy** только.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="5fe5b-111">Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="5fe5b-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5fe5b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5fe5b-112">See also</span></span>
- [<span data-ttu-id="5fe5b-113">Операции массового копирования в SQL Server</span><span class="sxs-lookup"><span data-stu-id="5fe5b-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="5fe5b-114">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5fe5b-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
