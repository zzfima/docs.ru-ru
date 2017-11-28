---
title: "Модификатор параметров out (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 68ef554f95fe71f925cfa22cc49758cec3da237e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="out-parameter-modifier-c-reference"></a>Модификатор параметров out (справочник по C#)
Ключевое `out` инициирует передачу аргументов по ссылке. Оно схоже с ключевым словом [ref](../../../csharp/language-reference/keywords/ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать. Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`. Пример:  
  
 [!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]  

> [!NOTE] 
> Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным. Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](../../../csharp/language-reference/keywords/out-generic-modifier.md).
  
 Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода. Но перед передачей управления из вызванного метода он должен присвоить значение.  
  
 Несмотря на то, что ключевые слова `ref` и `out` вызвать другое поведение среды выполнения, они не считаются частью подписи метода во время компиляции. Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref`, а другой — аргумент `out`. Следующий код, например, компилироваться не будет.  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Перегрузка допустима, если один метод принимает аргумент `ref` или `out`, а другой не использует ни одного из них, как показано далее.  
  
 [!code-csharp[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]  
  
 Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.  
  
 Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.  
  
-   Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).  
  
-   Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.  

## <a name="declaring-out-arguments"></a>Объявление аргументов `out`   

 Объявление метода с аргументами `out` полезно в случае, если требуется, чтобы метод возвращал несколько значений. В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода. Обратите внимание, что третьему аргумент присвоено значение null. Это позволяет методам возвращать значения по желанию.  
  
 [!code-csharp[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]  

 [Шаблон Try](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) предполагает возврат значения типа `bool`, указывающего на успешность выполнения операции, и значения, полученного в результате операции, в аргументе `out`. Этот шаблон используется несколькими методами анализа, например методом [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)).
   
## <a name="calling-a-method-with-an-out-argument"></a>Вызов метода с аргументом `out`

В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`. В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.

 [!code-csharp[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]  

Начиная с версии 7 языка C# переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно. Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода. Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).

 [!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]  
   
В предыдущем примере переменная `number` строго типизирована как `int`. Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.

 [!code-csharp[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]  
   
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)
