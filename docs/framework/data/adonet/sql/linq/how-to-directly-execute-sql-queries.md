---
title: "Практическое руководство. Непосредственное выполнение запросов SQL"
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
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ccc47a1ea740c5106517f6f53620ddc8097c531
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="ad3db-102">Практическое руководство. Непосредственное выполнение запросов SQL</span><span class="sxs-lookup"><span data-stu-id="ad3db-102">How to: Directly Execute SQL Queries</span></span>
<span data-ttu-id="ad3db-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в параметризованные запросы SQL (в текстовой форме) и отправляет их на сервер SQL для обработки.</span><span class="sxs-lookup"><span data-stu-id="ad3db-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="ad3db-104">В SQL не может выполняться все разнообразие методов, локально доступных приложению.</span><span class="sxs-lookup"><span data-stu-id="ad3db-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="ad3db-105"> пытается преобразовать эти локальные методы в равноценные операторы и функции среды SQL.</span><span class="sxs-lookup"><span data-stu-id="ad3db-105"> tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="ad3db-106">Для большинства методов и операторов, основанных на встроенных типах [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], предусмотрены непосредственные преобразования в команды SQL.</span><span class="sxs-lookup"><span data-stu-id="ad3db-106">Most methods and operators on [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="ad3db-107">Некоторые методы и операторы можно создать из доступных функций,</span><span class="sxs-lookup"><span data-stu-id="ad3db-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="ad3db-108">а те, которые не могут быть преобразованы, вызывают исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad3db-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="ad3db-109">Дополнительные сведения см. в разделе [сопоставление типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="ad3db-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="ad3db-110">В тех случаях, когда запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] недостаточно для выполнения специализированной задачи, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> для выполнения запроса SQL и последующего преобразования результата запроса непосредственно в объекты.</span><span class="sxs-lookup"><span data-stu-id="ad3db-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3db-111">Пример</span><span class="sxs-lookup"><span data-stu-id="ad3db-111">Example</span></span>  
 <span data-ttu-id="ad3db-112">В следующем примере предполагается, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2).</span><span class="sxs-lookup"><span data-stu-id="ad3db-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="ad3db-113">Запрос возвращает последовательность объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="ad3db-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="ad3db-114">При условии, что имена столбцов в табличных результатах соответствуют свойствам столбцов класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты вне запроса SQL.</span><span class="sxs-lookup"><span data-stu-id="ad3db-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad3db-115">Пример</span><span class="sxs-lookup"><span data-stu-id="ad3db-115">Example</span></span>  
 <span data-ttu-id="ad3db-116">Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> также допускает использование параметров.</span><span class="sxs-lookup"><span data-stu-id="ad3db-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="ad3db-117">Для выполнения параметризованного запроса используется код, аналогичный представленному ниже.</span><span class="sxs-lookup"><span data-stu-id="ad3db-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="ad3db-118">Параметры записываются в тексте запроса с помощью той же нотации с фигурными скобками, которая используется в методах `Console.WriteLine()` и `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="ad3db-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="ad3db-119">На самом деле `String.Format()` вызван в строке запроса, вы предоставляете, заменив фигурные скобки параметры на созданные имена параметров, таких как @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="ad3db-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3db-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ad3db-120">See Also</span></span>  
 [<span data-ttu-id="ad3db-121">Общие сведения</span><span class="sxs-lookup"><span data-stu-id="ad3db-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="ad3db-122">Запросы к базе данных</span><span class="sxs-lookup"><span data-stu-id="ad3db-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
