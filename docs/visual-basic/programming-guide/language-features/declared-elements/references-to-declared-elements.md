---
title: Ссылки на объявленные элементы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 16f4fb28ab030ccebed2a8d1b93a3a6c29d075c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501260"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="070f0-102">Ссылки на объявленные элементы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="070f0-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="070f0-103">Когда код ссылается на объявленный элемент, компилятор Visual Basic совпадает с именем в ссылке соответствующий объявлению.</span><span class="sxs-lookup"><span data-stu-id="070f0-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="070f0-104">Если более чем один элемент объявлен с тем же именем, вы можете контролировать, какие из этих элементов — на них ссылается *удовлетворяющим требованиям* его имя.</span><span class="sxs-lookup"><span data-stu-id="070f0-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="070f0-105">Компилятор пытается сопоставить ссылку имени с объявлением с *наиболее узкой области*.</span><span class="sxs-lookup"><span data-stu-id="070f0-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="070f0-106">Это означает, что он начинается с кода, делая ссылку и работая через последовательные уровни, содержащего элементы.</span><span class="sxs-lookup"><span data-stu-id="070f0-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="070f0-107">Пример ссылки на две переменные с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="070f0-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="070f0-108">В примере объявляются две переменные, каждая с именем `totalCount`, на разных уровнях области в модуле `container`.</span><span class="sxs-lookup"><span data-stu-id="070f0-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="070f0-109">Когда процедура `showCount` отображает `totalCount` без квалификации, компилятор Visual Basic разрешает ссылку на объявление с самой узкой областью, а именно: локальное объявление внутри `showCount`.</span><span class="sxs-lookup"><span data-stu-id="070f0-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="070f0-110">При уточнении `totalCount` с содержащим модулем `container`, компилятор разрешает ссылку на объявление с более широкой областью.</span><span class="sxs-lookup"><span data-stu-id="070f0-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="070f0-111">Уточнение имени элемента</span><span class="sxs-lookup"><span data-stu-id="070f0-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="070f0-112">Если вы хотите переопределить этот процесс поиска и укажите имя, объявленное в более широкую область необходимо *квалифицировать* имя с содержащим элементом более широкой области.</span><span class="sxs-lookup"><span data-stu-id="070f0-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="070f0-113">В некоторых случаях может потребоваться уточнять содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="070f0-114">Уточнение имени означает, что предшествует ей в исходном операторе сведения, которые определяют, где определен целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="070f0-115">Эта информация называется *уточняющей строке*.</span><span class="sxs-lookup"><span data-stu-id="070f0-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="070f0-116">Она может включать одно или несколько пространств имен и модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="070f0-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="070f0-117">Строка квалификации должна однозначно указать модуль, класс или структура, содержащая целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="070f0-118">Контейнер, в свою очередь могут находиться в другой содержащий элемент, обычно в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="070f0-119">Может потребоваться включить несколько элементов в уточняющей строке.</span><span class="sxs-lookup"><span data-stu-id="070f0-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="070f0-120">Для доступа к объявленного элемента, указав его имя</span><span class="sxs-lookup"><span data-stu-id="070f0-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="070f0-121">Определите расположение, в котором был определен элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="070f0-122">Это может включать пространство имен или даже иерархии пространств имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="070f0-123">В пространстве имен самого низкого уровня элемент должен содержаться в модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="070f0-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="070f0-124">Определите путь квалификации, в зависимости от расположения целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="070f0-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="070f0-125">Начнем с самого верхнего уровня пространства имен, перейдите к пространству имен самого низкого уровня и заканчиваться модуль, класс или структура, содержащая целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="070f0-126">Каждый элемент в пути должен содержать элемент, следующий за ним.</span><span class="sxs-lookup"><span data-stu-id="070f0-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="070f0-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="070f0-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="070f0-128">Подготовка уточняющей строки для целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="070f0-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="070f0-129">Поместите точку (`.`) после каждого элемента в пути.</span><span class="sxs-lookup"><span data-stu-id="070f0-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="070f0-130">Приложение должно иметь доступ к каждому элементу уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="070f0-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="070f0-131">Напишите выражение или оператор присваивания, ссылающийся на целевой элемент обычным способом.</span><span class="sxs-lookup"><span data-stu-id="070f0-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="070f0-132">Перед именем целевой элемент в уточняющей строке.</span><span class="sxs-lookup"><span data-stu-id="070f0-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="070f0-133">Имя должно следовать сразу за период (`.`), который следует за модуля, класса или структуры, которая содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="070f0-134">Компилятор использует уточняющей строке, чтобы найти точное, однозначное объявление, к которому она может соответствовать ссылку на целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="070f0-135">Кроме того, может потребоваться уточнять ссылки на имена, если приложение имеет доступ к более одного элемента программирования, который имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="070f0-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="070f0-136">Например <xref:System.Windows.Forms> и <xref:System.Web.UI.WebControls> пространства имен оба содержат `Label` класс (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="070f0-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="070f0-137">Если приложение использует оба или определяет собственный `Label` класса, необходимо различать разные `Label` объектов.</span><span class="sxs-lookup"><span data-stu-id="070f0-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="070f0-138">Включите пространство имен или псевдоним в объявлении переменной.</span><span class="sxs-lookup"><span data-stu-id="070f0-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="070f0-139">В следующем примере используется псевдоним импорта.</span><span class="sxs-lookup"><span data-stu-id="070f0-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="070f0-140">Членами других элементов с содержимым</span><span class="sxs-lookup"><span data-stu-id="070f0-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="070f0-141">При использовании члену другого класса или структуры, сначала необходимо уточнить имя члена с помощью переменной или выражение, которое указывает на экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="070f0-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="070f0-142">В следующем примере `demoClass` является экземпляром класса с именем `class1`.</span><span class="sxs-lookup"><span data-stu-id="070f0-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="070f0-143">Нельзя использовать имя самого класса для уточнения члена, не [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="070f0-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="070f0-144">Во-первых, необходимо создать экземпляр в переменной объекта (в данном случае `demoClass`) и затем ссылаться на него по имени этой переменной.</span><span class="sxs-lookup"><span data-stu-id="070f0-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="070f0-145">Если класс или структура имеет `Shared` член, можно уточнить этот член с именем класса или структуры, переменной или выражение, которое указывает на экземпляр.</span><span class="sxs-lookup"><span data-stu-id="070f0-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="070f0-146">Модуль имеет все отдельные экземпляры, и все его члены являются `Shared` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="070f0-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="070f0-147">Таким образом вы уточнения члена модуля с именем модуля.</span><span class="sxs-lookup"><span data-stu-id="070f0-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="070f0-148">В следующем примере полные ссылки на процедуры члена модуля.</span><span class="sxs-lookup"><span data-stu-id="070f0-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="070f0-149">В этом примере объявляется два `Sub` процедуры, и именованные `perform`, в разных модулях в проекте.</span><span class="sxs-lookup"><span data-stu-id="070f0-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="070f0-150">Каждая из них можно указывать без уточнения внутри свой собственный модуль, но должен быть определен, если ссылка в других местах.</span><span class="sxs-lookup"><span data-stu-id="070f0-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="070f0-151">Так как последняя ссылка в `module3` неприменима `perform`, компилятор не может разрешить эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="070f0-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="070f0-152">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="070f0-152">References to Projects</span></span>  
 <span data-ttu-id="070f0-153">Для использования [открытый](../../../../visual-basic/language-reference/modifiers/public.md) элементов, определенных в другом проекте, необходимо сначала установить *ссылку* для этого проекта сборки или библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="070f0-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="070f0-154">Чтобы задать ссылку, щелкните **добавить ссылку** на **проекта** меню или используйте [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр командной строки компилятора.</span><span class="sxs-lookup"><span data-stu-id="070f0-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="070f0-155">Например, можно использовать объектную модель XML [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="070f0-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="070f0-156">Если задать ссылку на <xref:System.Xml> пространства имен, можно объявить и использовать любой из его классы, такие как <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="070f0-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="070f0-157">В следующем примере используется <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="070f0-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="070f0-158">Импорт элементов</span><span class="sxs-lookup"><span data-stu-id="070f0-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="070f0-159">Можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для *импорта* пространства имен, содержащих модули или классы, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="070f0-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="070f0-160">Это позволяет ссылаться на элементы, определенные в импортированное пространство имен без полных имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="070f0-161">Следующий пример перезаписывает предыдущий пример для импорта <xref:System.Xml> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="070f0-162">Кроме того `Imports` можно определить оператор *псевдоним импорта* для каждого импортируемого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="070f0-163">Это может сделать исходный код короче и удобнее для чтения.</span><span class="sxs-lookup"><span data-stu-id="070f0-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="070f0-164">Следующий пример перезаписывает предыдущий пример для использования `xD` в качестве псевдонима для <xref:System.Xml> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="070f0-165">`Imports` Инструкция не выполняет элементы из других проектов доступными для приложения.</span><span class="sxs-lookup"><span data-stu-id="070f0-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="070f0-166">То есть он не замещать ссылку.</span><span class="sxs-lookup"><span data-stu-id="070f0-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="070f0-167">Импорт пространства имен просто удаляет требование для уточнения имен, определенных в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="070f0-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="070f0-168">Можно также использовать `Imports` для импорта модулей, классов, структур и перечислений.</span><span class="sxs-lookup"><span data-stu-id="070f0-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="070f0-169">Затем можно использовать члены импортированных элементов без указания полного имени.</span><span class="sxs-lookup"><span data-stu-id="070f0-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="070f0-170">Тем не менее всегда необходимо определять членам экземпляров классов и структур с переменной или выражение, значением которого является экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="070f0-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="070f0-171">Правила именования</span><span class="sxs-lookup"><span data-stu-id="070f0-171">Naming Guidelines</span></span>  
 <span data-ttu-id="070f0-172">При определении два или несколько программных элементов, которые имеют одинаковое имя, *неоднозначность имен* может привести к Если компилятор пытается разрешить ссылку на это имя.</span><span class="sxs-lookup"><span data-stu-id="070f0-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="070f0-173">Если более одного определения находится в области, или если определение не находится в области, ссылка является неразрешимой.</span><span class="sxs-lookup"><span data-stu-id="070f0-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="070f0-174">Например см. в разделе «Пример уточненной ссылки» на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="070f0-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="070f0-175">Неоднозначность имен можно избежать, предоставляя уникальные имена всех элементов.</span><span class="sxs-lookup"><span data-stu-id="070f0-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="070f0-176">Затем можно создать ссылку к любому элементу без уточнения его именем пространства имен, модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="070f0-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="070f0-177">Вы также снизить вероятность случайной ссылки на неправильный элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="070f0-178">Затенение</span><span class="sxs-lookup"><span data-stu-id="070f0-178">Shadowing</span></span>  
 <span data-ttu-id="070f0-179">Если два программных элемента имеют одинаковые имена, один из них может скрыть, или *тени*, другой.</span><span class="sxs-lookup"><span data-stu-id="070f0-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="070f0-180">Скрытый элемент недоступен для обращения. Вместо этого когда код использует затененного имени элемента, компилятор Visual Basic разрешает его скрывающий элемент.</span><span class="sxs-lookup"><span data-stu-id="070f0-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="070f0-181">Более подробное описание с примерами, см. в разделе [сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="070f0-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="070f0-182">См. также</span><span class="sxs-lookup"><span data-stu-id="070f0-182">See also</span></span>
- [<span data-ttu-id="070f0-183">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="070f0-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="070f0-184">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="070f0-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="070f0-185">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="070f0-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="070f0-186">Переменные</span><span class="sxs-lookup"><span data-stu-id="070f0-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="070f0-187">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="070f0-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="070f0-188">Оператор New</span><span class="sxs-lookup"><span data-stu-id="070f0-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="070f0-189">Public</span><span class="sxs-lookup"><span data-stu-id="070f0-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
