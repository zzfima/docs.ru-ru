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
# <a name="readonly-c-reference"></a><span data-ttu-id="5799c-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="5799c-102">readonly (C# Reference)</span></span>
<span data-ttu-id="5799c-103">Ключевое слово `readonly` — это модификатор, который можно использовать для полей.</span><span class="sxs-lookup"><span data-stu-id="5799c-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="5799c-104">Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.</span><span class="sxs-lookup"><span data-stu-id="5799c-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5799c-105">Пример</span><span class="sxs-lookup"><span data-stu-id="5799c-105">Example</span></span>  
 <span data-ttu-id="5799c-106">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="5799c-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 <span data-ttu-id="5799c-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5799c-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span></span>  
  
 <span data-ttu-id="5799c-108">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="5799c-108">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="5799c-109">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="5799c-109">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="5799c-110">Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля, — в статическом конструкторе класса, содержащего объявление поля.</span><span class="sxs-lookup"><span data-stu-id="5799c-110">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="5799c-111">Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out.md) или [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="5799c-111">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5799c-112">Ключевое слово `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="5799c-112">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="5799c-113">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="5799c-113">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="5799c-114">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="5799c-114">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="5799c-115">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="5799c-115">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="5799c-116">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="5799c-116">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="5799c-117">Пример</span><span class="sxs-lookup"><span data-stu-id="5799c-117">Example</span></span>  
 <span data-ttu-id="5799c-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5799c-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span></span>  
  
 <span data-ttu-id="5799c-119">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="5799c-119">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="5799c-120">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="5799c-120">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="5799c-121">Это такая же ошибка, которая возникает при попытке присвоить значение константе.</span><span class="sxs-lookup"><span data-stu-id="5799c-121">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5799c-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5799c-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5799c-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5799c-123">See Also</span></span>  
 <span data-ttu-id="5799c-124">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5799c-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5799c-125">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5799c-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5799c-126">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5799c-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5799c-127">[Модификаторы](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="5799c-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="5799c-128">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="5799c-128">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 [<span data-ttu-id="5799c-129">Поля</span><span class="sxs-lookup"><span data-stu-id="5799c-129">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

