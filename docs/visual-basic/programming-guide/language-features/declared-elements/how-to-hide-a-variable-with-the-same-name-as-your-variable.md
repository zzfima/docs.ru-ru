---
title: Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная
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
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345360"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="dac10-102">Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dac10-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="dac10-103">Переменную можно скрыть, то есть Переопределяя *ее переменной* с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="dac10-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="dac10-104">Переменную, которую нужно скрыть, можно затенить двумя способами:</span><span class="sxs-lookup"><span data-stu-id="dac10-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="dac10-105">**Затенение через область.**</span><span class="sxs-lookup"><span data-stu-id="dac10-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="dac10-106">Это можно сделать с помощью области, переобъявляя ее в подобласти области, содержащей переменную, которую необходимо скрыть.</span><span class="sxs-lookup"><span data-stu-id="dac10-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="dac10-107">**Затенение посредством наследования.**</span><span class="sxs-lookup"><span data-stu-id="dac10-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="dac10-108">Если переменная, которую нужно скрыть, определена на уровне класса, ее можно затенить с помощью наследования, повторно объявляя ее с помощью ключевого слова [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) в производном классе.</span><span class="sxs-lookup"><span data-stu-id="dac10-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="dac10-109">Два способа скрыть переменную</span><span class="sxs-lookup"><span data-stu-id="dac10-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="dac10-110">Скрытие переменной путем ее скрытия с помощью Scope</span><span class="sxs-lookup"><span data-stu-id="dac10-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="dac10-111">Определите регион, определяющий переменную, которую необходимо скрыть, и определите подобласть, в которой нужно переопределить переменную.</span><span class="sxs-lookup"><span data-stu-id="dac10-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="dac10-112">Регион переменной</span><span class="sxs-lookup"><span data-stu-id="dac10-112">Variable's region</span></span>|<span data-ttu-id="dac10-113">Допустимая подобласть для переопределения</span><span class="sxs-lookup"><span data-stu-id="dac10-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="dac10-114">Модуль</span><span class="sxs-lookup"><span data-stu-id="dac10-114">Module</span></span>|<span data-ttu-id="dac10-115">Класс внутри модуля</span><span class="sxs-lookup"><span data-stu-id="dac10-115">A class within the module</span></span>|
    |<span data-ttu-id="dac10-116">Class</span><span class="sxs-lookup"><span data-stu-id="dac10-116">Class</span></span>|<span data-ttu-id="dac10-117">Подкласс в классе</span><span class="sxs-lookup"><span data-stu-id="dac10-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="dac10-118">Процедура в классе</span><span class="sxs-lookup"><span data-stu-id="dac10-118">A procedure within the class</span></span>|

    <span data-ttu-id="dac10-119">Нельзя переопределить переменную процедуры в блоке внутри этой процедуры, например в конструкции `If`...`End If` или в цикле `For`.</span><span class="sxs-lookup"><span data-stu-id="dac10-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="dac10-120">Создайте подобласть, если она еще не существует.</span><span class="sxs-lookup"><span data-stu-id="dac10-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="dac10-121">В пределах подобласти напишите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) , объявляющий переменную с тенью.</span><span class="sxs-lookup"><span data-stu-id="dac10-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="dac10-122">Если код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку на переменную с тенью.</span><span class="sxs-lookup"><span data-stu-id="dac10-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="dac10-123">В следующем примере демонстрируется затенение через область, а также ссылка, которая обходит затенение.</span><span class="sxs-lookup"><span data-stu-id="dac10-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="dac10-124">В предыдущем примере переменная объявляется `num` как на уровне модуля, так и на уровне процедуры (в процедуре `show`).</span><span class="sxs-lookup"><span data-stu-id="dac10-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="dac10-125">Локальная переменная `num` затеняет переменную уровня модуля `num` в пределах `show`, поэтому локальной переменной присваивается значение 2.</span><span class="sxs-lookup"><span data-stu-id="dac10-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="dac10-126">Однако в процедуре `useModuleLevelNum` нет локальной переменной для теневого `num`.</span><span class="sxs-lookup"><span data-stu-id="dac10-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="dac10-127">Таким образом, `useModuleLevelNum` устанавливает значение переменной уровня модуля равным 1.</span><span class="sxs-lookup"><span data-stu-id="dac10-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="dac10-128">`MsgBox` вызов в `show` обходит механизм теневого копирования путем уточнения `num` именем модуля.</span><span class="sxs-lookup"><span data-stu-id="dac10-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="dac10-129">Таким образом, вместо локальной переменной отображается переменная уровня модуля.</span><span class="sxs-lookup"><span data-stu-id="dac10-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="dac10-130">Скрытие переменной путем ее скрытия с помощью наследования</span><span class="sxs-lookup"><span data-stu-id="dac10-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="dac10-131">Убедитесь, что переменная, которую нужно скрыть, объявлена в классе и на уровне класса (вне любой процедуры).</span><span class="sxs-lookup"><span data-stu-id="dac10-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="dac10-132">В противном случае ее нельзя будет скрыть с помощью наследования.</span><span class="sxs-lookup"><span data-stu-id="dac10-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="dac10-133">Определите класс, производный от класса переменной, если он еще не существует.</span><span class="sxs-lookup"><span data-stu-id="dac10-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="dac10-134">Внутри производного класса напишите оператор `Dim`, объявляющий переменную.</span><span class="sxs-lookup"><span data-stu-id="dac10-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="dac10-135">Включите в объявление ключевое слово [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) .</span><span class="sxs-lookup"><span data-stu-id="dac10-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="dac10-136">Если код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.</span><span class="sxs-lookup"><span data-stu-id="dac10-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="dac10-137">В следующем примере показано затенение с помощью наследования.</span><span class="sxs-lookup"><span data-stu-id="dac10-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="dac10-138">Он делает две ссылки — одну, которая обращается к переменной с тенью, и одну, которая обходит затенение.</span><span class="sxs-lookup"><span data-stu-id="dac10-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="dac10-139">В предыдущем примере переменная объявляется `shadowString` в базовом классе и скрывается в производном классе.</span><span class="sxs-lookup"><span data-stu-id="dac10-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="dac10-140">Процедура, `showStrings` в производном классе, отображает версию строки с тенью, если имя `shadowString` не является полным.</span><span class="sxs-lookup"><span data-stu-id="dac10-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="dac10-141">Затем отображается затененная версия, если `shadowString` дополнено ключевым словом `MyBase`.</span><span class="sxs-lookup"><span data-stu-id="dac10-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="dac10-142">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="dac10-142">Robust Programming</span></span>

