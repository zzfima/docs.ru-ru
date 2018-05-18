---
title: stackalloc (Справочник по C#)
ms.date: 04/12/2018
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 905873cf7f576ff35a9bc1c182ce7ebe17920288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="stackalloc-c-reference"></a>stackalloc (Справочник по C#)
Ключевое слово `stackalloc` используется в контексте небезопасного кода для выделения блока памяти стеку.

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a>Примечания

Это ключевое слово допустимо только в инициализаторах локальных переменных. Следующий код вызывает ошибки компилятора.

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

Начиная с версии C# 7.3 для массивов `stackalloc` можно использовать синтаксис инициализатора массива. Во всех следующих примерах объявляется массив с тремя элементами, имеющими целочисленные значения `1`, `2` и `3`:

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

Так как задаются типы указателей, `stackalloc` требует [небезопасного](unsafe.md) контекста. Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md). 

`stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.

## <a name="examples"></a>Примеры

Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи. Каждое из них представляет собой сумму двух предыдущих чисел. В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку. Адрес блока хранится в указателе `fib`. Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](fixed-statement.md)). Время существования блока памяти ограничивается временем существования метода, который его определяет. Освободить эту память прежде, чем метод выдаст результат, невозможно.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

В приведенном ниже примере массив целых чисел `stackalloc` инициализируется с использованием битовой маски, задающей один бит в каждом элементе. Таким образом в нем демонстрируется использование нового синтаксиса инициализатора, доступного начиная с версии C# 7.3.

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a>Безопасность

Небезопасный код менее безопасен, чем безопасные аналоги. В то же время при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера. Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.

## <a name="c-language-specification"></a>Спецификация языка C#
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
