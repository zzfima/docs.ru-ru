---
title: "checked (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="checked-c-reference"></a>checked (Справочник по C#)
Ключевое слово `checked` используется для явного включения проверки переполнения при выполнении арифметических операций и преобразований с данными целого типа.  
  
 По умолчанию выражение, содержащее только константные значения, вызывает ошибку компилятора в том случае, если результат его вычисления выходит за допустимые пределы значений конечного типа. Если выражение содержит одно или несколько неконстантных значений, компилятор не выполняет проверку переполнения. Вычисление выражения, присвоенного переменной `i2` в приведенном ниже примере, не вызывает ошибку компилятора.  
  
 [!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]  
  
 По умолчанию эти неконстантные выражения также не проверяются на переполнение во время выполнения, и они не создают исключений переполнения. В предыдущем примере в качестве суммы двух положительных целых чисел выводится значение -2 147 483 639.  
  
 Проверку переполнения можно включить посредством параметров компилятора, настройки среды или использования ключевого слова `checked`. В следующих примерах демонстрируется использование выражения `checked` или блока `checked` для обнаружения переполнения, возникающего в результате предыдущего сложения во время выполнения. В обоих примерах создается исключение переполнения.  
  
 [!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]  
  
 Для запрета проверки переполнения можно использовать ключевое слово [unchecked](../../../csharp/language-reference/keywords/unchecked.md).  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется включение проверки переполнения во время выполнения посредством ключевого слова `checked`.  
  
 [!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)   
 [unchecked](../../../csharp/language-reference/keywords/unchecked.md)

