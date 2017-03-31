---
title: "Оператор new (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f0831bbbaf68c8c9e1e0e2d77ccf18e7c8b42e4a
ms.lasthandoff: 03/13/2017

---
# <a name="new-operator-c-reference"></a>Оператор new (Справочник по C#)
Применяется для создания объектов и вызова конструкторов. Например:  
  
```  
Class1 obj  = new Class1();  
```  
  
 Он также используется для создания экземпляров анонимных типов.  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 С помощью оператора `new` можно вызвать заданный по умолчанию конструктор для типов значений. Например:  
  
```  
int i = new int();  
```  
  
 В предыдущем операторе `i` инициализируется значением `0`, которое является значением по умолчанию для типа `int`. Этот оператор приводит к результату, представленному далее.  
  
```  
int i = 0;  
```  
  
 Полный список значений по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Следует помнить, что объявление конструктора по умолчанию для [структуры](../../../csharp/language-reference/keywords/struct.md) является ошибкой, поскольку каждый тип значения неявно имеет открытый заданный по умолчанию конструктор. Можно объявить параметризованные конструкторы в типе структуры, чтобы задать начальные значения, однако это необходимо, только если требуются значения, отличные от установленных по умолчанию.  
  
 Объекты типа значения, например структуры, создаются в стеке, тогда как объекты ссылочного типа, например классы, создаются в куче. Уничтожение обоих типов объектов выполняется автоматически, но объекты на основе типов значений удаляются при выходе за рамки области действия, а объекты на основе ссылочных типов — в неуказанное время после удаления последней ссылки, указывающей на них. Для ссылочных типов, использующих фиксированные ресурсы, например большой объем памяти, файловые дескрипторы, сетевые подключения, иногда рекомендуется использовать детерминированную финализацию для обеспечения скорейшего уничтожения объекта. Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Оператор `new` перегрузить нельзя.  
  
 Если оператору `new` не удается выделить память, он создает исключение <xref:System.OutOfMemoryException>.  
  
## <a name="example"></a>Пример  
 В следующем примере создаются объект `struct` и объект класса, которые инициализируются с помощью оператора `new`, после чего им присваиваются значения. Отображаются заданные по умолчанию и присвоенные значения.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 Обратите внимание, что в примере строка имеет значение по умолчанию `null`. Поэтому она не отображается.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)
