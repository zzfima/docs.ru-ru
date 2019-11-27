---
title: References to Declared Elements
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: a6477a9f0abaf8eb9176f4f6ab2a920af6c8f500
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345299"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="7e9ad-102">Ссылки на объявленные элементы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e9ad-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="7e9ad-103">Когда код ссылается на объявленный элемент, компилятор Visual Basic сопоставляет имя в ссылке с соответствующим объявлением этого имени.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="7e9ad-104">Если с одним и тем же именем объявлено несколько элементов, можно указать, к какому из этих элементов следует обращаться с помощью *уточнения* его имени.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="7e9ad-105">Компилятор пытается сопоставить ссылку на имя с объявлением имени с *самой короткой областью*.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="7e9ad-106">Это означает, что он начинается с кода, который делает ссылку и работает наружу через последовательные уровни содержащихся элементов.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="7e9ad-107">В следующем примере показаны ссылки на две переменные с одинаковым именем.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="7e9ad-108">В примере объявляются две переменные, каждая с именем `totalCount`, на разных уровнях области в `container`модуля.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="7e9ad-109">Если процедура `showCount` отображает `totalCount` без квалификации, компилятор Visual Basic разрешает ссылку на объявление с самой узкий областью, а именно локальное объявление в `showCount`.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="7e9ad-110">Когда он определяет `totalCount`, содержащий `container`модуля, компилятор разрешает ссылку на объявление с более широкой областью.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="7e9ad-111">Уточнение имени элемента</span><span class="sxs-lookup"><span data-stu-id="7e9ad-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="7e9ad-112">Если вы хотите переопределить этот процесс поиска и указать имя, объявленное в более широкой области видимости, необходимо *уточнить* имя с помощью содержащего его элемента из более широкой области.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="7e9ad-113">В некоторых случаях может также потребоваться квалификация содержащего его элемента.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="7e9ad-114">Уточнение имени означает, что перед ним в исходном операторе содержатся сведения, указывающие, где определен целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="7e9ad-115">Эти сведения называются *уточняющей строкой*.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="7e9ad-116">Он может включать одно или несколько пространств имен, а также модуль, класс или структуру.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="7e9ad-117">Уточняющая строка должна однозначно указывать модуль, класс или структуру, содержащую целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="7e9ad-118">Контейнер может находиться в другом содержащем его элементе, обычно в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="7e9ad-119">Может потребоваться включить несколько элементов, содержащихся в уточняющей строке.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="7e9ad-120">Получение доступа к объявленному элементу с помощью уточнения его имени</span><span class="sxs-lookup"><span data-stu-id="7e9ad-120">To access a declared element by qualifying its name</span></span>  
  
