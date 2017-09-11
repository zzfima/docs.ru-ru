---
title: "Ссылки на объявленные элементы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements
- references, declared elements
- qualified names
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5de39ac5c30b1cff2a8bfd0cd606dee33c078514
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="8066e-102">Ссылки на объявленные элементы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8066e-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="8066e-103">Когда код ссылается на объявленный элемент [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятора соответствует имени в ссылке соответствующему объявлению этого имени.</span><span class="sxs-lookup"><span data-stu-id="8066e-103">When your code refers to a declared element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="8066e-104">Если более чем один элемент объявлен с тем же именем, можно выбрать, какие из этих элементов должен ссылаться на *соответствующая* его имя.</span><span class="sxs-lookup"><span data-stu-id="8066e-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="8066e-105">Компилятор пытается сопоставить ссылку имени с объявлением с *узкой области*.</span><span class="sxs-lookup"><span data-stu-id="8066e-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="8066e-106">Это означает, что он начинается с кода, делая ссылку и работая через последовательные уровни содержащих элементов.</span><span class="sxs-lookup"><span data-stu-id="8066e-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="8066e-107">В следующем примере показаны ссылки на две переменные с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="8066e-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="8066e-108">В примере объявляются две переменные, каждая с именем `totalCount`, на различных уровнях области в модуле `container`.</span><span class="sxs-lookup"><span data-stu-id="8066e-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="8066e-109">Если процедура `showCount` отображает `totalCount` без квалификации, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор разрешает ссылку на объявление с самой узкой областью, а именно, локальное объявление внутри `showCount`.</span><span class="sxs-lookup"><span data-stu-id="8066e-109">When the procedure `showCount` displays `totalCount` without qualification, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="8066e-110">При уточнении `totalCount` с содержащим модулем `container`, компилятор разрешает ссылку на объявление с более широкой областью.</span><span class="sxs-lookup"><span data-stu-id="8066e-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="8066e-111">Уточнение имени элемента</span><span class="sxs-lookup"><span data-stu-id="8066e-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="8066e-112">Если требуется переопределить этот процесс поиска и задать имя, объявленное в более широкой области, необходимо *уточнения* имя содержащим элементом более широкой области.</span><span class="sxs-lookup"><span data-stu-id="8066e-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="8066e-113">В некоторых случаях может потребоваться уточнять содержащий элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="8066e-114">Уточнение имени означает предшествующего ему в исходном операторе сведения, определяющие, где определен целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="8066e-115">Эта информация называется *уточняющую строку*.</span><span class="sxs-lookup"><span data-stu-id="8066e-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="8066e-116">Она может включать одно или несколько пространств имен и модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8066e-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="8066e-117">Строка квалификации должна однозначно указать модуль, класс или структура, содержащая целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8066e-118">Контейнер, в свою очередь может находиться в другом вмещающем элементе, обычно в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8066e-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="8066e-119">Может потребоваться включить несколько элементов в уточняющую строку.</span><span class="sxs-lookup"><span data-stu-id="8066e-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="8066e-120">Чтобы получить доступ к объявленным элементом, указав его имя</span><span class="sxs-lookup"><span data-stu-id="8066e-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="8066e-121">Определите расположение, в котором был определен элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="8066e-122">Это может включать пространство имен или даже иерархии пространств имен.</span><span class="sxs-lookup"><span data-stu-id="8066e-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="8066e-123">В пространстве имен нижнего уровня элемент должен содержаться в модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8066e-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2.  <span data-ttu-id="8066e-124">Определите классификационный путь на основе расположения целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="8066e-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="8066e-125">Начнем с пространство имен верхнего уровня, перейдите к пространству имен самого низкого уровня и заканчиваться модуля, класса или структуры, содержащей целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="8066e-126">Каждый элемент пути должен содержать элемент, следующий за ним.</span><span class="sxs-lookup"><span data-stu-id="8066e-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="8066e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="8066e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="8066e-128">Подготовка уточняющей строки для целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="8066e-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="8066e-129">Поместите точку (`.`) после каждого элемента пути.</span><span class="sxs-lookup"><span data-stu-id="8066e-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="8066e-130">Приложение должно иметь доступ к каждому элементу уточняющей строки.</span><span class="sxs-lookup"><span data-stu-id="8066e-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="8066e-131">Напишите выражение или оператор присваивания, ссылающийся на конечный элемент обычным образом.</span><span class="sxs-lookup"><span data-stu-id="8066e-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="8066e-132">Перед именем целевого элемента уточняющую строку.</span><span class="sxs-lookup"><span data-stu-id="8066e-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="8066e-133">Имя должна стоять точка (`.`), который следует за модуля, класса или структуры, которая содержит элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="8066e-134">Компилятор использует уточняющую строку, чтобы найти точное, однозначное объявление, к которому может сопоставить ссылку на целевой элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="8066e-135">Может также потребоваться уточнять ссылки на имена, если приложение имеет доступ к более чем один элемент программирования, который имеет то же имя.</span><span class="sxs-lookup"><span data-stu-id="8066e-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="8066e-136">Например <xref:System.Windows.Forms>и <xref:System.Web.UI.WebControls>пространства имен содержат `Label` класса (<xref:System.Windows.Forms.Label?displayProperty=fullName> и <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</xref:System.Web.UI.WebControls.Label?displayProperty=fullName> </xref:System.Windows.Forms.Label?displayProperty=fullName> </xref:System.Web.UI.WebControls> </xref:System.Windows.Forms></span><span class="sxs-lookup"><span data-stu-id="8066e-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=fullName> and <xref:System.Web.UI.WebControls.Label?displayProperty=fullName>).</span></span> <span data-ttu-id="8066e-137">Если приложение использует оба или определяет собственный `Label` класса, необходимо различать разные `Label` объектов.</span><span class="sxs-lookup"><span data-stu-id="8066e-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="8066e-138">Включите пространство имен или псевдоним в объявлении переменной.</span><span class="sxs-lookup"><span data-stu-id="8066e-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="8066e-139">В следующем примере псевдоним импорта.</span><span class="sxs-lookup"><span data-stu-id="8066e-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="8066e-140">Члены других содержащих элементов</span><span class="sxs-lookup"><span data-stu-id="8066e-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="8066e-141">При использовании не совместно членом другого класса или структуры нужно сначала уточнить имя члена с помощью переменной или выражения, указывающего на экземпляр класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8066e-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="8066e-142">В следующем примере `demoClass` представляет собой экземпляр класса с именем `class1`.</span><span class="sxs-lookup"><span data-stu-id="8066e-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="8066e-143">Нельзя использовать имя самого класса для уточнения члена, который не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8066e-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="8066e-144">Необходимо сначала создать экземпляр в переменной объекта (в данном случае `demoClass`) и затем сослаться на него, используя имя переменной.</span><span class="sxs-lookup"><span data-stu-id="8066e-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="8066e-145">Если класс или структура имеет `Shared` член, уточнить этот член именем класса или структуры, переменной или выражение, которое указывает на экземпляр.</span><span class="sxs-lookup"><span data-stu-id="8066e-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="8066e-146">Модуль имеет любой отдельных экземпляров, и все его члены являются `Shared` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8066e-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="8066e-147">Таким образом уточняется член модуля с именем модуля.</span><span class="sxs-lookup"><span data-stu-id="8066e-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="8066e-148">В следующем примере полные ссылки на процедуры члена модуля.</span><span class="sxs-lookup"><span data-stu-id="8066e-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="8066e-149">В примере объявляются две `Sub` процедуры, обе с именем `perform`, в разных модулях проекта.</span><span class="sxs-lookup"><span data-stu-id="8066e-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="8066e-150">Каждая из них можно указывать без уточнения внутри собственный модуль, но должно быть уточнено обращения из других мест.</span><span class="sxs-lookup"><span data-stu-id="8066e-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="8066e-151">Так как последняя ссылка в `module3` неприменима `perform`, компилятор не может разрешить эту ссылку.</span><span class="sxs-lookup"><span data-stu-id="8066e-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="8066e-152">Ссылки на проекты</span><span class="sxs-lookup"><span data-stu-id="8066e-152">References to Projects</span></span>  
 <span data-ttu-id="8066e-153">Для использования [открытый](../../../../visual-basic/language-reference/modifiers/public.md) элементов, определенных в другом проекте, необходимо сначала установить *ссылки* для этого проекта сборку или библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="8066e-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="8066e-154">Чтобы установить ссылку, нажмите кнопку **добавить ссылку** на **проекта** меню или используйте [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр командной строки компилятора.</span><span class="sxs-lookup"><span data-stu-id="8066e-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="8066e-155">Например, можно использовать объектную модель XML из [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="8066e-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="8066e-156">Если задать ссылку на <xref:System.Xml>пространства имен, можно объявить и использовать все его классы, такие как <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> </xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="8066e-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="8066e-157">В следующем примере используется <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument></span><span class="sxs-lookup"><span data-stu-id="8066e-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="8066e-158">Импорт содержащих элементов</span><span class="sxs-lookup"><span data-stu-id="8066e-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="8066e-159">Можно использовать [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для *импорта* пространства имен, содержащих модули или классы, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="8066e-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="8066e-160">Это позволяет ссылаться на элементы, определенные в импортированном пространстве имен без полных имен.</span><span class="sxs-lookup"><span data-stu-id="8066e-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="8066e-161">Следующий пример перезаписывает предыдущий пример для импорта <xref:System.Xml>имен.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="8066e-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="8066e-162">Кроме того `Imports` можно определить оператор *псевдоним импорта* для каждого импортируемого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8066e-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="8066e-163">Это может сделать исходный код короче и удобнее для чтения.</span><span class="sxs-lookup"><span data-stu-id="8066e-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="8066e-164">Следующий пример перезаписывает предыдущий пример для использования `xD` в качестве псевдонима для <xref:System.Xml>имен.</xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="8066e-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="8066e-165">`Imports` Инструкция не делает элементы из других проектов доступными для приложения.</span><span class="sxs-lookup"><span data-stu-id="8066e-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="8066e-166">То есть он не замещать ссылку.</span><span class="sxs-lookup"><span data-stu-id="8066e-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="8066e-167">Импорт пространства имен просто освобождает от необходимости уточнения имен, определенных в этом пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="8066e-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="8066e-168">Можно также использовать `Imports` для импорта модулей, классов, структур и перечислений.</span><span class="sxs-lookup"><span data-stu-id="8066e-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="8066e-169">Затем можно использовать члены импортированных элементов без уточнения.</span><span class="sxs-lookup"><span data-stu-id="8066e-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="8066e-170">Тем не менее всегда необходимо предварять собственным членам классов и структур с помощью переменной или выражение, результатом которого является экземпляром класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8066e-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="8066e-171">Правила именования</span><span class="sxs-lookup"><span data-stu-id="8066e-171">Naming Guidelines</span></span>  
 <span data-ttu-id="8066e-172">При определении двух или более элементов программирования, которые имеют одинаковое имя, *неоднозначность имен* может привести к когда компилятор пытается разрешить ссылку на это имя.</span><span class="sxs-lookup"><span data-stu-id="8066e-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="8066e-173">Если более одного определения находится в области, или если определение отсутствует в области, ссылка является неразрешимой.</span><span class="sxs-lookup"><span data-stu-id="8066e-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="8066e-174">Пример в разделе «Полное пример ссылки» на этой странице справки.</span><span class="sxs-lookup"><span data-stu-id="8066e-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="8066e-175">Неоднозначность имен можно избежать, присвоив уникальные имена всех элементов.</span><span class="sxs-lookup"><span data-stu-id="8066e-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="8066e-176">Затем можно сделать ссылку на любой элемент без уточнения его имени пространства имен, модуля или класса.</span><span class="sxs-lookup"><span data-stu-id="8066e-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="8066e-177">Можно также снизить вероятность случайной ссылки на неправильный элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="8066e-178">Затенение</span><span class="sxs-lookup"><span data-stu-id="8066e-178">Shadowing</span></span>  
 <span data-ttu-id="8066e-179">Если два программных элемента имеют общее имя, один из них может скрыть, или *тени*, другой.</span><span class="sxs-lookup"><span data-stu-id="8066e-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="8066e-180">Затененный элемент недоступен для обращения. Вместо этого в том случае, если ваш код использует затененного имени элемента, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор разрешает его переопределяющий элемент.</span><span class="sxs-lookup"><span data-stu-id="8066e-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="8066e-181">Более подробное описание с примерами см. в разделе [сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="8066e-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8066e-182">См. также</span><span class="sxs-lookup"><span data-stu-id="8066e-182">See Also</span></span>  
 <span data-ttu-id="8066e-183">[Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="8066e-183">[Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="8066e-184"> [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="8066e-184"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="8066e-185"> [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="8066e-185"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="8066e-186"> [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="8066e-186"> [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="8066e-187"> [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="8066e-187"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="8066e-188"> [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8066e-188"> [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) </span></span>  
<span data-ttu-id="8066e-189"> [Public](../../../../visual-basic/language-reference/modifiers/public.md)</span><span class="sxs-lookup"><span data-stu-id="8066e-189"> [Public](../../../../visual-basic/language-reference/modifiers/public.md)</span></span>
