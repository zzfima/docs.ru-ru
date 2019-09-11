---
title: Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 87bd7124d476ef39553db3ceaca206e44db8e5e9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854616"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="71818-102">Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции</span><span class="sxs-lookup"><span data-stu-id="71818-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="71818-103">Рассмотрим, как выполнить команду для концептуальной модели с использованием объекта <xref:System.Data.EntityClient.EntityCommand> и как получить результат с вложенной коллекцией при использовании <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="71818-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="71818-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="71818-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="71818-105">Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="71818-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="71818-106">Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.</span><span class="sxs-lookup"><span data-stu-id="71818-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="71818-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="71818-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="71818-108">Пример</span><span class="sxs-lookup"><span data-stu-id="71818-108">Example</span></span>  
 <span data-ttu-id="71818-109">*Вложенная коллекция* — это коллекция, которая находится внутри другой коллекции.</span><span class="sxs-lookup"><span data-stu-id="71818-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="71818-110">В следующем коде происходит получение коллекции `Contacts` и вложенных коллекций `SalesOrderHeaders`, которые связаны с каждым объектом `Contact`.</span><span class="sxs-lookup"><span data-stu-id="71818-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="71818-111">См. также</span><span class="sxs-lookup"><span data-stu-id="71818-111">See also</span></span>

- [<span data-ttu-id="71818-112">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="71818-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
