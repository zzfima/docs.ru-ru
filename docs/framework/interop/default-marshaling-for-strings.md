---
title: Маршалинг по умолчанию для строк
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 49f2d871a42db484e20f0bfc35634a0e8b959c2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123548"
---
# <a name="default-marshaling-for-strings"></a>Маршалинг по умолчанию для строк

Классы <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> ведут себя при маршалинге одинаково.

Строки маршалируются как тип `BSTR` стиля COM или как строка (массив символов), заканчивающаяся символом null. Символы в строке могут маршалироваться как символы Юникода (по умолчанию в системах Windows) или символы в кодировке ANSI.

## <a name="strings-used-in-interfaces"></a>Строки, используемые в интерфейсах

В таблице ниже показаны варианты маршалинга данных строкового типа в неуправляемый код в качестве аргумента метода. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в COM-интерфейсы.

|Тип перечисления|Описание неуправляемого формата|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr` (по умолчанию)|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|
|`UnmanagedType.LPStr`|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|

Эта таблица применяется к <xref:System.String>. Для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `UnmanagedType.LPStr` и `UnmanagedType.LPWStr`.

В примере ниже показаны строки, объявленные в интерфейсе `IStringWorker`.

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

В примере ниже показан соответствующий интерфейс, описанный в библиотеке типов.

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a>Строки, используемые в вызовах неуправляемого кода

Вызов неуправляемого кода копирует строковые аргументы, выполняя преобразование из формата .NET Framework (Юникод) в неуправляемый формат платформы. При возврате из вызова строки не изменяются и не копируются обратно из неуправляемой памяти в управляемую.

В таблице ниже перечислены варианты маршалинга для строк, маршалируемых в качестве аргумента метода при вызове неуправляемого кода. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк.

|Тип перечисления|Описание неуправляемого формата|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке ANSI.|
|`UnmanagedType.BStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|
|`UnmanagedType.LPStr` (по умолчанию)|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|
|`UnmanagedType.LPTStr`|Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.|
|`UnmanagedType.LPUTF8Str`|Указатель на строку знаков в кодировке UTF-8, завершающуюся нулевым значением.|
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|
|`UnmanagedType.TBStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке, зависящей от платформы.|
|`VBByRefStr`|Значение, позволяющее Visual Basic .NET изменять строку в неуправляемом коде и получать результаты, отраженные в управляемом коде. Это значение поддерживается только для вызова неуправляемого кода. Это значение по умолчанию для строк `ByVal` в Visual Basic.|

Эта таблица применяется к <xref:System.String>. Для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `LPStr`, `LPTStr` и `LPWStr`.

В определении типа ниже показано правильное использование атрибута `MarshalAsAttribute` для вызовов неуправляемого кода.

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a>Строки, используемые в структурах

Строки являются допустимыми элементами структур, но буферы <xref:System.Text.StringBuilder> недопустимы в структурах. В таблице ниже показаны варианты маршалинга для типа данных <xref:System.String> при маршалинге типа как поля. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в поле.

|Тип перечисления|Описание неуправляемого формата|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|
|`UnmanagedType.LPStr` (по умолчанию)|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|
|`UnmanagedType.LPTStr`|Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.|
|`UnmanagedType.LPUTF8Str`|Указатель на строку знаков в кодировке UTF-8, завершающуюся нулевым значением.|
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|
|`UnmanagedType.ByValTStr`|Массив символов фиксированной длины; тип массива определяется кодировкой содержащей его структуры.|

Тип `ByValTStr` используется для встроенных массивов символов фиксированной длины, расположенных в структуре. Другие типы применяются к ссылкам на строки, включенным в структуры, содержащие указатели на строки.

Аргумент `CharSet` класса <xref:System.Runtime.InteropServices.StructLayoutAttribute>, применяемый к содержащей указатели структуре, определяет формат символов строк в структурах. Ниже приведены примеры структур, содержащих ссылки на строки и встроенные строки, а также символы в кодировках ANSI, Юникод и кодировке, зависящей от платформы. Представление этих структур в библиотеке типов показано в следующем коде C++:

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

В примере ниже показано, как с помощью класса <xref:System.Runtime.InteropServices.MarshalAsAttribute> определить одну и ту же структуру в различных форматах.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

```vb
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _
Structure StringInfoA
    <MarshalAs(UnmanagedType.LPStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _
Structure StringInfoW
    <MarshalAs(UnmanagedType.LPWStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
<MarshalAs(UnmanagedType.BStr)> Public f3 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _
Structure StringInfoT
    <MarshalAs(UnmanagedType.LPTStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure
```

## <a name="fixed-length-string-buffers"></a>Буферы строк фиксированной длины

При некоторых обстоятельствах необходимо передавать в неуправляемый код для обработки символьные буферы фиксированной длины. Простая передача строки в этом случае не работает, так как вызываемый объект не может изменять содержимое переданного буфера. Даже если строка передается по ссылке, не существует способа инициализации буфера заданного размера.

Решением является передача в качестве аргумента буфера <xref:System.Text.StringBuilder> вместо <xref:System.String>. Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`. Его также можно инициализировать с фиксированной длиной. Например, если вы инициализируете буфер `StringBuilder` емкостью `N`, упаковщик предоставляет буфер размером (`N`+1) символов. Дополнительный символ объясняется тем, что неуправляемая строка заканчивается символом null, а буфер `StringBuilder` нет.

Например, функция API [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) Windows (определенная в файле *winuser.h*) требует, чтобы вызывающий объект передавал буфер символов фиксированной длины, в который эта функция записывает текст окна. `LpString` указывает на выделенный вызывающим объектом буфер размером `nMaxCount`. Предполагается, что вызывающий объект выделяет буфер и задает аргумент `nMaxCount` равным размеру выделяемого буфера. В приведенном ниже примере показано объявление функции `GetWindowText`, определенное в файле *winuser.h*.

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`. В примере кода ниже показана инициализация буфера `StringBuilder` с фиксированной длиной.

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a>См. также

- [Характеристики маршалинга по умолчанию](default-marshaling-behavior.md)
- [Mаршалинг строк](marshaling-strings.md)
- [Преобразуемые и непреобразуемые типы](blittable-and-non-blittable-types.md)
- [Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)
- [Копирование и закрепление](copying-and-pinning.md)
