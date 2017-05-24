---
title: "yield (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: 46
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 22ef950c85b5d19141ea346a9e02d58003f45232
ms.contentlocale: ru-ru
ms.lasthandoff: 03/24/2017

---
# <a name="yield-c-reference"></a>yield (справочник по C#)
Использование в операторе ключевого слова `yield` означает, что метод, оператор или метод доступа `get`, в котором присутствует это ключевое слово, является итератором. Использование `yield` для определения итератора исключает необходимость применения явного дополнительного класса (в котором содержится состояние перечисления; в качестве примера см. <xref:System.Collections.Generic.IEnumerator%601>) при реализации шаблонов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> для пользовательского типа коллекции.  
  
 В следующем примере показаны две формы оператора `yield`.  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор `yield return` используется для возврата каждого элемента по одному.  
  
 Метод итератора используется путем применения оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md) или запроса LINQ. Каждая итерация цикла `foreach` вызывает метод итератора. При достижении в методе итератора оператора `yield return` возвращается `expression` и сохраняется текущее расположение в коде. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Для завершения итерации можно использовать оператор `yield break`.  
  
 Дополнительные сведения об итераторах см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="iterator-methods-and-get-accessors"></a>Методы итератора и методы доступа get  
 Объявление итератора должно соответствовать следующим требованиям.  
  
-   Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Объявление не должно содержать параметры [ref](../../../csharp/language-reference/keywords/ref.md) и [out](../../../csharp/language-reference/keywords/out.md).  
  
 Тип `yield` итератора, который возвращает <xref:System.Collections.IEnumerable> или <xref:System.Collections.IEnumerator>, — `object`.  Если итератор возвращает <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.Generic.IEnumerator%601>, необходимо выполнить неявное преобразование из типа выражения в операторе `yield return` в параметр универсального типа.  
  
 Ниже указаны методы, в которых операторы `yield return` и `yield break` использовать нельзя.  
  
-   Анонимные методы. Дополнительные сведения см. в разделе [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
-   Методы, содержащие небезопасные блоки. Дополнительные сведения см. в разделе [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exception-handling"></a>Обработка исключений  
 Оператор `yield return` нельзя размещать в блоке try-catch. Оператор `yield return` можно размещать в блоке try оператора try-finally.  
  
 Оператор `yield break` можно размещать в блоке try или catch, но не в блоке finally.  
  
 Если тело оператора `foreach` (вне метода итератора) вызывает исключение, выполняется блок `finally` в методе итератора.  
  
## <a name="technical-implementation"></a>Техническая реализация  
 В следующем коде возвращается объект `IEnumerable<string>` из метода итератора и затем выполняется перебор его элементов.  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 При вызове `MyIteratorMethod` тело метода не выполняется. Вместо этого вызов возвращает `IEnumerable<string>` в переменную `elements`.  
  
 В итерации цикла `foreach` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`. Этот вызов выполняет тело `MyIteratorMethod` до достижения следующего оператора `yield return`. Выражение, возвращаемое оператором `yield return`, определяет не только значение переменной `element` для использования телом цикла, но и свойство <xref:System.Collections.Generic.IEnumerator%601.Current%2A> элементов, представляющее собой `IEnumerable<string>`.  
  
 В каждой последующей итерации цикла `foreach` выполнение тела итератора продолжается с места остановки и при достижении оператора `yield return` оно снова останавливается. Цикл `foreach` завершается при достижении конца метода итератора или оператора `yield break`.  
  
## <a name="example"></a>Пример  
 В следующем примере имеется оператор `yield return`, расположенный в цикле `for`. Каждая итерация тела оператора `foreach` в `Process` создает вызов функции итератора `Power`. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `yield return`, которое осуществляется во время следующей итерации цикла `for`.  
  
 Тип возвращаемого значения метода итератора — <xref:System.Collections.IEnumerable> (тип интерфейса итератора). При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.  
  
 [!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется метод доступа `get`, представляющий собой итератор. В этом примере каждый оператор `yield return` возвращает экземпляр пользовательского класса.  
  
 [!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
