---
title: Практическое руководство. Переход по отношениям с помощью оператора Navigate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: c8c23e00112859ffa9949d268c3263f73d3a714f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251435"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="83e0f-102">Практическое руководство. Переход по отношениям с помощью оператора Navigate</span><span class="sxs-lookup"><span data-stu-id="83e0f-102">How to: Navigate Relationships with the Navigate Operator</span></span>
<span data-ttu-id="83e0f-103">В этом подразделе показано выполнение команды для концептуальной модели с помощью объекта <xref:System.Data.EntityClient.EntityCommand>, а также получение результатов <xref:System.Data.Metadata.Edm.RefType> с помощью <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="83e0f-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="83e0f-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="83e0f-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="83e0f-105">Добавьте [модель AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) в проект и настройте проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83e0f-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="83e0f-106">Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.</span><span class="sxs-lookup"><span data-stu-id="83e0f-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="83e0f-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="83e0f-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="83e0f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="83e0f-108">Example</span></span>  
 <span data-ttu-id="83e0f-109">В следующем примере показано, как перемещаться по [!INCLUDE[esql](../../../../../includes/esql-md.md)] связям в с помощью оператора [navigate](./language-reference/navigate-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="83e0f-109">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](./language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="83e0f-110">`Navigate` Оператор принимает следующие параметры: экземпляр сущности, тип связи, окончание связи и начало связи между ними.</span><span class="sxs-lookup"><span data-stu-id="83e0f-110">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="83e0f-111">При необходимости можно передать `Navigate` оператору только экземпляр сущности и тип связи.</span><span class="sxs-lookup"><span data-stu-id="83e0f-111">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="83e0f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="83e0f-112">See also</span></span>

- [<span data-ttu-id="83e0f-113">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="83e0f-113">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="83e0f-114">Язык Entity SQL</span><span class="sxs-lookup"><span data-stu-id="83e0f-114">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
