---
title: Передача структур
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
ms.openlocfilehash: 11e329fa8f0c059b6c2f1c8ccb1d6bd0d0f0030a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181337"
---
# <a name="passing-structures"></a>Передача структур
В качестве параметров во многие неуправляемые функции должны передаваться члены, структуры (определяемые пользователем типы в Visual Basic) или члены классов, которые определяются в управляемом коде. При передаче структур или классов в неуправляемый код посредством вызовов неуправляемого кода необходимо указать дополнительную информацию для сохранения исходного размещения и выравнивания. В этом разделе описывается атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute>, который используется для определения форматированных типов. Для управляемых структур и классов можно выбрать любое из нескольких предсказуемых поведений размещения в перечислении **LayoutKind**.  
  
 Представленные в этом разделе понятия приводятся с учетом важного различия между структурами и типами классов. Структуры представляют собой типы значений, а классы — ссылочные типы. В классах всегда реализуется как минимум один уровень косвенного обращения к памяти (указатель на значение). Это важное отличие, поскольку неуправляемые функции часто используют косвенное обращение, как показано в сигнатурах в первом столбце в следующей таблице. Управляемые структуры и объявления классов в оставшихся столбцах демонстрируют, в какой степени можно изменить уровень косвенного обращения в объявлении. Объявления предоставляются как для Visual Basic, так и для Visual C#.  
  
|Неуправляемая сигнатура|Управляемое объявление: <br />без косвенного обращения<br />`Structure MyType`<br />`struct MyType;`|Управляемое объявление: <br />один уровень косвенного обращения<br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> Требуется ноль уровней косвенного обращения.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Добавляет ноль уровней косвенного обращения.|Невозможно, поскольку один уровень косвенного обращения уже существует.|  
|`DoWork(MyType* x);`<br /><br /> Требуется один уровень косвенного обращения.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Добавляет один уровень косвенного обращения.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Добавляет ноль уровней косвенного обращения.|  
|`DoWork(MyType** x);`<br /><br /> Требуется два уровня косвенного обращения.|Невозможно, поскольку нельзя использовать **ByRef** **ByRef** или `ref` `ref`.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Добавляет один уровень косвенного обращения.|  
  
 В этой таблице описываются следующие рекомендации по объявлению вызовов неуправляемого кода:  
  
- Если неуправляемая функция не требует косвенного обращения, используйте структуру, передаваемую по значению.  
  
- Если неуправляемая функция требует один уровень косвенного обращения, используйте передаваемую по ссылке структуру или передаваемый по значению класс.  
  
- Если неуправляемая функция требует два уровня косвенного обращения, используйте класс, передаваемый по ссылке.  
  
## <a name="declaring-and-passing-structures"></a>Объявление и передача структур  
 В следующем примере демонстрируется, как определить структуры `Point` и `Rect` в управляемом коде и передать типы в качестве параметров в функцию **PtInRect** в файле User32.dll. Функция **PtInRect** имеет следующую неуправляемую сигнатуру:  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Обратите внимание, что структуру Rect необходимо передавать по ссылке, поскольку функция принимает указатель на тип RECT.  
  
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
  
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "user32.dll" (
        ByRef r As Rect, p As Point) As Boolean  
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
  
internal static class NativeMethods
{  
    [DllImport("User32.dll")]  
    internal static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a>Объявление и передача классов  
 Члены класса можно передавать в неуправляемую функцию DLL при условии, что класс имеет фиксированное размещение членов. В следующем примере демонстрируется, как передать члены класса `MySystemTime`, которые определяются последовательно, в функцию **GetSystemTime** в файле User32.dll. Функция **GetSystemTime** имеет следующую неуправляемую сигнатуру:  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 В отличие от типов значений, классы всегда имеют как минимум один уровень косвенного обращения.  
  
```vb  
Imports System.Runtime.InteropServices  
  
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
  
Friend Class NativeMethods  
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        sysTime As MySystemTime)  
    Friend Declare Auto Function MessageBox Lib "User32.dll" (
        hWnd As IntPtr, lpText As String, lpCaption As String, uType As UInteger) As Integer  
End Class  
  
Public Class TestPlatformInvoke
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        NativeMethods.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)
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
internal static class NativeMethods
{  
    [DllImport("Kernel32.dll")]  
    internal static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet = CharSet.Auto)]  
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        NativeMethods.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a>См. также раздел

- [Вызов функции DLL](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
