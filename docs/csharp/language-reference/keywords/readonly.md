---
title: "readonly (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
dev_langs:
- CSharp
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
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
ms.openlocfilehash: 2660aa56721815cbbeb668328863956473cce8f1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="readonly-c-reference"></a>readonly (Справочник по C#)
Ключевое слово `readonly` — это модификатор, который можно использовать для полей. Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.  
  
## <a name="example"></a>Пример  
 В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:  
  
 [!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Можно присвоить значение полю `readonly` только в следующих контекстах:  
  
-   Когда переменная инициализируется в объявлении, например:  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля, — в статическом конструкторе класса, содержащего объявление поля. Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out.md) или [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  Ключевое слово `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md). Поле `const` может быть инициализировано только при объявлении поля. Поле `readonly` может быть инициализировано при объявлении или в конструкторе. Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора. К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 В предыдущем примере при использовании такого оператора:  
  
 `p2.y = 66;        // Error`  
  
 будет отображено сообщение об ошибке компилятора:  
  
 `The left-hand side of an assignment must be an l-value`  
  
 Это такая же ошибка, которая возникает при попытке присвоить значение константе.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [Поля](../../../csharp/programming-guide/classes-and-structs/fields.md)

