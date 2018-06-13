---
title: Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 2f62488af6c1226352efc6f4031635d4ff01d15b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761782"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="38b03-102">Практическое руководство. Выполнение запроса, возвращающего вложенные коллекции</span><span class="sxs-lookup"><span data-stu-id="38b03-102">How to: Execute a Query that Returns Nested Collections</span></span>
<span data-ttu-id="38b03-103">Рассмотрим, как выполнить команду для концептуальной модели с использованием объекта <xref:System.Data.EntityClient.EntityCommand> и как получить результат с вложенной коллекцией при использовании <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="38b03-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="38b03-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="38b03-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="38b03-105">Добавить [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38b03-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="38b03-106">Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="38b03-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="38b03-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="38b03-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="38b03-108">Пример</span><span class="sxs-lookup"><span data-stu-id="38b03-108">Example</span></span>  
 <span data-ttu-id="38b03-109">Объект *вложенные коллекции* — коллекция, которая находится внутри другой коллекции.</span><span class="sxs-lookup"><span data-stu-id="38b03-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="38b03-110">В следующем коде происходит получение коллекции `Contacts` и вложенных коллекций `SalesOrderHeaders`, которые связаны с каждым объектом `Contact`.</span><span class="sxs-lookup"><span data-stu-id="38b03-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="38b03-111">См. также</span><span class="sxs-lookup"><span data-stu-id="38b03-111">See Also</span></span>  
 [<span data-ttu-id="38b03-112">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="38b03-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
