---
title: "Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6654b162fbdeb59ed2a135d7d8cf58c8b3406c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="32a44-102">Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="32a44-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="32a44-103">Используйте анонимный тип в выражении запроса, если выполняются оба следующих условия:</span><span class="sxs-lookup"><span data-stu-id="32a44-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
-   <span data-ttu-id="32a44-104">требуется возвращать только некоторые свойства каждого исходного элемента;</span><span class="sxs-lookup"><span data-stu-id="32a44-104">You want to return only some of the properties of each source element.</span></span>  
  
-   <span data-ttu-id="32a44-105">не требуется хранить результаты запроса за пределами области метода, в котором выполняется запрос.</span><span class="sxs-lookup"><span data-stu-id="32a44-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="32a44-106">Если требуется возвращать только одно свойство или поле из каждого исходного элемента, вы можете использовать оператор "точка" в предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="32a44-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="32a44-107">Например, чтобы вернуть только `ID` для каждого элемента `student`, напишите предложение `select` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="32a44-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="32a44-108">Пример</span><span class="sxs-lookup"><span data-stu-id="32a44-108">Example</span></span>  
 <span data-ttu-id="32a44-109">В следующем примере показано, как использовать анонимный тип для возвращения только конкретного набора свойств каждого исходного элемента, соответствующего указанному условию.</span><span class="sxs-lookup"><span data-stu-id="32a44-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 <span data-ttu-id="32a44-110">Обратите внимание, что анонимный тип использует имена исходных элементов для соответствующих свойств, если имена не заданы.</span><span class="sxs-lookup"><span data-stu-id="32a44-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="32a44-111">Чтобы присваивать новые имена свойствам в анонимном типе, напишите инструкцию `select` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="32a44-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="32a44-112">Если вы попробуете сделать это в предыдущем примере, также необходимо изменить инструкцию `Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="32a44-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32a44-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="32a44-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="32a44-114">Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, которое было создано в [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32a44-114">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="32a44-115">По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], и он будет включать ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq.</span><span class="sxs-lookup"><span data-stu-id="32a44-115">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it will have a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="32a44-116">Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.</span><span class="sxs-lookup"><span data-stu-id="32a44-116">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="32a44-117">См. также</span><span class="sxs-lookup"><span data-stu-id="32a44-117">See Also</span></span>  
 [<span data-ttu-id="32a44-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="32a44-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="32a44-119">Анонимные типы</span><span class="sxs-lookup"><span data-stu-id="32a44-119">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="32a44-120">Выражения запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="32a44-120">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
