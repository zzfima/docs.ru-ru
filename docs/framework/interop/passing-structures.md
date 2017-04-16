---
title: "Passing Structures | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "platform invoke, calling unmanaged functions"
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Passing Structures
Для многих неуправляемых функций в качестве параметра должны быть переданы члены структур \(в Visual Basic это определяемые пользователем типы\) или члены классов, определяемые в управляемом коде программы.  Для сохранения исходного размещения и выравнивания при передаче структур или классов в неуправляемый код необходимо предоставить дополнительные сведения при вызове неуправляемого кода.  В этом разделе описывается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, который можно использовать для определения форматированных типов.  Для управляемых структур и классов можно выбрать одно из стандартных размещений, предоставленных перечислением **LayoutKind**.  
  
 Важнейшим из понятий, описанных в этом разделе, является существенное различие между структурами и классами как типами.  Структуры представляют собой типы значений, а классы —ссылочные типы, которые всегда обеспечивают, по крайней мере, один уровень косвенного обращения к памяти \(указатель на значение\).  Это различие очень важно, так как неуправляемые функции часто требуют косвенного обращения, что видно из примеров сигнатур в первом столбце следующей таблицы.  Объявления управляемых структур и классов в остальных столбцах показывают, насколько возможна настройка уровня косвенного обращения в объявлении.  Объявления предназначены как для Visual Basic и Visual C\# для C.  
  
|Неуправляемая сигнатура|Управляемое объявление:                <br /> без косвенного обращения               <br />  `Structure MyType`  <br />  `struct MyType;`|Управляемое объявление:                <br /> один уровень косвенного обращения               <br />  `Class MyType`  <br />  `class MyType;`|  
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> Требует отсутствия уровней косвенного обращения.|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> Добавляет ноль уровней косвенного обращения.|Невозможно, так как уже существует один уровень косвенного обращения.|  
|`DoWork(MyType* x);`<br /><br /> Требует одного уровня косвенного обращения.|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> Добавляет один уровень косвенного обращения.|`DoWork(ByVal x As MyType)`  <br />  `DoWork(MyType x)`<br /><br /> Добавляет ноль уровней косвенного обращения.|  
|`DoWork(MyType** x);`<br /><br /> Требует двух уровней косвенного обращения.|Невозможно, так как **ByRef** или **ByRef**`ref` нельзя использовать `ref`.|`DoWork(ByRef x As MyType)`  <br />  `DoWork(ref MyType x)`<br /><br /> Добавляет один уровень косвенного обращения.|  
  
 Эта таблица содержит следующие указания для объявлений вызовов неуправляемого кода:  
  
-   Если неуправляемая функция не требует косвенного обращения, структуру следует передавать по значению.  
  
-   Если для неуправляемой функции требуется один уровень косвенного обращения, используется либо структура, передаваемая по ссылке, либо класс, передаваемый по значению.  
  
-   Если для неуправляемой функции требуется два уровня косвенного обращения, используется класс, передаваемый по ссылке.  
  
## Объявление и передача структур  
 В следующем примере показано определение структур `Point` и `Rect` в управляемом коде и передача типов в качестве параметра функции **PtInRect** в файле библиотеки User32.dll.  Для функции **PtInRect** используется следующая неуправляемая сигнатура:  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Обратите внимание, что структуру Rect следует передавать по ссылке, так как функция должна получить указатель на тип RECT.  
  
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
  
## Объявление и передача классов  
 Если для класса используется фиксированное размещение членов, их можно передавать в неуправляемую функцию DLL,.  В следующем примере демонстрируется передача последовательно упорядоченных в определении членов класса `MySystemTime` в функцию **GetSystemTime** в файле User32.dll.  Для функции **GetSystemTime** используется следующая неуправляемая сигнатура:  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 В отличие от типов значений для классов всегда используется, по крайней мере, один уровень косвенного обращения.  
  
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
  
## См. также  
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)   
 [Класс StructLayoutAttribute](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [Класс StructLayoutAttribute](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic)   
 [Класс FieldOffsetAttribute](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)