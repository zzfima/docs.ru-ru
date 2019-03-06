---
title: Как выполнить Руководство по программированию на C#. Возвращение подмножества свойств элементов в запросе
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 80f13250576957b252d6d83bfbcf70346b49b5a7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980741"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Возвращение подмножества свойств элементов в запросе
Используйте анонимный тип в выражении запроса, если выполняются оба следующих условия:  
  
-   требуется возвращать только некоторые свойства каждого исходного элемента;  
  
-   не требуется хранить результаты запроса за пределами области метода, в котором выполняется запрос.  
  
 Если требуется возвращать только одно свойство или поле из каждого исходного элемента, вы можете использовать оператор "точка" в предложении `select`. Например, чтобы вернуть только `ID` для каждого элемента `student`, напишите предложение `select` следующим образом:  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать анонимный тип для возвращения только конкретного набора свойств каждого исходного элемента, соответствующего указанному условию.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Обратите внимание, что анонимный тип использует имена исходных элементов для соответствующих свойств, если имена не заданы. Чтобы присваивать новые имена свойствам в анонимном типе, напишите инструкцию `select` следующим образом:  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Если вы попробуете сделать это в предыдущем примере, также необходимо изменить инструкцию `Console.WriteLine`:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, созданный в Visual Studio. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], и он будет включать ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
- [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)
