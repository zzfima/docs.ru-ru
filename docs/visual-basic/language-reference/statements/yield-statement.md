---
title: "Оператор Yield (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Yield"
helpviewer_keywords: 
  - "итераторы, оператор Yield [Visual Basic]"
  - "итераторы [Visual Basic]"
  - "Yield - оператор [Visual Basic]"
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Оператор Yield (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Отправляет следующий элемент коллекции в инструкцию `For Each...Next`.  
  
## Синтаксис  
  
```  
Yield expression  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Термин|Определение|  
|`expression`|Обязательное.  Выражение, которое неявно преобразовать в значение типа функции итератора или доступа `Get`, который содержит оператора `Yield`.|  
  
## Заметки  
 Выписка `Yield` возвращает один элемент коллекции одновременно.  Выписка `Yield` включена в функции итератора или доступе `Get`, которая выполняет пользовательские итерации по коллекции.  
  
 Используется функция итератора с помощью [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или запроса LINQ.  Все итерации цикла `For Each` вызывает функцию итератора.  При достижении выписка `Yield` в функции итератора, возвращается значение `expression` и текущего расположения в коде сохраняются.  Среда выполнения будет перезапуске из этого расположения при следующем вызове функции итератора данной функции.  
  
 Неявное преобразование должно существовать из типа `expression` в инструкцию `Yield` к возвращаемому типу итератора.  
  
 Можно использовать выписка `Exit Function` или `Return` для выполнения итерации.  
  
 "Выход" нет зарезервированого ключевые слова и имеет специальное значение, только если он используется в доступе функции `Iterator` или `Get`.  
  
 Дополнительные сведения о функциях итератора доступах и `Get` см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Функции итератора и получают доступ  
 Объявление функции итератора или доступа `Get` должно отвечать следующим требованиям.  
  
-   Он должен включать модификатор [Итератор](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   Он не может содержать параметры `ByRef`.  
  
 Функция итератора, не может содержаться в событии, конструкторе экземпляра, статическим конструктором, или статическом деструкторе.  
  
 Функция итератора может быть анонимной функции.  Для получения дополнительной информации см. [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Обработка исключений  
 Выписка `Yield` может быть внутри блока `Try`[Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  Блок `Try`, имеющий оператор `Yield`, может содержать блоки `Catch` и блок `Finally`.  
  
 Оператор `Yield` не может быть внутри блока `Catch` или блока `Finally`.  
  
 Если тело `For Each` \(вне функции итератора\) создает исключение, оно не выполняется блок `Catch` в функции итератора, но выполняется блок `Finally` в функции итератора.  Блок `Catch` внутри функции итератора перехватывает только исключения, происходящие внутри функции итератора.  
  
## Техническая реализация  
 Следующий код возвращает `IEnumerable (Of String)` из функции итератора и затем перебираются элементы `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Вызов `MyIteratorFunction` не выполняет тело функции.  Вместо этого вызов возвращается в переменную `IEnumerable(Of String)``elements`.  
  
 В итерации цикла `For Each`, метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`.  Этот вызов выполняется тело `MyIteratorFunction` до тех пор, пока не будет достигнут следующую выписка `Yield`.  Выписка `Yield` возвращает не только выражение, задающее значение переменной `element` для использования циклом, но и свойства элементов <xref:System.Collections.Generic.IEnumerator%601.Current%2A>, `IEnumerable (Of String)`.  
  
 В каждой последующей итерации цикла `For Each`, среда выполнения продолжает из тела итератора, где он вышло, снова остановка при достижении оператора `Yield`.  Цикл `For Each` завершается при достижении конца функции итератора или выписки `Return` или `Exit Function`.  
  
## Пример  
 В следующем примере два оператора `Yield`, внутри цикла [For… Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  Каждая итерация тела выписки [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) в `Main` создает вызов функции `Power` итератора.  Каждый вызов функции итератора переходит к следующему выполнения выписки `Yield`, которая происходит во время следующей итерации цикла `For…Next`.  
  
 Тип возвращаемого значения метода итератора <xref:System.Collections.Generic.IEnumerable%601> тип интерфейса итератора.  Если метод вызывается итератора, он возвращает перечислимый объект, содержащий степени числа.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/yield-statement_1.vb)]  
  
## Пример  
 В следующем примере демонстрируется доступа `Get`, итератор.  Объявление свойства включает модификатор `Iterator`.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/yield-statement_2.vb)]  
  
 Дополнительные примеры см. в разделе [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md).  
  
## Требования  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs-dev11-long-md.md)]  
  
## См. также  
 [Итераторы](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md)   
 [Операторы](../../../visual-basic/language-reference/statements/index.md)