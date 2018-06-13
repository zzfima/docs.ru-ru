---
title: Практическое руководство. Непосредственное выполнение команд SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 90fb0d7027946ce4f38c2ba4930ac3510e2a42b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351876"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="f431c-102">Практическое руководство. Непосредственное выполнение команд SQL</span><span class="sxs-lookup"><span data-stu-id="f431c-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="f431c-103">Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="f431c-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f431c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f431c-104">Example</span></span>  
 <span data-ttu-id="f431c-105">В следующем примере SQL Server увеличивает цену за единицу на 1.</span><span class="sxs-lookup"><span data-stu-id="f431c-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="f431c-106">См. также</span><span class="sxs-lookup"><span data-stu-id="f431c-106">See Also</span></span>  
 [<span data-ttu-id="f431c-107">Практическое руководство. Непосредственное выполнение запросов SQL</span><span class="sxs-lookup"><span data-stu-id="f431c-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="f431c-108">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="f431c-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
