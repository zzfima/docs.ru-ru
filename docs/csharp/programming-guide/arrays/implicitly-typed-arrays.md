---
title: "Неявно типизированные массивы (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- arrays [C#], implicity-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
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
ms.openlocfilehash: 5a042bdebd07062debe70cbea0a9661fbd425804
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Неявно типизированные массивы (Руководство по программированию на C#)
Вы можете создать неявно типизированный массив, тип экземпляра которого будет определяться на основе элементов, указанных в инициализаторе массива. В отношении таких массивов действуют правила для неявно типизированных переменных. Дополнительные сведения см. в статье [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Неявно типизированные локальные переменные).  
  
 Неявно типизированные массивы обычно используются в выражениях запросов вместе с анонимными типами, а также инициализаторами объектов и коллекций.  
  
 В следующих примерах демонстрируется создание неявно типизированного массива:  
  
 [!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 Обратите внимание, что в предыдущем примере с неявно типизированными массивами в левой части выражения инициализации не используются квадратные скобки. Также обратите внимание, что массивы массивов инициализируются с помощью выражения `new []`, как и одномерные массивы.  
  
## <a name="implicitly-typed-arrays-in-object-initializers"></a>Неявно типизированные массивы в инициализаторах объектов  
 При создании анонимного типа, содержащего массив, этот массив необходимо неявно типизировать в инициализаторе объекта типа. В следующем примере `contacts` представляет собой неявно типизированный массив анонимных типов, каждый из которых содержит массив с именем `PhoneNumbers`. Обратите внимание, что внутри инициализаторов объектов не используется ключевое слово `var`.  
  
 [!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Неявно типизированные локальные переменные](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Анонимные типы](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [Выражения запросов LINQ](../../../csharp/programming-guide/linq-query-expressions/index.md)

