---
title: Операторы. Руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: 78d40aa2069e56357f55f39c3b7479ee46d0342c
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422830"
---
# <a name="statements-c-programming-guide"></a>Инструкции (Руководство по программированию на C#)
Действия программы выражаются в инструкциях. В общие действия включено объявление переменных, присвоение значений, вызов методов, проход по коллекциям и ветвление на один или другой блок кода, в зависимости от заданного условия. Порядок выполнения инструкций в программе называется потоком управления или потоком выполнения. Поток управления может отличаться при каждом запуске программы, в зависимости от реакции программы на входные данные, которые она получает во время выполнения.  
  
 Инструкция может состоять из одной строки кода, которая заканчивается точкой с запятой, или из ряда однострочных инструкций в блоке. Блок инструкций заключен в скобки {} и может содержать вложенные блоки. В следующем коде показаны два примера однострочных инструкций и блок многострочных инструкций:  
  
 [!code-csharp[csProgGuideStatements#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#1)]  
  
## <a name="types-of-statements"></a>Типы инструкций  
 В приведенной ниже таблице перечислены различные типы инструкций в C# и связанные с ними ключевые слова со ссылками на разделы, в которых содержатся дополнительные сведения.  
  
|Категория|Ключевые слова / примечания C#|  
|--------------|---------------------------|  
|[Инструкции объявления](#declaration-statements)|Инструкция объявления представляет новую переменную или константу. Объявление переменной может при необходимости присвоить значение переменной. В объявлении константы необходимо назначение.|  
|[Инструкции выражений](expressions.md)|Инструкции выражений, вычисляющие значение, должны сохранить его в переменной. Дополнительные сведения см. в разделе [Инструкции выражений](#expression-statements).|  
|Операторы выбора|Инструкции выбора позволяют ветвление на разные разделы кода, в зависимости от одного или нескольких заданных условий. Дополнительные сведения см. в следующих разделах:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|Операторы итерации|Инструкции итерации позволяют просмотр коллекций как массивов или многократное выполнение того же набора инструкций до выполнения заданного условия. Дополнительные сведения см. в следующих разделах:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|Операторы перехода|Инструкции перехода передают управление другому разделу кода. Дополнительные сведения см. в следующих разделах:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|Операторы обработки исключений|Инструкции обработки исключений позволяют аккуратно выполнить восстановление после исключительных условий, возникающих во время выполнения. Дополнительные сведения см. в следующих разделах:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Инструкции checked и unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Инструкции checked и unchecked позволяют указать, позволено ли числовым операциям вызывать переполнение, когда результат сохраняется в переменной, которая слишком мала для хранения результирующего значения. Дополнительные сведения см. в разделах [checked](../../../csharp/language-reference/keywords/checked.md) и [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Инструкция `await`|Если пометить метод с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md), можно использовать в этом методе инструкцию [await](../../../csharp/language-reference/keywords/await.md). Когда управление достигает выражения `await` в асинхронном методе, управление возвращается вызывающему объекту, и выполнение метода приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в методе.<br /><br /> Простой пример см. в подразделе "Асинхронные методы" раздела [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md). Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../../../csharp/programming-guide/concepts/async/index.md).|  
|Инструкция `yield return`|Итератор выполняет настраиваемую итерацию по коллекции, например по списку или массиву. Итератор использует инструкцию [yield return](../../../csharp/language-reference/keywords/yield.md) для возврата всех элементов по одному. При достижении инструкции `yield return` текущее расположение в коде запоминается. При следующем вызове итератора выполнение возобновляется с этого места.<br /><br /> Дополнительные сведения см. в разделе [Итераторы](../../../csharp/programming-guide/concepts/iterators.md).|  
|Инструкция `fixed`|Инструкция fixed не позволяет сборщику мусора переносить перемещаемую переменную. Дополнительные сведения см. в разделе [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Инструкция `lock`|Инструкция lock позволяет ограничить одновременный доступ к блокам кода только до одного потока. Дополнительные сведения см. в разделе [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Инструкции с метками|Инструкцию можно пометить и затем использовать ключевое слово [goto](../../../csharp/language-reference/keywords/goto.md) для перехода к инструкции с меткой. (См. пример в следующей строке.)|  
|[Пустая инструкция](#the-empty-statement)|Пустая инструкция состоит из точки с запятой. Она ничего не делает, и ее можно использовать там, где инструкция необходима, но не нужно выполнять никаких действий.|  
  
## <a name="declaration-statements"></a>Инструкции объявления

В следующем коде приведены примеры объявления переменных с начальным значением и без него, а также пример объявления константы с необходимой инициализацией.

 [!code-csharp[csProgGuideStatements#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#23)]

## <a name="expression-statements"></a>Инструкции выражений

В следующем коде показаны примеры инструкций выражений, включая присваивание, создание объекта с помощью присваивания и вызов метода.

 [!code-csharp[csProgGuideStatements#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#24)]

## <a name="the-empty-statement"></a>Пустая инструкция

В следующих примерах показаны два способа использования пустой инструкции:

 [!code-csharp[csProgGuideStatements#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#25)]

## <a name="embedded-statements"></a>Внедренные инструкции

 В некоторых инструкциях, включая [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) и [foreach](../../../csharp/language-reference/keywords/foreach-in.md), всегда есть внедренная инструкция, следующая за ними. Эта внедренная инструкция может быть либо одной инструкцией, либо несколькими инструкциями, заключенными в скобки {} в блоке инструкций. Даже однострочные внедренные инструкции могут быть заключены в скобки {}, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#26)]  
  
 Внедренная инструкция, не заключенная в скобки {}, не может быть инструкцией объявления или инструкцией с меткой. Это показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#27)]  
  
 Чтобы устранить ошибку, поместите внедренную инструкцию в блок:  
  
 [!code-csharp[csProgGuideStatements#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#28)]  
  
## <a name="nested-statement-blocks"></a>Вложенные блоки инструкций  
 Блоки инструкций могут быть вложенными, как показано в следующем коде:  
  
 [!code-csharp[csProgGuideStatements#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#29)]  
  
## <a name="unreachable-statements"></a>Недостижимые инструкции  
 Если компилятор определяет, что поток управления ни при каких обстоятельствах не сможет достичь определенной инструкции, то он выдаст предупреждение CS0162, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideStatements#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#22)]  
  
## <a name="related-sections"></a>Связанные разделы  
  
- [Ключевые слова инструкций](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
- [Выражения](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
- [Инструкции](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
