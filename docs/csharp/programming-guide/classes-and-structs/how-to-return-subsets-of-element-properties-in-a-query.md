---
title: "Практическое руководство. Возвращение наборов свойств элементов в запросе (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 99768c4b486dd6e8a25af22ab187c673c548ece9
ms.contentlocale: ru-ru
ms.lasthandoff: 06/15/2017

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
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 Обратите внимание, что анонимный тип использует имена исходных элементов для соответствующих свойств, если имена не заданы. Чтобы присваивать новые имена свойствам в анонимном типе, напишите инструкцию `select` следующим образом:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Если вы попробуете сделать это в предыдущем примере, также необходимо изменить инструкцию `Console.WriteLine`:  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, которое было создано в [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], и он будет включать ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
