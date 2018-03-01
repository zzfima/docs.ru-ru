---
title: "Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 89c3e335-3f5b-4e24-8c5a-b8036561fe8a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 557e72342901fab8bbe66e9cc3405cb4b2d9c1e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-command-line-arguments-using-foreach-c-programming-guide"></a>Практическое руководство. Доступ к аргументам командной строки с помощью оператора foreach (Руководство по программированию на C#)
Другим методом итерации всех элементов массива является использование оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md), как показано в приведенном ниже примере. Оператор `foreach` можно использовать для итерации всех элементов массива, класса коллекции .NET Framework либо любого класса или структуры, реализующих интерфейс <xref:System.Collections.IEnumerable>.  
  
> [!NOTE]
>  При выполнении приложения в Visual Studio аргументы командной строки можно указать на [странице "Отладка" в конструкторе проектов](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Пример  
 В этом примере показано, как напечатать аргументы командной строки с помощью оператора `foreach`.  
  
 [!code-csharp[csProgGuideMain#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_1.cs)]  
  
 [!code-csharp[csProgGuideMain#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-access-command-line-arguments-using-foreach_2.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Array>  
 <xref:System.Collections>  
 [Сборка из командной строки с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)  
 [Main() и аргументы командной строки](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Практическое руководство. Отображение аргументов командной строки](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Значения, возвращаемые методом main()](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
