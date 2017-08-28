---
title: "Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ad81ab699b079f4aabb04a886211e94a937335d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a>Практическое руководство. Доступ к классу коллекции с помощью оператора foreach (Руководство по программированию в C#)
В следующем примере кода показано, как записать неуниверсальный класс коллекции, который можно использовать с оператором [foreach](../../../csharp/language-reference/keywords/foreach-in.md). В этом примере определяется класс строкового лексического анализатора.  
  
> [!NOTE]
>  Этот пример представляет рекомендованный способ, только если использование универсального класса коллекции невозможно. Пример реализации типобезопасного универсального класса коллекции, поддерживающего <xref:System.Collections.Generic.IEnumerable%601>, см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
 В этом примере следующий сегмент кода использует класс `Tokens` для разделения предложения "Это предложение-образец" на токены с помощью разделителей " " и "-". Затем код отображает эти токены с помощью оператора `foreach`.  
  
 [!code-cs[csProgGuideCollections #3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a>Пример  
 По сути, класс `Tokens` использует массив для хранения токенов. Поскольку массивы реализуют <xref:System.Collections.IEnumerator> и <xref:System.Collections.IEnumerable>, в этом примере кода можно использовать методы перечисления массива (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>) вместо того, чтобы определять их в классе `Tokens`. Определения методов содержатся в примере для уточнения способа их определения и предназначения каждого из них.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 В C# для класса коллекции необязательно реализовывать <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> в совместимой с `foreach` форме. Если класс содержит необходимые члены <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> и <xref:System.Collections.IEnumerator.Current%2A>, он может работать с циклом `foreach`. Пропуск интерфейсов имеет преимущество, поскольку позволяет определить тип возврата для `Current`, который более специфичен, чем тип <xref:System.Object>. Это повышает типобезопасность.  
  
 Например, измените следующие строки в предыдущем примере.  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 Поскольку `Current` возвращает строку, компилятор может определить, когда используется несовместимый тип в операторе `foreach`, как показано в следующем коде.  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 Недостатком пропуска типов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> является то, что класс коллекции больше не может взаимодействовать с операторами `foreach` или эквивалентными операторами из других языков среды CLR.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Коллекции](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

