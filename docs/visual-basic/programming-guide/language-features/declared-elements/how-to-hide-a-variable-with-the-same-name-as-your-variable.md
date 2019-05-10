---
title: Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 3230dac924e9c22231494bfc8b81cd74e356bca3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610316"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="c95f2-102">Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c95f2-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>
<span data-ttu-id="c95f2-103">Можно скрыть переменной с *затенение* его, то есть путем переопределения его с переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c95f2-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="c95f2-104">Можно скрыть переменную, которую вы хотите скрыть двумя способами:</span><span class="sxs-lookup"><span data-stu-id="c95f2-104">You can shadow the variable you want to hide in two ways:</span></span>  
  
- <span data-ttu-id="c95f2-105">**Затемнения посредством области.**</span><span class="sxs-lookup"><span data-stu-id="c95f2-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="c95f2-106">Его можно скрыть области видимости, путем ее переопределения внутри входит в область, содержащая переменную, которую вы хотите скрыть.</span><span class="sxs-lookup"><span data-stu-id="c95f2-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>  
  
- <span data-ttu-id="c95f2-107">**Затемнения посредством наследования.**</span><span class="sxs-lookup"><span data-stu-id="c95f2-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="c95f2-108">Если вы хотите скрыть переменная определяется на уровне класса, можно скрыть его через наследование путем ее переопределения с [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в производном классе.</span><span class="sxs-lookup"><span data-stu-id="c95f2-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>  
  
## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="c95f2-109">Два способа скрыть переменной</span><span class="sxs-lookup"><span data-stu-id="c95f2-109">Two Ways to Hide a Variable</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="c95f2-110">Чтобы скрыть переменную с помощью области</span><span class="sxs-lookup"><span data-stu-id="c95f2-110">To hide a variable by shadowing it through scope</span></span>  
  
1. <span data-ttu-id="c95f2-111">Определите переменную, которую вы хотите скрыть область и подобласть, в котором следует переопределить его переменной.</span><span class="sxs-lookup"><span data-stu-id="c95f2-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>  
  
    |<span data-ttu-id="c95f2-112">Область переменной</span><span class="sxs-lookup"><span data-stu-id="c95f2-112">Variable's region</span></span>|<span data-ttu-id="c95f2-113">Допустимые подобласти для ее переопределения</span><span class="sxs-lookup"><span data-stu-id="c95f2-113">Allowable subregion for redefining it</span></span>|  
    |-----------------------|-------------------------------------------|  
    |<span data-ttu-id="c95f2-114">Module</span><span class="sxs-lookup"><span data-stu-id="c95f2-114">Module</span></span>|<span data-ttu-id="c95f2-115">Класс в модуле</span><span class="sxs-lookup"><span data-stu-id="c95f2-115">A class within the module</span></span>|  
    |<span data-ttu-id="c95f2-116">Класс</span><span class="sxs-lookup"><span data-stu-id="c95f2-116">Class</span></span>|<span data-ttu-id="c95f2-117">Подкласс внутри класса</span><span class="sxs-lookup"><span data-stu-id="c95f2-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="c95f2-118">Процедура внутри класса</span><span class="sxs-lookup"><span data-stu-id="c95f2-118">A procedure within the class</span></span>|  
  
     <span data-ttu-id="c95f2-119">Не удалось переопределить переменную процедуры в блоке, в рамках этой процедуры, например в `If`... `End If` конструкции или `For` цикла.</span><span class="sxs-lookup"><span data-stu-id="c95f2-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>  
  
2. <span data-ttu-id="c95f2-120">Создайте подобласть, если он еще не существует.</span><span class="sxs-lookup"><span data-stu-id="c95f2-120">Create the subregion if it does not already exist.</span></span>  
  
