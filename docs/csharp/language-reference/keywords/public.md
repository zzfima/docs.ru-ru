---
title: "public (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
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
ms.openlocfilehash: ae19bf9a33a9860a8960cde5dd4402e10418a094
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="public-c-reference"></a>public (справочник по C#)
Ключевое слово `public` является модификатором доступа для типов и членов типов. Общий доступ является уровнем доступа с максимальными правами. Ограничений доступа к общим членам не существует, как показано в следующем примере:  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 Дополнительные сведения см. в разделах [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) и [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## <a name="example"></a>Пример  
 В следующем примере объявляются два класса: `PointTest` и `MainClass`. Доступ к открытым членам `x` и `y` класса `PointTest` осуществляется непосредственно из класса `MainClass`.  
  
 [!code-cs[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 Если уровень доступа `public` изменить на [private](../../../csharp/language-reference/keywords/private.md) или [protected](../../../csharp/language-reference/keywords/protected.md), будет выводится следующее сообщение об ошибке:  
  
 "PointTest.y" недоступен из-за его уровня защиты.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

