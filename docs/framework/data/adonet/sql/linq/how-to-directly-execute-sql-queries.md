---
title: Как выполнить прямо выполнять запросы SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 1caf81df5998e5aaef4ad011a399d70aff43ca9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54634462"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="344c4-102">Как выполнить прямо выполнять запросы SQL</span><span class="sxs-lookup"><span data-stu-id="344c4-102">How to: Directly Execute SQL Queries</span></span>
<span data-ttu-id="344c4-103">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в параметризованные запросы SQL (в текстовой форме) и отправляет их на сервер SQL для обработки.</span><span class="sxs-lookup"><span data-stu-id="344c4-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="344c4-104">В SQL не может выполняться все разнообразие методов, локально доступных приложению.</span><span class="sxs-lookup"><span data-stu-id="344c4-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="344c4-105">пытается преобразовать эти локальные методы в равноценные операторы и функции среды SQL.</span><span class="sxs-lookup"><span data-stu-id="344c4-105">tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="344c4-106">Для большинства методов и операторов, основанных на встроенных типах [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], предусмотрены непосредственные преобразования в команды SQL.</span><span class="sxs-lookup"><span data-stu-id="344c4-106">Most methods and operators on [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="344c4-107">Некоторые методы и операторы можно создать из доступных функций,</span><span class="sxs-lookup"><span data-stu-id="344c4-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="344c4-108">а те, которые не могут быть преобразованы, вызывают исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="344c4-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="344c4-109">Дополнительные сведения см. в разделе [сопоставления типов SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="344c4-109">For more information, see [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="344c4-110">В тех случаях, когда запроса [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] недостаточно для выполнения специализированной задачи, можно использовать метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> для выполнения запроса SQL и последующего преобразования результата запроса непосредственно в объекты.</span><span class="sxs-lookup"><span data-stu-id="344c4-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="344c4-111">Пример</span><span class="sxs-lookup"><span data-stu-id="344c4-111">Example</span></span>  
 <span data-ttu-id="344c4-112">В следующем примере предполагается, что данные для класса `Customer` распределены по двум таблицам (customer1 и customer2).</span><span class="sxs-lookup"><span data-stu-id="344c4-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="344c4-113">Запрос возвращает последовательность объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="344c4-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="344c4-114">До тех пор, пока имена столбцов в табличных результатах соответствуют свойствам столбцов класса сущностей, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объекты вне запроса SQL.</span><span class="sxs-lookup"><span data-stu-id="344c4-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="344c4-115">Пример</span><span class="sxs-lookup"><span data-stu-id="344c4-115">Example</span></span>  
 <span data-ttu-id="344c4-116">Метод <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> также допускает использование параметров.</span><span class="sxs-lookup"><span data-stu-id="344c4-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="344c4-117">Для выполнения параметризованного запроса используется код, аналогичный представленному ниже.</span><span class="sxs-lookup"><span data-stu-id="344c4-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="344c4-118">Параметры записываются в тексте запроса с помощью той же нотации с фигурными скобками, которая используется в методах `Console.WriteLine()` и `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="344c4-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="344c4-119">На самом деле `String.Format()` фактически вызывается в строке запроса, вы предоставляете, заменив фигурные скобки параметры на созданные имена параметров, таких как @p0, @p1 ..., @p(n).</span><span class="sxs-lookup"><span data-stu-id="344c4-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344c4-120">См. также</span><span class="sxs-lookup"><span data-stu-id="344c4-120">See also</span></span>
- [<span data-ttu-id="344c4-121">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="344c4-121">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="344c4-122">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="344c4-122">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
