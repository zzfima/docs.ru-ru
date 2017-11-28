---
title: "readonly (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords: readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b499f9fc5121afe6c2e92bcf8c5d2ac593b4c06c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="readonly-c-reference"></a><span data-ttu-id="d2a56-102">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d2a56-102">readonly (C# Reference)</span></span>
<span data-ttu-id="d2a56-103">Ключевое слово `readonly` — это модификатор, который можно использовать для полей.</span><span class="sxs-lookup"><span data-stu-id="d2a56-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="d2a56-104">Если объявление поля содержит модификатор `readonly`, присвоение значений таким полям может происходить только как часть объявления или в конструкторе в том же классе.</span><span class="sxs-lookup"><span data-stu-id="d2a56-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2a56-105">Пример</span><span class="sxs-lookup"><span data-stu-id="d2a56-105">Example</span></span>  
 <span data-ttu-id="d2a56-106">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="d2a56-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]  
  
 <span data-ttu-id="d2a56-107">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="d2a56-107">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="d2a56-108">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="d2a56-108">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="d2a56-109">Для поля экземпляра — в конструкторах экземпляров класса, содержащего объявление поля, или, для статического поля, — в статическом конструкторе класса, содержащего объявление поля.</span><span class="sxs-lookup"><span data-stu-id="d2a56-109">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="d2a56-110">Это единственно возможные контексты, в которых можно передавать поле `readonly` в качестве параметра [out](../../../csharp/language-reference/keywords/out.md) или [ref](../../../csharp/language-reference/keywords/ref.md).</span><span class="sxs-lookup"><span data-stu-id="d2a56-110">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d2a56-111">Ключевое слово `readonly` отличается от ключевого слова [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="d2a56-111">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="d2a56-112">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="d2a56-112">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="d2a56-113">Поле `readonly` может быть инициализировано при объявлении или в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="d2a56-113">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="d2a56-114">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="d2a56-114">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="d2a56-115">К тому же, в то время как поле `const` является константой во время компиляции, поле `readonly` можно использовать для констант во время выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d2a56-115">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="d2a56-116">Пример</span><span class="sxs-lookup"><span data-stu-id="d2a56-116">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]  
  
 <span data-ttu-id="d2a56-117">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="d2a56-117">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="d2a56-118">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="d2a56-118">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="d2a56-119">Это такая же ошибка, которая возникает при попытке присвоить значение константе.</span><span class="sxs-lookup"><span data-stu-id="d2a56-119">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d2a56-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d2a56-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2a56-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d2a56-121">See Also</span></span>  
 [<span data-ttu-id="d2a56-122">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d2a56-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d2a56-123">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d2a56-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d2a56-124">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d2a56-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d2a56-125">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="d2a56-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="d2a56-126">const</span><span class="sxs-lookup"><span data-stu-id="d2a56-126">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="d2a56-127">Поля</span><span class="sxs-lookup"><span data-stu-id="d2a56-127">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)
