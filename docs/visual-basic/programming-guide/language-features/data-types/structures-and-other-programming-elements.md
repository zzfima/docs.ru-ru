---
title: Структуры и другие элементы программирования (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: ed406254435602dcd98bc97716cc88710a470ed1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679595"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="875a6-102">Структуры и другие элементы программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="875a6-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="875a6-103">Структуры можно использовать в сочетании с массивы, объекты и процедуры, а также друг с другом.</span><span class="sxs-lookup"><span data-stu-id="875a6-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="875a6-104">При взаимодействии применяется тот же синтаксис, который используется эти элементы по отдельности.</span><span class="sxs-lookup"><span data-stu-id="875a6-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="875a6-105">Вы не можете инициализировать любого из элементов структуры в объявлении структуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="875a6-106">Можно назначить значения только элементы переменной, который был объявлен как тип структуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="875a6-107">Структуры и массивы</span><span class="sxs-lookup"><span data-stu-id="875a6-107">Structures and Arrays</span></span>  
 <span data-ttu-id="875a6-108">Структура может содержать массив как один или несколько его элементов.</span><span class="sxs-lookup"><span data-stu-id="875a6-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="875a6-109">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 <span data-ttu-id="875a6-110">Доступ к значениям массива в структуре так же, доступе к свойству объекта.</span><span class="sxs-lookup"><span data-stu-id="875a6-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="875a6-111">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="875a6-112">Можно также объявить массив структур.</span><span class="sxs-lookup"><span data-stu-id="875a6-112">You can also declare an array of structures.</span></span> <span data-ttu-id="875a6-113">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="875a6-114">Вы выполните те же правила, доступ к компонентам этой архитектуры данных.</span><span class="sxs-lookup"><span data-stu-id="875a6-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="875a6-115">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="875a6-116">Структуры и объекты</span><span class="sxs-lookup"><span data-stu-id="875a6-116">Structures and Objects</span></span>  
 <span data-ttu-id="875a6-117">Структура может содержать объект как один или несколько его элементов.</span><span class="sxs-lookup"><span data-stu-id="875a6-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="875a6-118">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="875a6-119">В таком объявлении следует использовать определенный класс объекта вместо `Object`.</span><span class="sxs-lookup"><span data-stu-id="875a6-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="875a6-120">Структуры и процедуры</span><span class="sxs-lookup"><span data-stu-id="875a6-120">Structures and Procedures</span></span>  
 <span data-ttu-id="875a6-121">Можно передать структуру в качестве аргумента процедуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="875a6-122">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="875a6-123">В предыдущем примере передается структура *по ссылке*, что позволяет изменять его элементы, чтобы изменения вступили в силу в вызывающем коде процедуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="875a6-124">Если вы хотите защитить структуру от таких изменений, ее необходимо передайте по значению.</span><span class="sxs-lookup"><span data-stu-id="875a6-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="875a6-125">Можно также вернуть структуру из `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="875a6-126">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-126">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a><span data-ttu-id="875a6-127">Структуры внутри структур</span><span class="sxs-lookup"><span data-stu-id="875a6-127">Structures Within Structures</span></span>  
 <span data-ttu-id="875a6-128">Структуры могут содержать другие структуры.</span><span class="sxs-lookup"><span data-stu-id="875a6-128">Structures can contain other structures.</span></span> <span data-ttu-id="875a6-129">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="875a6-129">The following example illustrates this.</span></span>  
  
```vb  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 <span data-ttu-id="875a6-130">Этот метод может использоваться для инкапсуляции структуре, определенной в одном модуле в структуре, определенной в другом модуле.</span><span class="sxs-lookup"><span data-stu-id="875a6-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="875a6-131">Структуры могут содержать другие структуры в произвольном порядке.</span><span class="sxs-lookup"><span data-stu-id="875a6-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="875a6-132">См. также</span><span class="sxs-lookup"><span data-stu-id="875a6-132">See also</span></span>
- [<span data-ttu-id="875a6-133">Типы данных</span><span class="sxs-lookup"><span data-stu-id="875a6-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="875a6-134">Простые типы данных</span><span class="sxs-lookup"><span data-stu-id="875a6-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="875a6-135">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="875a6-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="875a6-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="875a6-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="875a6-137">Структуры</span><span class="sxs-lookup"><span data-stu-id="875a6-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="875a6-138">Устранение неполадок, связанных с типами данных</span><span class="sxs-lookup"><span data-stu-id="875a6-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="875a6-139">Практическое руководство. Объявление структуры</span><span class="sxs-lookup"><span data-stu-id="875a6-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="875a6-140">Переменные структуры</span><span class="sxs-lookup"><span data-stu-id="875a6-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="875a6-141">Структуры и классы</span><span class="sxs-lookup"><span data-stu-id="875a6-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="875a6-142">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="875a6-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
