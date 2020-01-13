---
title: Справочник по C#. Модификатор параметров out
ms.date: 03/26/2019
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: bc3814b91ed4327f4af1a4a1bfbda632b0393bb8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713274"
---
# <a name="out-parameter-modifier-c-reference"></a>Модификатор параметров out (справочник по C#)
Ключевое `out` инициирует передачу аргументов по ссылке. В результате этот формальный параметр становится псевдонимом для аргумента, который должен представлять собой переменную. Другими словами, любая операция в параметре осуществляется с аргументом. Оно схоже с ключевым словом [ref](ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать. Оно также похоже на ключевое слово [in](in-parameter-modifier.md) за исключением того, что `in` не позволяет вызываемому методу изменять значение аргумента. Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`. Пример:  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE] 
> Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным. Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](out-generic-modifier.md).
  
Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода. Но перед передачей управления из вызванного метода он должен присвоить значение.  
  
Ключевые слова `in`, `ref` и `out` не считаются частью сигнатуры метода для разрешения перегрузки. Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`. Следующий код, например, компилироваться не будет.  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Перегрузка допустима, если один метод принимает аргумент `ref`, `in` или `out`, а другой не использует ни один из этих модификаторов, как показано ниже.  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

Компилятор выбирает наиболее подходящую перегрузку, сравнивая модификаторы параметров в месте вызова с модификаторами параметров в вызове метода.
 
Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.
  
Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.  
  
- Асинхронные методы, которые определяются с помощью модификатора [async](./async.md).  
  
- Методы итератора, которые включают оператор [yield return](./yield.md) или `yield break`.  

## <a name="declaring-out-parameters"></a>Объявление параметров `out`   

Объявление метода с аргументами `out` — стандартное решение для возвращения нескольких значений. Начиная с версии C# 7.0, вы можете использовать [кортежи](../../tuples.md) для таких сценариев. В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода. Обратите внимание, что третьему аргумент присвоено значение null. Это позволяет методам возвращать значения по желанию.  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a>Вызов метода с аргументом `out`

В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`. В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

Начиная с C# версии 7.0 переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно. Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода. Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  
   
В предыдущем примере переменная `number` строго типизирована как `int`. Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  
   
## <a name="c-language-specification"></a>Спецификация языка C#  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [Параметры методов](./method-parameters.md)
