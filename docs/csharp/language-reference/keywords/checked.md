---
title: checked (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: b05af798217a4f312bcf134d531135713efa8c66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="checked-c-reference"></a>checked (Справочник по C#)
Ключевое слово `checked` используется для явного включения проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.  
  
 По умолчанию выражение, содержащее только константные значения, вызывает ошибку компилятора в том случае, если результат его вычисления выходит за допустимые пределы значений конечного типа. Если выражение содержит одно или несколько неконстантных значений, компилятор не выполняет проверку переполнения. Вычисление выражения, присвоенного переменной `i2` в приведенном ниже примере, не вызывает ошибку компилятора.  
  
 [!code-csharp[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 По умолчанию эти неконстантные выражения также не проверяются на переполнение во время выполнения, и они не создают исключений переполнения. В предыдущем примере в качестве суммы двух положительных целых чисел выводится значение -2 147 483 639.  
  
 Проверку переполнения можно включить посредством параметров компилятора, настройки среды или использования ключевого слова `checked`. В следующих примерах демонстрируется использование выражения `checked` или блока `checked` для обнаружения переполнения, возникающего в результате предыдущего сложения во время выполнения. В обоих примерах создается исключение переполнения.  
  
 [!code-csharp[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 Для запрета проверки переполнения можно использовать ключевое слово [unchecked](../../../csharp/language-reference/keywords/unchecked.md).  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется включение проверки переполнения во время выполнения посредством ключевого слова `checked`.  
  
 [!code-csharp[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)
