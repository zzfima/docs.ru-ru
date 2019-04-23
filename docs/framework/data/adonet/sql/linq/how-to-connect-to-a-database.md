---
title: Практическое руководство. Как соединиться с базой данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: f04726bc12fdfbca530ee5533d5b8969addf962e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208141"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="4f79b-102">Практическое руководство. Как соединиться с базой данных</span><span class="sxs-lookup"><span data-stu-id="4f79b-102">How to: Connect to a Database</span></span>
<span data-ttu-id="4f79b-103">Основным каналом, через который выполняется подключение к базе данных, извлекаются объекты и отправляются изменения обратно в базу данных, является класс <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="4f79b-103">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="4f79b-104">Использовании <xref:System.Data.Linq.DataContext> так же, как использовалась бы [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="4f79b-104">You use the <xref:System.Data.Linq.DataContext> just as you would use an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="4f79b-105">В действительности класс <xref:System.Data.Linq.DataContext> инициализируется с помощью предоставляемого пользователем подключения или строки подключения.</span><span class="sxs-lookup"><span data-stu-id="4f79b-105">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="4f79b-106">Дополнительные сведения см. в разделе [методы DataContext (реляционный конструктор объектов)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="4f79b-106">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="4f79b-107">Класс <xref:System.Data.Linq.DataContext> предназначен для преобразования запросов на получение объектов в запросы SQL, которые должны выполняться в базе данных, и последующей сборки объектов из результатов.</span><span class="sxs-lookup"><span data-stu-id="4f79b-107">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="4f79b-108">Класс <xref:System.Data.Linq.DataContext> поддерживает технологию [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] посредством реализации шаблона операторов, аналогичного стандартным операторам запросов, такими как `Where` и `Select`.</span><span class="sxs-lookup"><span data-stu-id="4f79b-108">The <xref:System.Data.Linq.DataContext> enables [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f79b-109">Одной из важнейших задач является обеспечение безопасности подключения.</span><span class="sxs-lookup"><span data-stu-id="4f79b-109">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="4f79b-110">Дополнительные сведения см. в разделе [безопасность в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4f79b-110">For more information, see [Security in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f79b-111">Пример</span><span class="sxs-lookup"><span data-stu-id="4f79b-111">Example</span></span>  
 <span data-ttu-id="4f79b-112">В следующем примере класс <xref:System.Data.Linq.DataContext> используется для подключения к учебной базе данных "Northwind" и извлечения строк заказчиков, расположенных в Лондоне.</span><span class="sxs-lookup"><span data-stu-id="4f79b-112">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="4f79b-113">Каждая таблица базы данных представлена коллекцией `Table`, доступной с помощью метода <xref:System.Data.Linq.DataContext.GetTable%2A>. Для идентификации таблицы используется класс сущностей.</span><span class="sxs-lookup"><span data-stu-id="4f79b-113">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f79b-114">Пример</span><span class="sxs-lookup"><span data-stu-id="4f79b-114">Example</span></span>  
 <span data-ttu-id="4f79b-115">Рекомендация заключается в объявлении строго типизированного класса <xref:System.Data.Linq.DataContext> вместо использования базового класса <xref:System.Data.Linq.DataContext> и метода <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f79b-115">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="4f79b-116">Строго типизированный класс <xref:System.Data.Linq.DataContext> объявляет все коллекции `Table` в качестве членов контекста, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4f79b-116">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="4f79b-117">После этого создание запроса на получение клиентов из Лондона можно осуществить более простым способом:</span><span class="sxs-lookup"><span data-stu-id="4f79b-117">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="4f79b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4f79b-118">See also</span></span>

- [<span data-ttu-id="4f79b-119">Установка связи с базой данных</span><span class="sxs-lookup"><span data-stu-id="4f79b-119">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
