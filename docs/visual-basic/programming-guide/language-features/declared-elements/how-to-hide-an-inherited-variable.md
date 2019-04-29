---
title: Практическое руководство. Сокрытие наследуемой переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: ee147ecd00b88b538ace32844c42ac9c5022b2ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794697"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="9a178-102">Практическое руководство. Сокрытие наследуемой переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a178-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="9a178-103">Производный класс наследует все определения базового класса.</span><span class="sxs-lookup"><span data-stu-id="9a178-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="9a178-104">Если вы хотите определить переменную с тем же именем, что элемент базового класса, можно скрыть, или *тени*, этот элемент базового класса при определении переменной в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9a178-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="9a178-105">После этого код в производном классе получает доступ к переменной, если явно не обходится скрывающий механизм.</span><span class="sxs-lookup"><span data-stu-id="9a178-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="9a178-106">Другой причиной может потребоваться сокрытие наследуемой переменной является защита версии базового класса.</span><span class="sxs-lookup"><span data-stu-id="9a178-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="9a178-107">Базовый класс может претерпеть изменения, изменяющей элемента, к которому вы наследуете.</span><span class="sxs-lookup"><span data-stu-id="9a178-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="9a178-108">В этом случае `Shadows` модификатор заставляет ссылки из производного класса разрешаться в переменную, а не в элемент базового класса.</span><span class="sxs-lookup"><span data-stu-id="9a178-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="9a178-109">Чтобы скрыть наследуемой переменной</span><span class="sxs-lookup"><span data-stu-id="9a178-109">To hide an inherited variable</span></span>  
  
1. <span data-ttu-id="9a178-110">Убедитесь, что переменная, которую вы хотите скрыть объявлен на уровне класса (вне любых процедур).</span><span class="sxs-lookup"><span data-stu-id="9a178-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="9a178-111">В противном случае не нужно скрыть его.</span><span class="sxs-lookup"><span data-stu-id="9a178-111">Otherwise you do not need to hide it.</span></span>  
  
2. <span data-ttu-id="9a178-112">Внутри производного класса, напишите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) объявляющий переменную.</span><span class="sxs-lookup"><span data-stu-id="9a178-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="9a178-113">Использование тем же именем, что и наследуемой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a178-113">Use the same name as that of the inherited variable.</span></span>  
  
3. <span data-ttu-id="9a178-114">Включить [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в объявлении.</span><span class="sxs-lookup"><span data-stu-id="9a178-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="9a178-115">Когда код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="9a178-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="9a178-116">В следующем примере показано переобъявлять наследуемой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a178-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
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
  
     <span data-ttu-id="9a178-117">В предыдущем примере объявляется переменной `shadowString` в базовом классе, скрывается в производном классе.</span><span class="sxs-lookup"><span data-stu-id="9a178-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="9a178-118">Процедура `showStrings` в производном классе отображает версию затенения строки при имя `shadowString` не обработаны квалификатором.</span><span class="sxs-lookup"><span data-stu-id="9a178-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="9a178-119">Затем он отобразит затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="9a178-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9a178-120">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="9a178-120">Robust Programming</span></span>  
 <span data-ttu-id="9a178-121">Затенение представляет несколько версий переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="9a178-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="9a178-122">Если оператор кода ссылается на имя переменной, версии, к которому компилятор разрешает ссылку зависит от факторов, таких как расположение оператор кода, а также наличие уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="9a178-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="9a178-123">Это может увеличить риск ссылки на неправильную версию затененной переменной.</span><span class="sxs-lookup"><span data-stu-id="9a178-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="9a178-124">Можно снизить этот риск путем полного все ссылки на переменную тенью.</span><span class="sxs-lookup"><span data-stu-id="9a178-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a178-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9a178-125">See also</span></span>

- [<span data-ttu-id="9a178-126">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="9a178-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="9a178-127">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9a178-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="9a178-128">Различия между затемнением и переопределением</span><span class="sxs-lookup"><span data-stu-id="9a178-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="9a178-129">Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная</span><span class="sxs-lookup"><span data-stu-id="9a178-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="9a178-130">Практическое руководство. Доступ к переменной, скрытой производным классом</span><span class="sxs-lookup"><span data-stu-id="9a178-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="9a178-131">Переопределения</span><span class="sxs-lookup"><span data-stu-id="9a178-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="9a178-132">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="9a178-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="9a178-133">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="9a178-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
