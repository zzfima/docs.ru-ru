---
title: Руководство по программированию на C#. Упаковка-преобразование и распаковка-преобразование
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 62df08bf4ae3580e9b8d5b3aab0697d396674ca1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745413"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a>Упаковка-преобразование и распаковка-преобразование (Руководство по программированию на C#)

Упаковка представляет собой процесс преобразования [типа значения](../../language-reference/builtin-types/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения. Когда тип значения упаковывается общеязыковой средой выполнения (CLR), он инкапсулирует значение внутри экземпляра <xref:System.Object?displayProperty=nameWithType> и сохраняет его в управляемой куче. Операция распаковки извлекает тип значения из объекта. Упаковка является неявной; распаковка является явной. Понятия упаковки и распаковки лежат в основе единой системы типов C#, в которой значение любого типа можно рассматривать как объект.

В следующем примере выполнена операция `i`упаковки *целочисленной переменной*, которая присвоена объекту `o`.

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

Затем можно выполнить операцию распаковки объекта `o`и присвоить его целочисленной переменной `i`:

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

Следующий пример иллюстрирует использование упаковки в C#.

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a>Производительность

По сравнению с простыми операциями присваивания операции упаковки и распаковки являются весьма затратными процессами с точки зрения вычислений. При выполнении упаковки типа значения необходимо создать и разместить новый объект. Объем вычислений при выполнении операции распаковки, хотя и в меньшей степени, но тоже весьма значителен. Дополнительные сведения см. в разделе [Производительность](../../../framework/performance/performance-tips.md).

## <a name="boxing"></a>Упаковка

Упаковка используется для хранения типов значений в куче со сбором мусора. Упаковка представляет собой неявное преобразование [типа значения](../../language-reference/builtin-types/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения. При упаковке типа значения в куче выделяется экземпляр объекта и выполняется копирование значения в этот новый объект.

Рассмотрим следующее объявление переменной типа значения.

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

Следующий оператор неявно применяет операцию упаковки к переменной `i`.

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

Результат этого оператора создает ссылку на объект `o` в стеке, которая ссылается на значение типа `int` в куче. Это значение является копией значения типа значения, присвоенного переменной `i`. Разница между этими двумя переменными, `i` и `o`, показана на рисунке упаковки-преобразования ниже:

![Рисунок, иллюстрирующий разницу между переменными "i" и "o".](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

Можно также выполнять упаковку явным образом, как в следующем примере, однако явная упаковка не является обязательной.

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a>Описание

В этом примере целочисленная переменная `i` преобразуется в объект `o` при помощи упаковки. Затем значение, хранимое переменной `i`, меняется с `123` на `456`. В примере показано, что исходный тип значения и упакованный объект используют отдельные ячейки памяти, а значит могут хранить разные значения.

## <a name="example"></a>Пример

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a>Распаковка

Распаковка является явным преобразованием из типа `object` в [тип значения](../../language-reference/builtin-types/value-types.md) или из типа интерфейса в тип значения, реализующего этот интерфейс. Операция распаковки состоит из следующих действий:

- проверка экземпляра объекта на то, что он является упакованным значением заданного типа значения;

- копирование значения из экземпляра в переменную типа значения.

В следующем коде показаны операции по упаковке и распаковке.

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

На рисунке ниже представлен результат выполнения этого кода.

![Рисунок, иллюстрирующий распаковку-преобразование.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

Для успешной распаковки типов значений во время выполнения необходимо, чтобы экземпляр, который распаковывается, был ссылкой на объект, предварительно созданный с помощью упаковки экземпляра этого типа значения. Попытка распаковать `null` создает исключение <xref:System.NullReferenceException>. Попытка распаковать ссылку на несовместимый тип значения создает исключение <xref:System.InvalidCastException>.

## <a name="example"></a>Пример

В следующем примере показан случай недопустимой распаковки, в результате чего создается исключение `InvalidCastException`. В случае использования `try` и `catch` при возникновении ошибки выводится сообщение.

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

При выполнении этой программы выводится следующий результат:

`Specified cast is not valid. Error: Incorrect unboxing.`

При изменении оператора:

```csharp
int j = (short) o;
```

на:

```csharp
int j = (int) o;
```

будет выполнено преобразование со следующим результатом:

`Unboxing OK.`

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Ссылочные типы](../../language-reference/keywords/reference-types.md)
- [Типы значений](../../language-reference/builtin-types/value-types.md)
