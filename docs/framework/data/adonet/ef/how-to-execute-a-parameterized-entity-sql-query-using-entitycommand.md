---
title: Практическое руководство. Выполнение SQL-запроса к параметрическому объекту с использованием EntityCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
ms.openlocfilehash: aa750ef088ee045c8d1045b2509d8fc4bde014ce
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854625"
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a><span data-ttu-id="4b852-102">Практическое руководство. Выполнение SQL-запроса к параметрическому объекту с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="4b852-102">How to: Execute a Parameterized Entity SQL Query Using EntityCommand</span></span>
<span data-ttu-id="4b852-103">В этом разделе показано, как выполнить [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос, имеющий параметры, <xref:System.Data.EntityClient.EntityCommand> с помощью объекта.</span><span class="sxs-lookup"><span data-stu-id="4b852-103">This topic shows how to execute an [!INCLUDE[esql](../../../../../includes/esql-md.md)] query that has parameters by using an <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="4b852-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="4b852-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="4b852-105">Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4b852-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="4b852-106">Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.</span><span class="sxs-lookup"><span data-stu-id="4b852-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="4b852-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="4b852-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="4b852-108">Пример</span><span class="sxs-lookup"><span data-stu-id="4b852-108">Example</span></span>  
 <span data-ttu-id="4b852-109">Следующий пример показывает, как создать строку запроса с двумя параметрами.</span><span class="sxs-lookup"><span data-stu-id="4b852-109">The following example shows how to construct a query string with two parameters.</span></span> <span data-ttu-id="4b852-110">Затем создается объект <xref:System.Data.EntityClient.EntityCommand>, добавляются два параметра в коллекцию <xref:System.Data.EntityClient.EntityParameter> этого объекта <xref:System.Data.EntityClient.EntityCommand> и совершается проход по элементам коллекции объектов `Contact`.</span><span class="sxs-lookup"><span data-stu-id="4b852-110">It then creates an <xref:System.Data.EntityClient.EntityCommand>, adds two parameters to the <xref:System.Data.EntityClient.EntityParameter> collection of that <xref:System.Data.EntityClient.EntityCommand>, and iterates through the collection of `Contact` items.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="4b852-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4b852-111">See also</span></span>

- <span data-ttu-id="4b852-112">[Практическое руководство. Выполнение параметризованного запроса](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4b852-112">[How to: Execute a Parameterized Query](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))</span></span>
- [<span data-ttu-id="4b852-113">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="4b852-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
