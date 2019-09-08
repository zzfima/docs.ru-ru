---
title: Практическое руководство. Как прямо выполнять команды SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 3f28351a29915bebd698e00113bb05647d8412b4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781992"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="7248c-102">Практическое руководство. Как прямо выполнять команды SQL</span><span class="sxs-lookup"><span data-stu-id="7248c-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="7248c-103">Если предположить наличие подключения <xref:System.Data.Linq.DataContext>, для выполнения команд, которые не возвращают объекты, можно воспользоваться методом <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>.</span><span class="sxs-lookup"><span data-stu-id="7248c-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7248c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="7248c-104">Example</span></span>  
 <span data-ttu-id="7248c-105">В следующем примере SQL Server увеличивает цену за единицу на 1.</span><span class="sxs-lookup"><span data-stu-id="7248c-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7248c-106">См. также</span><span class="sxs-lookup"><span data-stu-id="7248c-106">See also</span></span>

- [<span data-ttu-id="7248c-107">Практическое руководство. Выполнение запросов SQL напрямую</span><span class="sxs-lookup"><span data-stu-id="7248c-107">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="7248c-108">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="7248c-108">Communicating with the Database</span></span>](communicating-with-the-database.md)
