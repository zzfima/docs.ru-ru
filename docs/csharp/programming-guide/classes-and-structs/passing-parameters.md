---
title: "Передача параметров (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
caps.latest.revision: 17
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
ms.openlocfilehash: 4b8c0c7f7b8c3820edbafbe90fb961c12da8fc84
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="passing-parameters-c-programming-guide"></a>Передача параметров (Руководство по программированию в C#)
В C# аргументы могут передаваться параметрам либо по значению, либо по ссылке. Передача по ссылке позволяет изменять и сохранять измененные значения параметров членов функций, методов, свойств, индексаторов, операторов и конструкторов в вызывающей среде. Для передачи параметра по ссылке используйте ключевое слово `ref` или `out`. Для простоты в этих примерах используется только ключевое слово `ref`. Дополнительные сведения о различиях между ключевыми словами `ref` и `out` см. в разделах [ref](../../../csharp/language-reference/keywords/ref.md), [out](../../../csharp/language-reference/keywords/out.md) и [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 В приведенном ниже примере показано различие между параметрами-значениями и ссылочными параметрами.  
  
 [!code-cs[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [Передача параметров типа значения](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [Передача параметров ссылочного типа](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)

