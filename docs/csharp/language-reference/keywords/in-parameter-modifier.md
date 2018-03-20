---
title: "Модификатор параметров in (справочник по C#)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 035aac3e6b902f607e533b709713eb1d07c9774a
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="in-parameter-modifier-c-reference"></a>Модификатор параметров in (справочник по C#)

Ключевое `in` инициирует передачу аргументов по ссылке. Оно похоже на ключевые слова [ref](ref.md) или [out](out-parameter-modifier.md) за исключением того, что аргументы `in` не могут быть изменены вызываемым методом, тогда как аргументы `ref` могут быть изменены, аргументы `out` должны быть изменены вызывающим объектом, и такие изменения можно наблюдать в контексте вызова.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

Предыдущий пример показывает, что модификатор `in` не требуется в месте вызова. Он нужен только в объявлении метода.

> [!NOTE] 
> Ключевое слово `in` также можно использовать с параметром универсального типа для указания на то, что тип параметра является контравариантным, в рамках оператора `foreach` или предложения `join` в запросе LINQ. Дополнительные сведения об использовании ключевого слова `in` в таких контекстах см. в разделе [in](in.md), где приведены все соответствующие ссылки.
  
 Переменные, передаваемые в качестве аргументов `in`, требуется инициализировать перед передачей в вызов метода. Но вызванный метод не может присвоить значение или изменить аргумент.  
  
 Хотя ключевые слова `in`, `ref` и `out` вызывают разное поведение во время выполнения, они не считаются частью сигнатуры метода во время компиляции. Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`. Следующий код, например, компилироваться не будет.  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Перегрузка, основанная на наличии `in`, допустима, но приводит к возникновению предупреждения компилятора.  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

Свойства или константы можно передавать в качестве параметров `in`, так как вызывающий метод не может изменять их значения.
  
Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.  
  
- Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
- Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  

Аргументы `in` обычно объявляется, чтобы предотвратить операции копирования, необходимые для передачи аргументов по значению. Это особенно удобно, когда аргументы являются структурами и массивами структур.

## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)
