---
title: "Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand"
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
ms.assetid: 4f5639bf-bb7f-4982-bb1d-c7caa4348888
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8c7131ce5bdbd76fc53e2746f7f630b7b47647a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-a-parameterized-stored-procedure-using-entitycommand"></a><span data-ttu-id="5a2e0-102">Практическое руководство. Выполнение параметризованной хранимой процедуры с использованием EntityCommand</span><span class="sxs-lookup"><span data-stu-id="5a2e0-102">How to: Execute a Parameterized Stored Procedure Using EntityCommand</span></span>
<span data-ttu-id="5a2e0-103">В данном разделе приведен пример выполнения параметризированной хранимой процедуры при помощи команды <xref:System.Data.EntityClient.EntityCommand>.</span><span class="sxs-lookup"><span data-stu-id="5a2e0-103">This topic shows how to execute a parameterized stored procedure by using the <xref:System.Data.EntityClient.EntityCommand> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="5a2e0-104">Выполнение кода в этом примере</span><span class="sxs-lookup"><span data-stu-id="5a2e0-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="5a2e0-105">Добавить [модели School](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a2e0-105">Add the [School Model](http://msdn.microsoft.com/en-us/859a9587-81ea-4a45-9bc0-f8d330e1adac) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="5a2e0-106">Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="5a2e0-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="5a2e0-107">На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="5a2e0-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  <span data-ttu-id="5a2e0-108">Импортируйте хранимую процедуру `GetStudentGrades` и укажите сущности `CourseGrade` в качестве возвращаемого типа.</span><span class="sxs-lookup"><span data-stu-id="5a2e0-108">Import the `GetStudentGrades` stored procedure and specify `CourseGrade` entities as a return type.</span></span> <span data-ttu-id="5a2e0-109">Сведения о том, как импортировать хранимую процедуру в разделе [как: Импорт хранимой процедуры](http://msdn.microsoft.com/en-us/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span><span class="sxs-lookup"><span data-stu-id="5a2e0-109">For information on how to import a stored procedure, see [How to: Import a Stored Procedure](http://msdn.microsoft.com/en-us/24e68bf4-bd6d-428d-bc35-92d7b8e3736d).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a2e0-110">Пример</span><span class="sxs-lookup"><span data-stu-id="5a2e0-110">Example</span></span>  
 <span data-ttu-id="5a2e0-111">Следующий код выполняет хранимую процедуру `GetStudentGrades`, где параметр `StudentId` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5a2e0-111">The following code executes the `GetStudentGrades` stored procedure where `StudentId` is a required parameter.</span></span> <span data-ttu-id="5a2e0-112">Затем результаты считываются объектом <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="5a2e0-112">The results are then read by an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#storedprocwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#StoredProcWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#storedprocwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="5a2e0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5a2e0-113">See Also</span></span>  
 [<span data-ttu-id="5a2e0-114">Поставщик EntityClient для Entity Framework</span><span class="sxs-lookup"><span data-stu-id="5a2e0-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
