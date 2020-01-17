---
title: Операторы. Руководство по программированию на C#
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: d50b50bb291d0d087015ea5bd075ae90ced66ff5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711939"
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
|Операторы выбора|Инструкции выбора позволяют ветвление на разные разделы кода, в зависимости от одного или нескольких заданных условий. Дополнительные сведения см. в следующих разделах: <ul><li>[if](../../language-reference/keywords/if-else.md)</li><li>[else](../../language-reference/keywords/if-else.md)</li><li>[switch](../../language-reference/keywords/switch.md)</li><li>[case](../../language-reference/keywords/switch.md)</li></ul>|
|Операторы итерации|Инструкции итерации позволяют просмотр коллекций как массивов или многократное выполнение того же набора инструкций до выполнения заданного условия. Дополнительные сведения см. в следующих разделах: <ul><li>[do](../../language-reference/keywords/do.md)</li><li>[for](../../language-reference/keywords/for.md)</li><li>[foreach](../../language-reference/keywords/foreach-in.md)</li><li>[in](../../language-reference/keywords/foreach-in.md)</li><li>[while](../../language-reference/keywords/while.md)</li></ul>|
|Операторы перехода|Инструкции перехода передают управление другому разделу кода. Дополнительные сведения см. в следующих разделах: <ul><li>[break](../../language-reference/keywords/break.md)</li><li>[continue](../../language-reference/keywords/continue.md)</li><li>[default](../../language-reference/keywords/switch.md)</li><li>[goto](../../language-reference/keywords/goto.md)</li><li>[return](../../language-reference/keywords/return.md)</li><li>[yield](../../language-reference/keywords/yield.md)</li></ul>|
|Операторы обработки исключений|Инструкции обработки исключений позволяют аккуратно выполнить восстановление после исключительных условий, возникающих во время выполнения. Дополнительные сведения см. в следующих разделах: <ul><li>[throw](../../language-reference/keywords/throw.md)</li><li>[try-catch](../../language-reference/keywords/try-catch.md)</li><li>[try-finally](../../language-reference/keywords/try-finally.md)</li><li>[try-catch-finally](../../language-reference/keywords/try-catch-finally.md)</li></ul>|
|[Инструкции checked и unchecked](../../language-reference/keywords/checked-and-unchecked.md)|Инструкции checked и unchecked позволяют указать, позволено ли числовым операциям вызывать переполнение, когда результат сохраняется в переменной, которая слишком мала для хранения результирующего значения. Дополнительные сведения см. в разделах [checked](../../language-reference/keywords/checked.md) и [unchecked](../../language-reference/keywords/unchecked.md).|
|Инструкция `await`|Если пометить метод с помощью модификатора [async](../../language-reference/keywords/async.md), можно использовать в этом методе инструкцию [await](../../language-reference/operators/await.md). Когда управление достигает выражения `await` в асинхронном методе, управление возвращается вызывающему объекту, и выполнение метода приостанавливается до завершения выполнения ожидающей задачи. После завершения задачи можно возобновить выполнение в методе.<br /><br /> Простой пример см. в подразделе "Асинхронные методы" раздела [Методы](../classes-and-structs/methods.md). Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](../concepts/async/index.md).|
|Инструкция `yield return`|Итератор выполняет настраиваемую итерацию по коллекции, например по списку или массиву. Итератор использует инструкцию [yield return](../../language-reference/keywords/yield.md) для возврата всех элементов по одному. При достижении инструкции `yield return` текущее расположение в коде запоминается. При следующем вызове итератора выполнение возобновляется с этого места.<br /><br /> Дополнительные сведения см. в разделе [Итераторы](../concepts/iterators.md).|
|Инструкция `fixed`|Инструкция fixed не позволяет сборщику мусора переносить перемещаемую переменную. Дополнительные сведения см. в разделе [fixed](../../language-reference/keywords/fixed-statement.md).|
|Инструкция `lock`|Инструкция lock позволяет ограничить одновременный доступ к блокам кода только до одного потока. Дополнительные сведения см. в разделе [lock](../../language-reference/keywords/lock-statement.md).|
|Инструкции с метками|Инструкцию можно пометить и затем использовать ключевое слово [goto](../../language-reference/keywords/goto.md) для перехода к инструкции с меткой. (См. пример в следующей строке.)|
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

В некоторых инструкциях, включая [do](../../language-reference/keywords/do.md), [while](../../language-reference/keywords/while.md), [for](../../language-reference/keywords/for.md) и [foreach](../../language-reference/keywords/foreach-in.md), всегда есть внедренная инструкция, следующая за ними. Эта внедренная инструкция может быть либо одной инструкцией, либо несколькими инструкциями, заключенными в скобки {} в блоке инструкций. Даже однострочные внедренные инструкции могут быть заключены в скобки {}, как показано в следующем примере:

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

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Операторы](~/_csharplang/spec/statements.md) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Ключевые слова операторов](../../language-reference/keywords/statement-keywords.md)  
- [Выражения](expressions.md)  
