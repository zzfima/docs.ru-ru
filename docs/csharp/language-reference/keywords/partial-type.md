---
title: "разделяемый (тип) (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
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
ms.openlocfilehash: 5405455d933f6512cfa3a18e1a545556c5715151
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="partial-type-c-reference"></a>разделяемый (тип) (Справочник по C#)
Определения разделяемых типов позволяют разделять определения классов, структур и интерфейсов на несколько файлов.  
  
 В File1.cs:  
  
 [!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 В File2.cs объявление:  
  
 [!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a>Примечания  
 Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например предоставляемым [конструктором Windows Forms](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15). Разделяемый тип может содержать [разделяемый метод](../../../csharp/language-reference/keywords/partial-method.md). Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)

