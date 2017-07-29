---
title: "Автоматически реализуемые свойства (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
caps.latest.revision: 23
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
ms.openlocfilehash: 92e0037b73f1054673ea8060b71af5bd4db13ca3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="auto-implemented-properties-c-programming-guide"></a>Автоматически реализуемые свойства (Руководство по программированию на C#)
В C# 3.0 и более поздних версиях автоматически реализуемые свойства делают объявление свойств более лаконичным, когда в методах доступа к свойствам не требуется дополнительная логика. Они также позволяют клиентскому коду создавать объекты. При объявлении свойства, как показано в следующем примере, компилятор создает закрытое анонимное резервное поле, которое может быть доступно только через методы доступа `get` и `set` свойства.  
  
## <a name="example"></a>Пример  
 В следующем примере показан простой класс, имеющий несколько автоматически реализуемых свойств.  
  
 [!code-cs[csProgGuideLINQ #28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 В C# 6 и более поздних версиях можно инициализировать автоматически реализуемые свойства аналогично полям.  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 Класс, который показан в предыдущем примере, является изменяемым. Клиентский код может изменить значения в объектах после их создания. В сложных классах, которые содержат значительные возможности (методы) и данные, часто необходимо иметь открытые свойства. Однако для небольших классов или структур, которые просто инкапсулируют набор значений (данных) и имеют мало функциональных возможностей или совсем их не имеют, вы должны сделать объекты неизменяемыми либо путем объявления метода доступа set как [закрытого](../../../csharp/language-reference/keywords/private.md) (неизменяемого для потребителей), либо путем объявления только метода доступа get (неизменяемого везде, кроме конструктора).  Дополнительные сведения см. в статье [Практическое руководство. Реализация облегченного класса с автоматически реализуемыми свойствами](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).  
  
 Атрибуты в автоматически реализуемых свойствах допускаются, но очевидно не в резервных полях, так как они недоступны из исходного кода. Если вам необходимо использовать атрибут в резервном поле свойства, просто создайте обычное свойство.  
  
## <a name="see-also"></a>См. также  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)

