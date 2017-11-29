---
title: "Операторы (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 166130ca7a63127d0bd1df8328dc08b4a8cd7845
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2017
---
# <a name="statements-c-programming-guide"></a>Операторы (Руководство по программированию в C#)
Действия программы выражаются в операторах. В общие действия включено объявление переменных, присвоение значений, вызов методов, проход по коллекциям и ветвление на один или другой блок кода, в зависимости от заданного условия. Порядок выполнения операторов в программе называется потоком управления или потоком выполнения. Поток управления может отличаться при каждом запуске программы, в зависимости от реакции программы на входные данные, которые она получает во время выполнения.  
  
 Оператор может состоять из одной строки кода, которая заканчивается точкой с запятой, или из ряда однострочных операторов в блоке. Блок оператора заключен в скобки {} и может содержать вложенные блоки. В следующем коде показаны два примера однострочных операторов и блок многострочного оператора:  
  
 [!code-csharp[csProgGuideStatements#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_1.cs)]  
  
## <a name="types-of-statements"></a>Типы операторов  
 В приведенной ниже таблице перечислены различные типы операторов в C# и связанные с ними ключевые слова со ссылками на разделы, в которых содержатся дополнительные сведения.  
  
|Категория|Ключевые слова / примечания C#|  
|--------------|---------------------------|  
|Операторы объявления|Оператор объявления представляет новую переменную или константу. Объявление переменной может при необходимости присвоить значение переменной. В объявлении константы необходимо назначение.<br /><br /> [!code-csharp[csProgGuideStatements#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_2.cs)]|  
|Операторы выражений|Операторы выражений, вычисляющие значение, должны сохранить его в переменной.<br /><br /> [!code-csharp[csProgGuideStatements#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_3.cs)]|  
|[Операторы выбора](../../../csharp/language-reference/keywords/selection-statements.md)|Операторы выбора позволяют ветвление на разные разделы кода, в зависимости от одного или нескольких заданных условий. Дополнительные сведения см. в следующих разделах:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|[Операторы итерации](../../../csharp/language-reference/keywords/iteration-statements.md)|Операторы итерации позволяют просмотр коллекций как массивов или многократное выполнение того же набора операторов до выполнения заданного условия. Дополнительные сведения см. в следующих разделах:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|[Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)|Операторы перехода осуществляют передачу управления другому разделу кода. Дополнительные сведения см. в следующих разделах:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|[Операторы обработки исключений](../../../csharp/language-reference/keywords/exception-handling-statements.md)|Операторы обработки исключений позволяют аккуратно восстановиться после исключительных условий, возникающих во время выполнения. Дополнительные сведения см. в следующих разделах:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Операторы checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Операторы checked и unchecked позволяют указать, позволено ли числовым операциям вызывать переполнение, когда результат сохраняется в переменной, которая слишком мала для хранения результирующего значения. Дополнительные сведения см. в разделах [checked](../../../csharp/language-reference/keywords/checked.md) и [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Оператор `await`|Если пометить метод с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md) , можно использовать в этом методе инструкцию [await](../../../csharp/language-reference/keywords/await.md) . Когда управление достигает выражения `await` в асинхронном методе, управление возвращается вызывающему объекту, и выполнение метода приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в методе.<br /><br /> Простой пример см. в подразделе "Асинхронные методы" раздела [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md). Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md).|  
|Оператор `yield return`|Итератор выполняет настраиваемую итерацию по коллекции, например по списку или массиву. Итератор использует оператор [yield return](../../../csharp/language-reference/keywords/yield.md) для возврата всех элементов по одному. При достижении оператора `yield return` текущее расположение в коде запоминается. При следующем вызове итератора выполнение возобновляется с этого места.<br /><br /> Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).|  
|Оператор `fixed`|Оператор fixed не позволяет сборщику мусора переносить перемещаемую переменную. Дополнительные сведения см. в разделе [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Оператор `lock`|Оператор lock позволяет ограничить одновременный доступ к блокам кода только до одного потока. Дополнительные сведения см. в разделе [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Операторы с метками|Оператор можно пометить и затем использовать ключевое слово [goto](../../../csharp/language-reference/keywords/goto.md) для перехода к оператору с меткой. (См. пример в следующей строке.)|  
|Пустой оператор|Пустой оператор состоит из точки с запятой. Он не выполняет никаких действий, и его можно использовать в местах, в которых оператор необходим, но нет необходимости в выполнении каких-либо действий. В следующих примерах показаны два способа использования пустого оператора:<br /><br /> [!code-csharp[csProgGuideStatements#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_4.cs)]|  
  
## <a name="embedded-statements"></a>Внедренные операторы  
 В некоторых операторах, включая [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md), всегда есть внедренный оператор, следующий за ними. Этот внедренный оператор может быть либо одним оператором, либо несколькими операторами, заключенными в скобки {} в блоке оператора. Даже однострочные внедренные операторы могут быть заключены в скобки {}, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_5.cs)]  
  
 Внедренный оператор, не заключенный в скобки {}, не может быть оператором объявления или оператором с меткой. Это показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_6.cs)]  
  
 Чтобы устранить ошибку, поместите внедренный оператор в блок:  
  
 [!code-csharp[csProgGuideStatements#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_7.cs)]  
  
## <a name="nested-statement-blocks"></a>Вложенные блоки операторов  
 Блоки операторов могут быть вложенными, как показано в следующем коде:  
  
 [!code-csharp[csProgGuideStatements#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_8.cs)]  
  
## <a name="unreachable-statements"></a>Недостижимые операторы  
 Если компилятор определяет, что поток управления ни при каких обстоятельствах не сможет достичь определенного оператора, то он выдаст предупреждение CS0162, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/statements_9.cs)]  
  
## <a name="related-sections"></a>Связанные разделы  
  
-   [Ключевые слова операторов](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
-   [Выражения](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
-   [Операторы](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
