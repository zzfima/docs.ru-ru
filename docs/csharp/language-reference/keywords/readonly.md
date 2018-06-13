---
title: readonly (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d2f8a2f192dc319ad806aeef4bfbaeecc44b07a3
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172637"
---
# <a name="readonly-c-reference"></a>readonly (Справочник по C#)
Ключевое слово `readonly` — это модификатор, который можно использовать для полей. Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.  
  
## <a name="readonly-field-example"></a>Пример поля только для чтения  
 В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 Можно присвоить значение полю `readonly` только в следующих контекстах:  
  
-   Когда переменная инициализируется в объявлении, например:  
  
    ```csharp  
    public readonly int y = 5;  
    ```  
  
-   Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля, — в статическом конструкторе класса, содержащего объявление поля. Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) или [ref](../../../csharp/language-reference/keywords/ref.md).  
  
> [!NOTE]
>  Ключевое слово `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md). Поле `const` может быть инициализировано только при объявлении поля. Поле `readonly` может быть инициализировано при объявлении или в конструкторе. Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора. К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:  
  
```csharp  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="comparing-readonly-and-non-readonly-instance-fields"></a>Сравнение полей экземпляров, доступных только для чтения и не только для чтения  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
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