<span data-ttu-id="dac10-143">При затенении введено более одной версии переменной с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="dac10-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="dac10-144">Если инструкция Code ссылается на имя переменной, версия, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение инструкции Code и наличие подходящих строк.</span><span class="sxs-lookup"><span data-stu-id="dac10-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="dac10-145">Это может увеличить риск обращения к непреднамеренной версии затененной переменной.</span><span class="sxs-lookup"><span data-stu-id="dac10-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="dac10-146">Можно снизить этот риск, полностью подполняя все ссылки на затененную переменную.</span><span class="sxs-lookup"><span data-stu-id="dac10-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="dac10-147">См. также</span><span class="sxs-lookup"><span data-stu-id="dac10-147">See also</span></span>

- [<span data-ttu-id="dac10-148">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="dac10-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="dac10-149">Затенение в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dac10-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="dac10-150">Различия между затемнением и переопределением</span><span class="sxs-lookup"><span data-stu-id="dac10-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="dac10-151">Практическое руководство. Сокрытие наследуемой переменной</span><span class="sxs-lookup"><span data-stu-id="dac10-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="dac10-152">Практическое руководство. Доступ к переменной, скрытой производным классом</span><span class="sxs-lookup"><span data-stu-id="dac10-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="dac10-153">Переопределения</span><span class="sxs-lookup"><span data-stu-id="dac10-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="dac10-154">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="dac10-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="dac10-155">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="dac10-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