3. <span data-ttu-id="c95f2-121">В пределах подобласти, написать [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) объявление переменной затенения.</span><span class="sxs-lookup"><span data-stu-id="c95f2-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>  
  
     <span data-ttu-id="c95f2-122">Когда код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку переменной затенения.</span><span class="sxs-lookup"><span data-stu-id="c95f2-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>  
  
     <span data-ttu-id="c95f2-123">В следующем примере показано, затемнения посредством области, а также ссылку, которая обходит затенение.</span><span class="sxs-lookup"><span data-stu-id="c95f2-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     <span data-ttu-id="c95f2-124">В предыдущем примере объявляется переменной `num` как на уровне модуля, так и на уровне процедуры (в процедуре `show`).</span><span class="sxs-lookup"><span data-stu-id="c95f2-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="c95f2-125">Локальная переменная `num` скрывает переменную уровня модуля `num` в `show`, поэтому локальная переменная имеет значение 2.</span><span class="sxs-lookup"><span data-stu-id="c95f2-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="c95f2-126">Тем не менее, не существует локальной переменной в теневую `num` в `useModuleLevelNum` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c95f2-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="c95f2-127">Таким образом `useModuleLevelNum` присваивает значение переменной уровня модуля 1.</span><span class="sxs-lookup"><span data-stu-id="c95f2-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>  
  
     <span data-ttu-id="c95f2-128">`MsgBox` Вызывать внутри `show` обходит скрывающий механизм путем уточнения `num` с именем модуля.</span><span class="sxs-lookup"><span data-stu-id="c95f2-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="c95f2-129">Таким образом он отображает переменную уровня модуля, а не локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="c95f2-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="c95f2-130">Чтобы скрыть переменную с помощью наследования</span><span class="sxs-lookup"><span data-stu-id="c95f2-130">To hide a variable by shadowing it through inheritance</span></span>  
  
1. <span data-ttu-id="c95f2-131">Убедитесь, что переменная, которую вы хотите скрыть объявлена в классе, а также на уровне класса (вне любых процедур).</span><span class="sxs-lookup"><span data-stu-id="c95f2-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="c95f2-132">В противном случае он не может Затенять через наследование.</span><span class="sxs-lookup"><span data-stu-id="c95f2-132">Otherwise you cannot shadow it through inheritance.</span></span>  
  
2. <span data-ttu-id="c95f2-133">Определите класс, производный от класса переменной, если еще не существует.</span><span class="sxs-lookup"><span data-stu-id="c95f2-133">Define a class derived from the variable's class if one does not already exist.</span></span>  
  
3. <span data-ttu-id="c95f2-134">Внутри производного класса, напишите `Dim` инструкции объявления переменной.</span><span class="sxs-lookup"><span data-stu-id="c95f2-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="c95f2-135">Включить [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в объявлении.</span><span class="sxs-lookup"><span data-stu-id="c95f2-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="c95f2-136">Когда код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="c95f2-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="c95f2-137">В следующем примере показано, затемнения посредством наследования.</span><span class="sxs-lookup"><span data-stu-id="c95f2-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="c95f2-138">Он делает две ссылки, который обращается к переменной затенения, а другой обходит затенение.</span><span class="sxs-lookup"><span data-stu-id="c95f2-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="c95f2-139">В предыдущем примере объявляется переменной `shadowString` в базовом классе, скрывается в производном классе.</span><span class="sxs-lookup"><span data-stu-id="c95f2-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="c95f2-140">Процедура `showStrings` в производном классе отображает версию затенения строки при имя `shadowString` не обработаны квалификатором.</span><span class="sxs-lookup"><span data-stu-id="c95f2-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="c95f2-141">Затем он отобразит затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="c95f2-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c95f2-142">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="c95f2-142">Robust Programming</span></span>  
 <span data-ttu-id="c95f2-143">Затенение представляет несколько версий переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c95f2-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="c95f2-144">Если оператор кода ссылается на имя переменной, версии, к которому компилятор разрешает ссылку зависит от факторов, таких как расположение оператор кода, а также наличие уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="c95f2-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="c95f2-145">Это может увеличить риск ссылки на неправильную версию затененной переменной.</span><span class="sxs-lookup"><span data-stu-id="c95f2-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="c95f2-146">Можно снизить этот риск путем полного все ссылки на переменную тенью.</span><span class="sxs-lookup"><span data-stu-id="c95f2-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c95f2-147">См. также</span><span class="sxs-lookup"><span data-stu-id="c95f2-147">See also</span></span>

- [<span data-ttu-id="c95f2-148">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="c95f2-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c95f2-149">Сокрытие в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c95f2-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="c95f2-150">Различия между затемнением и переопределением</span><span class="sxs-lookup"><span data-stu-id="c95f2-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="c95f2-151">Практическое руководство. Сокрытие наследуемой переменной</span><span class="sxs-lookup"><span data-stu-id="c95f2-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="c95f2-152">Практическое руководство. Доступ к переменной, скрытой производным классом</span><span class="sxs-lookup"><span data-stu-id="c95f2-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="c95f2-153">Переопределения</span><span class="sxs-lookup"><span data-stu-id="c95f2-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c95f2-154">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="c95f2-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="c95f2-155">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="c95f2-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
