---
title: Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648051"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="4366b-102">Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4366b-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="4366b-103">Когда код в производном классе получает доступ к переменной, компилятор обычно разрешает ссылку на ближайшую доступную версию, то есть доступный минимальное количество производных действий назад от обращающегося класса.</span><span class="sxs-lookup"><span data-stu-id="4366b-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="4366b-104">Если переменная определена в производном классе, код обычно обращается к этому определению.</span><span class="sxs-lookup"><span data-stu-id="4366b-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="4366b-105">Если переменная производного класса затеняет переменную в базовом классе, он скрывает версии базового класса.</span><span class="sxs-lookup"><span data-stu-id="4366b-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="4366b-106">Тем не менее, можно получить доступ к переменной базового класса путем определения ее с `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4366b-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="4366b-107">Чтобы получить доступ к переменной базового класса, скрытой производным классом</span><span class="sxs-lookup"><span data-stu-id="4366b-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="4366b-108">В выражение или оператор присваивания, перед именем переменной с `MyBase` ключевое слово и точку (`.`).</span><span class="sxs-lookup"><span data-stu-id="4366b-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="4366b-109">Компилятор разрешает ссылку на версию базового класса переменной.</span><span class="sxs-lookup"><span data-stu-id="4366b-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="4366b-110">В следующем примере показано затемнения посредством наследования.</span><span class="sxs-lookup"><span data-stu-id="4366b-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="4366b-111">Он делает две ссылки, который обращается к переменной затенения, а другой обходит затенение.</span><span class="sxs-lookup"><span data-stu-id="4366b-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="4366b-112">В предыдущем примере объявляются переменная `shadowString` в базовом классе, скрывается в производном классе.</span><span class="sxs-lookup"><span data-stu-id="4366b-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="4366b-113">Процедура `showStrings` в производном классе отображает версию затенения строки, если имя `shadowString` не обработаны квалификатором.</span><span class="sxs-lookup"><span data-stu-id="4366b-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="4366b-114">Затем отображается затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="4366b-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4366b-115">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4366b-115">Robust Programming</span></span>  
 <span data-ttu-id="4366b-116">Чтобы снизить риск ссылки на неправильную версию затененной переменной, можно полностью определить все ссылки на затененную переменную.</span><span class="sxs-lookup"><span data-stu-id="4366b-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="4366b-117">Затенение представляет несколько версий переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="4366b-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="4366b-118">Когда оператор кода ссылается на имя переменной, версии, для которого компилятор разрешает ссылку зависит от факторов, таких как расположение оператора кода и наличие уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="4366b-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="4366b-119">Это может увеличить риск ссылки на неправильную версию переменной.</span><span class="sxs-lookup"><span data-stu-id="4366b-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4366b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4366b-120">See Also</span></span>  
 [<span data-ttu-id="4366b-121">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="4366b-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="4366b-122">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4366b-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="4366b-123">Различия между затемнением и переопределением</span><span class="sxs-lookup"><span data-stu-id="4366b-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="4366b-124">Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная</span><span class="sxs-lookup"><span data-stu-id="4366b-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="4366b-125">Практическое руководство. Сокрытие наследуемой переменной</span><span class="sxs-lookup"><span data-stu-id="4366b-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="4366b-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="4366b-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="4366b-127">Переопределения</span><span class="sxs-lookup"><span data-stu-id="4366b-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="4366b-128">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="4366b-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="4366b-129">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="4366b-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
