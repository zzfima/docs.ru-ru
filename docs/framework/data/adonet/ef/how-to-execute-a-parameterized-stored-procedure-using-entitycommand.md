---
title: Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
ms.openlocfilehash: 433c04f673b402ae893507b1991f170119758b97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155276"
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="34910-102">Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="34910-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="34910-103">В данном разделе приведен пример выполнения параметризированной хранимой процедуры при помощи команды <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="34910-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="34910-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="34910-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="34910-105">Добавить [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34910-105">Add the [School Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="34910-106">Дополнительные сведения см. в разделе [Как Использовать мастер моделей EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34910-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="34910-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="34910-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="34910-108">Импортируйте хранимую процедуру `GetStudentGrades` и укажите сущности `CourseGrade` в качестве типа возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="34910-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="34910-109">Сведения о том, как импортировать хранимую процедуру, см. в разделе [как: Импортировать хранимую процедуру](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="34910-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896231(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34910-110">Пример</span><span class="sxs-lookup"><span data-stu-id="34910-110">Example</span></span>  
 <span data-ttu-id="34910-111">Следующий код выполняет хранимую процедуру `GetStudentGrades`, где параметр `StudentId` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="34910-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="34910-112">Затем результаты считываются объектом <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="34910-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="34910-113">См. также</span><span class="sxs-lookup"><span data-stu-id="34910-113">See also</span></span>

- [<span data-ttu-id="34910-114">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="34910-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