1. <span data-ttu-id="7e9ad-121">Определите расположение, в котором был определен элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="7e9ad-122">Это может быть пространство имен или даже иерархия пространств имен.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="7e9ad-123">В пространстве имен самого низкого уровня элемент должен содержаться в модуле, классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2. <span data-ttu-id="7e9ad-124">Определите классификационный путь на основе расположения целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="7e9ad-125">Начните с пространства имен наивысшего уровня, перейдите к пространству имен самого низкого уровня и завершите работу с модулем, классом или структурой, содержащей целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="7e9ad-126">Каждый элемент в пути должен содержать элемент, следующий за ним.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="7e9ad-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="7e9ad-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3. <span data-ttu-id="7e9ad-128">Подготовьте уточняющую строку для целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="7e9ad-129">Поместите точку (`.`) после каждого элемента в пути.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="7e9ad-130">Приложение должно иметь доступ к каждому элементу в уточняющей строке.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4. <span data-ttu-id="7e9ad-131">Напишите выражение или оператор присваивания, ссылающийся на целевой элемент обычным способом.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5. <span data-ttu-id="7e9ad-132">Перед именем целевого элемента введите уточняющую строку.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="7e9ad-133">Имя должно следовать за точкой (`.`) после модуля, класса или структуры, содержащей элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="7e9ad-134">Компилятор использует строку квалификации для поиска четкого однозначного объявления, к которому он может сопоставить ссылку на целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="7e9ad-135">Также может потребоваться уточнение ссылки на имя, если приложение имеет доступ к более чем одному элементу программирования с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="7e9ad-136">Например, пространства имен <xref:System.Windows.Forms> и <xref:System.Web.UI.WebControls> содержат класс `Label` (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> и <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="7e9ad-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="7e9ad-137">Если приложение использует оба объекта или определяет собственный класс `Label`, необходимо отличать разные объекты `Label`.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="7e9ad-138">Включите пространство имен или псевдоним импорта в объявление переменной.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="7e9ad-139">В следующем примере используется псевдоним Import.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="7e9ad-140">Члены других содержащих элементов</span><span class="sxs-lookup"><span data-stu-id="7e9ad-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="7e9ad-141">При использовании несовместного члена другого класса или структуры необходимо сначала уточнить имя члена с помощью переменной или выражения, указывающего на экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="7e9ad-142">В следующем примере `demoClass` является экземпляром класса с именем `class1`.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="7e9ad-143">Нельзя использовать имя класса для определения члена, который не является [общим](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="7e9ad-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="7e9ad-144">Сначала необходимо создать экземпляр в объектной переменной (в данном случае `demoClass`), а затем сослаться на него по имени переменной.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="7e9ad-145">Если класс или структура имеет элемент `Shared`, можно указать, что этот элемент имеет имя класса или структуры либо переменную или выражение, которое указывает на экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="7e9ad-146">Модуль не имеет отдельных экземпляров, и все его члены `Shared` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="7e9ad-147">Таким образом, для члена модуля необходимо указать имя модуля.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="7e9ad-148">В следующем примере показаны полные ссылки на процедуры членов модуля.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="7e9ad-149">В примере объявляются две `Sub` процедуры, как именованные `perform`, в разных модулях проекта.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="7e9ad-150">Каждый из них можно указать без квалификации в своем собственном модуле, но должен быть квалифицирован при ссылке из любого места.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="7e9ad-151">Поскольку последняя ссылка в `module3` не имеет квалификаторов `perform`, компилятор не может разрешить эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="7e9ad-152">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="7e9ad-152">References to Projects</span></span>  
 <span data-ttu-id="7e9ad-153">Чтобы использовать [открытые](../../../../visual-basic/language-reference/modifiers/public.md) элементы, определенные в другом проекте, необходимо сначала задать *ссылку* на сборку или библиотеку типов этого проекта.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="7e9ad-154">Чтобы задать ссылку, щелкните **Добавить ссылку** в меню **проект** или используйте параметр компилятора командной строки [-Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="7e9ad-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="7e9ad-155">Например, можно использовать объектную модель XML .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-155">For example, you can use the XML object model of the .NET Framework.</span></span> <span data-ttu-id="7e9ad-156">Если задать ссылку на пространство имен <xref:System.Xml>, можно объявить и использовать любой из его классов, например <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="7e9ad-157">В следующем примере используется <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="7e9ad-158">Импорт содержащих элементов</span><span class="sxs-lookup"><span data-stu-id="7e9ad-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="7e9ad-159">Для *импорта* пространств имен, содержащих модули или классы, которые необходимо использовать, можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) .</span><span class="sxs-lookup"><span data-stu-id="7e9ad-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="7e9ad-160">Это позволяет ссылаться на элементы, определенные в импортированном пространстве имен, без указания полных имен.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="7e9ad-161">В следующем примере показана перезапись предыдущего примера для импорта пространства имен <xref:System.Xml>.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="7e9ad-162">Кроме того, оператор `Imports` может определять *Псевдоним импорта* для каждого импортированного пространства имен.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="7e9ad-163">Это может сделать исходный код короче и проще в чтении.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="7e9ad-164">В следующем примере показана перезапись предыдущего примера для использования `xD` в качестве псевдонима для пространства имен <xref:System.Xml>.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="7e9ad-165">Инструкция `Imports` не делает элементы из других проектов доступными для приложения.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="7e9ad-166">Это значит, что не стоит устанавливать ссылку.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="7e9ad-167">При импорте пространства имен просто удаляются требования для уточнения имен, определенных в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="7e9ad-168">Можно также использовать инструкцию `Imports` для импорта модулей, классов, структур и перечислений.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="7e9ad-169">Затем можно использовать члены таких импортированных элементов без уточнения.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="7e9ad-170">Однако необходимо всегда уточнять несовместное использование членов классов и структур переменной или выражением, результатом которого является экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="7e9ad-171">Правила задания имен</span><span class="sxs-lookup"><span data-stu-id="7e9ad-171">Naming Guidelines</span></span>  
 <span data-ttu-id="7e9ad-172">При определении двух или более элементов программирования с одинаковыми именами может возникнуть *неоднозначность имени* , когда компилятор пытается разрешить ссылку на это имя.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="7e9ad-173">Если в области есть несколько определений или если определение не находится в области видимости, то используется ссылка неразрешимая.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="7e9ad-174">Пример см. на странице справки «пример с полными ссылками».</span><span class="sxs-lookup"><span data-stu-id="7e9ad-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="7e9ad-175">Неоднозначность имен можно избежать, присваивая всем элементам уникальные имена.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="7e9ad-176">Затем можно сделать ссылку на любой элемент, не указывая его имя с помощью пространства имен, модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="7e9ad-177">Кроме того, уменьшается вероятность случайной ссылки на неправильный элемент.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="7e9ad-178">Удаленное управление</span><span class="sxs-lookup"><span data-stu-id="7e9ad-178">Shadowing</span></span>  
 <span data-ttu-id="7e9ad-179">Если два программных элемента имеют одно и то же имя, один из них может скрыть или *затенить*другой.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="7e9ad-180">Затененный элемент недоступен для справки; Вместо этого, если в коде используется имя затененного элемента, компилятор Visual Basic разрешает его в элемент с тенью.</span><span class="sxs-lookup"><span data-stu-id="7e9ad-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="7e9ad-181">Более подробное объяснение с примерами см. [в разделе теневая поддержка в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="7e9ad-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9ad-182">См. также</span><span class="sxs-lookup"><span data-stu-id="7e9ad-182">See also</span></span>

- [<span data-ttu-id="7e9ad-183">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="7e9ad-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="7e9ad-184">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="7e9ad-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="7e9ad-185">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="7e9ad-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="7e9ad-186">Переменные</span><span class="sxs-lookup"><span data-stu-id="7e9ad-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="7e9ad-187">Оператор Imports (пространство имен и тип .NET)</span><span class="sxs-lookup"><span data-stu-id="7e9ad-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="7e9ad-188">Оператор New</span><span class="sxs-lookup"><span data-stu-id="7e9ad-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="7e9ad-189">Public</span><span class="sxs-lookup"><span data-stu-id="7e9ad-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
