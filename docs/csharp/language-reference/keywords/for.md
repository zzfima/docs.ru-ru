---
title: "for (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f2f32dd4bde376dd241cf168a4f034ba8f6e9b50
ms.lasthandoff: 03/13/2017

---
# <a name="for-c-reference"></a>for (Справочник по C#)
Используя цикл `for`, можно раз за разом выполнять оператор или блок операторов, пока определенное выражение не примет значение `false`. Этот тип цикла удобен для перебора массивов и для других сфер применения, в которых заранее известно количество итераций цикла.  
  
## <a name="example"></a>Пример  
 В следующем примере значение `i` записывается в консоль и увеличивается на единицу при каждой итерации цикла.  
  
 [!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]  
  
 Оператор `for` в предыдущем примере выполняет следующие действия.  
  
1.  Во-первых, устанавливается начальное значение переменной `i`. Это происходит только один раз, независимо от числа повторений цикла. Можно представить эту инициализацию происходящей вне циклического процесса.  
  
2.  Для вычисления условия (`i <= 5`) значение `i` сравнивается с 5.  
  
    -   Если значение `i` меньше или равно 5, условие вычисляется как `true` и выполняются следующие действия.  
  
        1.  Оператор `Console.WriteLine` в теле цикла отображает значение `i`.  
  
        2.  Значение `i` увеличивается на единицу.  
  
        3.  Цикл возвращается к началу выполнения шага 2, чтобы повторно вычислить условие.  
  
    -   Если значение `i` больше 5, условие вычисляется как `false` и выполняется выход из цикла.  
  
 Обратите внимание, что, если начальное значение `i` больше 5, тело цикла вообще не запускается.  
  
 Каждый оператор `for` определяет инициализатор, условие и разделы итератора. В этих разделах обычно задается количество итераций цикла.  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 Разделы служат для следующих целей.  
  
-   Раздел инициализатора задает начальное условие. Операторы в этом разделе выполняются только один раз, перед входом в цикл. Раздел может содержать только один из двух параметров.  
  
    -   Объявление и инициализацию локальной переменной цикла (как в первом примере: `int i = 1`). Переменная является локальной для цикла: к ней нельзя получить доступ из-за его пределов.  
  
    -   Нуль или более выражений операторов из следующего списка, разделенные запятыми:  
  
        -   оператор [присваивания](../../../csharp/language-reference/operators/assignment-operator.md)  
  
        -   вызов метода  
  
        -   префиксное или постфиксное выражение [приращения](../../../csharp/language-reference/operators/increment-operator.md), такое как `++i` или `i++`  
  
        -   префиксное или постфиксное выражение [декремента](../../../csharp/language-reference/operators/decrement-operator.md), такое как `--i` или `i--`  
  
        -   создание объекта с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md)  
  
        -   выражение [await](../../../csharp/language-reference/keywords/await.md)  
  
-   В разделе условия содержится логическое выражение, которое вычисляется для определения необходимости выхода цикла или его повторного выполнения.  
  
-   Раздел итератора определяет, что происходит после каждой итерации тела цикла. Раздел итератора, содержащий ноль или более следующих выражений оператора, разделенных запятыми.  
  
    -   оператор [присваивания](../../../csharp/language-reference/operators/assignment-operator.md)  
  
    -   вызов метода  
  
    -   префиксное или постфиксное выражение [приращения](../../../csharp/language-reference/operators/increment-operator.md), такое как `++i` или `i++`  
  
    -   префиксное или постфиксное выражение [декремента](../../../csharp/language-reference/operators/decrement-operator.md), такое как `--i` или `i--`  
  
    -   создание объекта с помощью оператора [new](../../../csharp/language-reference/keywords/new-operator.md)  
  
    -   выражение [await](../../../csharp/language-reference/keywords/await.md)  
  
-   Тело цикла состоит из оператора, пустого оператора или блока операторов, которые вы создаете, заключив ноль или более операторов в фигурные скобки.  
  
     Вы можете прервать цикл `for` с помощью ключевого слова [break](../../../csharp/language-reference/keywords/break.md) или перейти к следующей итерации с помощью ключевого слова [continue](../../../csharp/language-reference/keywords/continue.md). Также можно выйти из любого цикла с помощью операторов [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md).  
  
 В первом примере в этом разделе показан наиболее типичный тип цикла `for`, который выполняет следующие действия для разделов.  
  
-   Инициализатор объявляет и инициализирует локальную переменную цикла `i`, которая хранит количество итераций цикла.  
  
-   Условие проверяет значение переменной цикла, сравнивая его с известным окончательным значением 5.  
  
-   Раздел итератора использует постфиксный оператор приращения, `i++`, для регистрации каждой итерации цикла.  
  
 В следующем примере показаны несколько менее распространенные варианты: присваивание значения внешней переменной цикла в разделе инициализатора, вызов метода `Console.WriteLine` в разделах инициализатора и итератора и изменение значения двух переменных в разделе итератора.  
  
 [!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]  
  
 Все выражения, определяющие оператор `for`, являются необязательными. Например, следующая инструкция создает бесконечный цикл.  
  
 [!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Оператор for (C++)](https://docs.microsoft.com/cpp/cpp/for-statement-cpp)   
 [Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)
