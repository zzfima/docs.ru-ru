---
title: "Передача структур"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab9002d6e86b91f0ed21dae41f82af31f04291c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-structures"></a><span data-ttu-id="65ea3-102">Передача структур</span><span class="sxs-lookup"><span data-stu-id="65ea3-102">Passing Structures</span></span>
<span data-ttu-id="65ea3-103">В качестве параметров во многие неуправляемые функции должны передаваться члены, структуры (определяемые пользователем типы в Visual Basic) или члены классов, которые определяются в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="65ea3-103">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="65ea3-104">При передаче структур или классов в неуправляемый код посредством вызовов неуправляемого кода необходимо указать дополнительную информацию для сохранения исходного размещения и выравнивания.</span><span class="sxs-lookup"><span data-stu-id="65ea3-104">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="65ea3-105">В этом разделе описывается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, который используется для определения форматированных типов.</span><span class="sxs-lookup"><span data-stu-id="65ea3-105">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="65ea3-106">Для управляемых структур и классов можно выбрать любое из нескольких предсказуемых поведений размещения в перечислении **LayoutKind**.</span><span class="sxs-lookup"><span data-stu-id="65ea3-106">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="65ea3-107">Представленные в этом разделе понятия приводятся с учетом важного различия между структурами и типами классов.</span><span class="sxs-lookup"><span data-stu-id="65ea3-107">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="65ea3-108">Структуры представляют собой типы значений, а классы — ссылочные типы. В классах всегда реализуется как минимум один уровень косвенного обращения к памяти (указатель на значение).</span><span class="sxs-lookup"><span data-stu-id="65ea3-108">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="65ea3-109">Это важное отличие, поскольку неуправляемые функции часто используют косвенное обращение, как показано в сигнатурах в первом столбце в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="65ea3-109">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="65ea3-110">Управляемые структуры и объявления классов в оставшихся столбцах демонстрируют, в какой степени можно изменить уровень косвенного обращения в объявлении. Объявления предоставляются как для Visual Basic, так и для Visual C#.</span><span class="sxs-lookup"><span data-stu-id="65ea3-110">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="65ea3-111">Неуправляемая сигнатура</span><span class="sxs-lookup"><span data-stu-id="65ea3-111">Unmanaged signature</span></span>|<span data-ttu-id="65ea3-112">Управляемое объявление:</span><span class="sxs-lookup"><span data-stu-id="65ea3-112">Managed declaration:</span></span> <br /><span data-ttu-id="65ea3-113">без косвенного обращения</span><span class="sxs-lookup"><span data-stu-id="65ea3-113">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="65ea3-114">Управляемое объявление:</span><span class="sxs-lookup"><span data-stu-id="65ea3-114">Managed declaration:</span></span> <br /><span data-ttu-id="65ea3-115">один уровень косвенного обращения</span><span class="sxs-lookup"><span data-stu-id="65ea3-115">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="65ea3-116">Требуется ноль уровней косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-116">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="65ea3-117">Добавляет ноль уровней косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-117">Adds zero levels of indirection.</span></span>|<span data-ttu-id="65ea3-118">Невозможно, поскольку один уровень косвенного обращения уже существует.</span><span class="sxs-lookup"><span data-stu-id="65ea3-118">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="65ea3-119">Требуется один уровень косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-119">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="65ea3-120">Добавляет один уровень косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-120">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="65ea3-121">Добавляет ноль уровней косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-121">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="65ea3-122">Требуется два уровня косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-122">Demands two levels of indirection.</span></span>|<span data-ttu-id="65ea3-123">Невозможно, поскольку нельзя использовать **ByRef** **ByRef** или `ref` `ref`.</span><span class="sxs-lookup"><span data-stu-id="65ea3-123">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="65ea3-124">Добавляет один уровень косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-124">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="65ea3-125">В этой таблице описываются следующие рекомендации по объявлению вызовов неуправляемого кода:</span><span class="sxs-lookup"><span data-stu-id="65ea3-125">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
-   <span data-ttu-id="65ea3-126">Если неуправляемая функция не требует косвенного обращения, используйте структуру, передаваемую по значению.</span><span class="sxs-lookup"><span data-stu-id="65ea3-126">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
-   <span data-ttu-id="65ea3-127">Если неуправляемая функция требует один уровень косвенного обращения, используйте передаваемую по ссылке структуру или передаваемый по значению класс.</span><span class="sxs-lookup"><span data-stu-id="65ea3-127">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
-   <span data-ttu-id="65ea3-128">Если неуправляемая функция требует два уровня косвенного обращения, используйте класс, передаваемый по ссылке.</span><span class="sxs-lookup"><span data-stu-id="65ea3-128">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="65ea3-129">Объявление и передача структур</span><span class="sxs-lookup"><span data-stu-id="65ea3-129">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="65ea3-130">В следующем примере демонстрируется, как определить структуры `Point` и `Rect` в управляемом коде и передать типы в качестве параметров в функцию **PtInRect** в файле User32.dll.</span><span class="sxs-lookup"><span data-stu-id="65ea3-130">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="65ea3-131">Функция **PtInRect** имеет следующую неуправляемую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="65ea3-131">**PtInRect** has the following unmanaged signature:</span></span>  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="65ea3-132">Обратите внимание, что структуру Rect необходимо передавать по ссылке, поскольку функция принимает указатель на тип RECT.</span><span class="sxs-lookup"><span data-stu-id="65ea3-132">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="65ea3-133">Объявление и передача классов</span><span class="sxs-lookup"><span data-stu-id="65ea3-133">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="65ea3-134">Члены класса можно передавать в неуправляемую функцию DLL при условии, что класс имеет фиксированное размещение членов.</span><span class="sxs-lookup"><span data-stu-id="65ea3-134">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="65ea3-135">В следующем примере демонстрируется, как передать члены класса `MySystemTime`, которые определяются последовательно, в функцию **GetSystemTime** в файле User32.dll.</span><span class="sxs-lookup"><span data-stu-id="65ea3-135">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="65ea3-136">Функция **GetSystemTime** имеет следующую неуправляемую сигнатуру:</span><span class="sxs-lookup"><span data-stu-id="65ea3-136">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="65ea3-137">В отличие от типов значений, классы всегда имеют как минимум один уровень косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="65ea3-137">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="65ea3-138">См. также</span><span class="sxs-lookup"><span data-stu-id="65ea3-138">See Also</span></span>  
 [<span data-ttu-id="65ea3-139">Вызов функции DLL</span><span class="sxs-lookup"><span data-stu-id="65ea3-139">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
