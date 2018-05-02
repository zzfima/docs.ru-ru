---
title: Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d77c04210c7e6e6084b6f6887378c930abcf1608
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Практическое руководство. Возвращение поднаборов свойств элементов в запросе (Руководство по программированию в C#)
Используйте анонимный тип в выражении запроса, если выполняются оба следующих условия:  
  
-   требуется возвращать только некоторые свойства каждого исходного элемента;  
  
-   не требуется хранить результаты запроса за пределами области метода, в котором выполняется запрос.  
  
 Если требуется возвращать только одно свойство или поле из каждого исходного элемента, вы можете использовать оператор "точка" в предложении `select`. Например, чтобы вернуть только `ID` для каждого элемента `student`, напишите предложение `select` следующим образом:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать анонимный тип для возвращения только конкретного набора свойств каждого исходного элемента, соответствующего указанному условию.  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Обратите внимание, что анонимный тип использует имена исходных элементов для соответствующих свойств, если имена не заданы. Чтобы присваивать новые имена свойствам в анонимном типе, напишите инструкцию `select` следующим образом:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Если вы попробуете сделать это в предыдущем примере, также необходимо изменить инструкцию `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, созданный в Visual Studio. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], и он будет включать ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
