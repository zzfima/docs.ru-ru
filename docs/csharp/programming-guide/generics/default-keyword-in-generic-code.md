---
title: "Ключевое слово default в универсальном коде (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b5f5995b720d377717a5fff8a5e7e6e2196c612c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="default-keyword-in-generic-code-c-programming-guide"></a>Ключевое слово default в универсальном коде (Руководство по программированию на C#)
В универсальных классах и методах существует проблема, связанная с присваиванием значения по умолчанию параметризованному типу T, для которого заранее неизвестны следующие характеристики:  
  
-   Будет ли тип T ссылочным типом или типом значения.  
  
-   Если тип T является типом значения, будет ли это числовое значение или структура.  
  
 Для переменной t, имеющей параметризованный тип T, оператор t = null будет допустимым только в том случае, если тип T является ссылочным, а оператор t = 0 действителен только для числовых типов значения и не подходит для структур. Решение заключается в использовании ключевого слова `default`, которое возвращает NULL для ссылочных типов и ноль для числовых типов значений. Для структур это ключевое слово возвращает каждый член структуры, который был инициализирован с использованием нулевого значения или значения NULL в зависимости от того, имеет ли он тип значения или ссылочный тип. Для типов значений, допускающих значения NULL, ключевое слово default возвращает <xref:System.Nullable%601?displayProperty=fullName>, которое инициализируется как любая другая структура.  
  
 В следующем примере на основе класса `GenericList<T>` показано, как использовать ключевое слово `default`. Дополнительные сведения см. в разделе [Общие сведения об универсальных шаблонах](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Универсальные шаблоны](~/docs/standard/generics/index.md)

