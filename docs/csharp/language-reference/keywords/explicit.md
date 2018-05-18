---
title: explicit (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: c8a05aef3318eb34242ed1268ea26663592e4d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="explicit-c-reference"></a>explicit (Справочник по C#)
Ключевое слово `explicit` объявляет оператор преобразования определяемого пользователем типа, который должен быть вызван с помощью приведения. Например, этот оператор выполняет преобразование из класса Fahrenheit в класс Celsius:  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 Такой оператор преобразования можно вызвать следующим образом:  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 Оператор преобразования преобразует исходный тип в конечный. Исходный тип предоставляет оператор преобразования. В отличие от неявного преобразования, операторы явного преобразования должны вызываться с помощью приведения. Если операция преобразования может вызвать исключения или привести к потере данных, следует пометить ее как `explicit`. Это предотвращает выполнение компилятором скрытого вызова операции преобразования с возможно непредвиденными последствиями.  
  
 Пропуск приведения приводит к ошибке времени компиляции CS0266.  
  
 Дополнительные сведения см. в разделе [Использование операторов преобразования](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Пример  
 В следующем примере приводятся классы `Fahrenheit` и `Celsius`, каждый из которых предоставляет явный оператор преобразования в другой класс.  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере определяется структура `Digit`, представляющая одну десятичную цифру. Оператор определен для преобразования из `byte` в `Digit`, но поскольку не все байты могут быть преобразованы в `Digit`, выполняется явное преобразование.  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md)  
 [Практическое руководство. Реализация определенных пользователем преобразований между структурами](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [Связанные пользовательские явные преобразования в C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
