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
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="149ec-102">Маршалинг по умолчанию для строк</span><span class="sxs-lookup"><span data-stu-id="149ec-102">Default Marshaling for Strings</span></span>

<span data-ttu-id="149ec-103">Классы <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> ведут себя при маршалинге одинаково.</span><span class="sxs-lookup"><span data-stu-id="149ec-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="149ec-104">Строки маршалируются как тип `BSTR` стиля COM или как строка (массив символов), заканчивающаяся символом null.</span><span class="sxs-lookup"><span data-stu-id="149ec-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="149ec-105">Символы в строке могут маршалироваться как символы Юникода (по умолчанию в системах Windows) или символы в кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="149ec-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="149ec-106">Строки, используемые в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="149ec-106">Strings Used in Interfaces</span></span>

<span data-ttu-id="149ec-107">В таблице ниже показаны варианты маршалинга данных строкового типа в неуправляемый код в качестве аргумента метода.</span><span class="sxs-lookup"><span data-stu-id="149ec-107">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="149ec-108">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в COM-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="149ec-108">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="149ec-109">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="149ec-109">Enumeration type</span></span>|<span data-ttu-id="149ec-110">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="149ec-110">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="149ec-111">`UnmanagedType.BStr` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="149ec-111">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="149ec-112">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="149ec-112">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="149ec-113">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="149ec-113">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="149ec-114">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="149ec-114">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="149ec-115">Эта таблица применяется к <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="149ec-115">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="149ec-116">Для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `UnmanagedType.LPStr` и `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="149ec-116">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="149ec-117">В примере ниже показаны строки, объявленные в интерфейсе `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="149ec-117">The following example shows strings declared in the `IStringWorker` interface.</span></span>

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

<span data-ttu-id="149ec-118">В примере ниже показан соответствующий интерфейс, описанный в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="149ec-118">The following example shows the corresponding interface described in a type library.</span></span>

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

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="149ec-119">Строки, используемые в вызовах неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="149ec-119">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="149ec-120">Вызов неуправляемого кода копирует строковые аргументы, выполняя преобразование из формата .NET Framework (Юникод) в неуправляемый формат платформы.</span><span class="sxs-lookup"><span data-stu-id="149ec-120">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="149ec-121">При возврате из вызова строки не изменяются и не копируются обратно из неуправляемой памяти в управляемую.</span><span class="sxs-lookup"><span data-stu-id="149ec-121">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="149ec-122">В таблице ниже перечислены варианты маршалинга для строк, маршалируемых в качестве аргумента метода при вызове неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="149ec-122">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="149ec-123">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк.</span><span class="sxs-lookup"><span data-stu-id="149ec-123">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="149ec-124">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="149ec-124">Enumeration type</span></span>|<span data-ttu-id="149ec-125">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="149ec-125">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="149ec-126">Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="149ec-126">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="149ec-127">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="149ec-127">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="149ec-128">`UnmanagedType.LPStr` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="149ec-128">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="149ec-129">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="149ec-129">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="149ec-130">Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.</span><span class="sxs-lookup"><span data-stu-id="149ec-130">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="149ec-131">Указатель на строку знаков в кодировке UTF-8, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="149ec-131">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="149ec-132">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="149ec-132">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="149ec-133">Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке, зависящей от платформы.</span><span class="sxs-lookup"><span data-stu-id="149ec-133">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="149ec-134">Значение, позволяющее Visual Basic .NET изменять строку в неуправляемом коде и получать результаты, отраженные в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="149ec-134">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="149ec-135">Это значение поддерживается только для вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="149ec-135">This value is supported only for platform invoke.</span></span> <span data-ttu-id="149ec-136">Это значение по умолчанию для строк `ByVal` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="149ec-136">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="149ec-137">Эта таблица применяется к <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="149ec-137">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="149ec-138">Для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `LPStr`, `LPTStr` и `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="149ec-138">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="149ec-139">В определении типа ниже показано правильное использование атрибута `MarshalAsAttribute` для вызовов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="149ec-139">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

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

## <a name="strings-used-in-structures"></a><span data-ttu-id="149ec-140">Строки, используемые в структурах</span><span class="sxs-lookup"><span data-stu-id="149ec-140">Strings Used in Structures</span></span>

<span data-ttu-id="149ec-141">Строки являются допустимыми элементами структур, но буферы <xref:System.Text.StringBuilder> недопустимы в структурах.</span><span class="sxs-lookup"><span data-stu-id="149ec-141">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="149ec-142">В таблице ниже показаны варианты маршалинга для типа данных <xref:System.String> при маршалинге типа как поля.</span><span class="sxs-lookup"><span data-stu-id="149ec-142">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="149ec-143">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в поле.</span><span class="sxs-lookup"><span data-stu-id="149ec-143">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="149ec-144">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="149ec-144">Enumeration type</span></span>|<span data-ttu-id="149ec-145">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="149ec-145">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="149ec-146">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="149ec-146">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="149ec-147">`UnmanagedType.LPStr` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="149ec-147">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="149ec-148">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="149ec-148">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="149ec-149">Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.</span><span class="sxs-lookup"><span data-stu-id="149ec-149">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="149ec-150">Указатель на строку знаков в кодировке UTF-8, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="149ec-150">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="149ec-151">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="149ec-151">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="149ec-152">Массив символов фиксированной длины; тип массива определяется кодировкой содержащей его структуры.</span><span class="sxs-lookup"><span data-stu-id="149ec-152">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="149ec-153">Тип `ByValTStr` используется для встроенных массивов символов фиксированной длины, расположенных в структуре.</span><span class="sxs-lookup"><span data-stu-id="149ec-153">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="149ec-154">Другие типы применяются к ссылкам на строки, включенным в структуры, содержащие указатели на строки.</span><span class="sxs-lookup"><span data-stu-id="149ec-154">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="149ec-155">Аргумент `CharSet` класса <xref:System.Runtime.InteropServices.StructLayoutAttribute>, применяемый к содержащей указатели структуре, определяет формат символов строк в структурах.</span><span class="sxs-lookup"><span data-stu-id="149ec-155">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="149ec-156">Ниже приведены примеры структур, содержащих ссылки на строки и встроенные строки, а также символы в кодировках ANSI, Юникод и кодировке, зависящей от платформы.</span><span class="sxs-lookup"><span data-stu-id="149ec-156">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="149ec-157">Представление этих структур в библиотеке типов показано в следующем коде C++:</span><span class="sxs-lookup"><span data-stu-id="149ec-157">The representation of these structures in a type library is shown in the following C++ code:</span></span>

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

<span data-ttu-id="149ec-158">В примере ниже показано, как с помощью класса <xref:System.Runtime.InteropServices.MarshalAsAttribute> определить одну и ту же структуру в различных форматах.</span><span class="sxs-lookup"><span data-stu-id="149ec-158">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

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

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="149ec-159">Буферы строк фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="149ec-159">Fixed-Length String Buffers</span></span>

<span data-ttu-id="149ec-160">При некоторых обстоятельствах необходимо передавать в неуправляемый код для обработки символьные буферы фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="149ec-160">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="149ec-161">Простая передача строки в этом случае не работает, так как вызываемый объект не может изменять содержимое переданного буфера.</span><span class="sxs-lookup"><span data-stu-id="149ec-161">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="149ec-162">Даже если строка передается по ссылке, не существует способа инициализации буфера заданного размера.</span><span class="sxs-lookup"><span data-stu-id="149ec-162">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="149ec-163">Решением является передача в качестве аргумента буфера <xref:System.Text.StringBuilder> вместо <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="149ec-163">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="149ec-164">Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="149ec-164">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="149ec-165">Его также можно инициализировать с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="149ec-165">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="149ec-166">Например, если вы инициализируете буфер `StringBuilder` емкостью `N`, упаковщик предоставляет буфер размером (`N`+1) символов.</span><span class="sxs-lookup"><span data-stu-id="149ec-166">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="149ec-167">Дополнительный символ объясняется тем, что неуправляемая строка заканчивается символом null, а буфер `StringBuilder` нет.</span><span class="sxs-lookup"><span data-stu-id="149ec-167">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="149ec-168">Например, функция API [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) Windows (определенная в файле *winuser.h*) требует, чтобы вызывающий объект передавал буфер символов фиксированной длины, в который эта функция записывает текст окна.</span><span class="sxs-lookup"><span data-stu-id="149ec-168">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="149ec-169">`LpString` указывает на выделенный вызывающим объектом буфер размером `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="149ec-169">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="149ec-170">Предполагается, что вызывающий объект выделяет буфер и задает аргумент `nMaxCount` равным размеру выделяемого буфера.</span><span class="sxs-lookup"><span data-stu-id="149ec-170">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="149ec-171">В приведенном ниже примере показано объявление функции `GetWindowText`, определенное в файле *winuser.h*.</span><span class="sxs-lookup"><span data-stu-id="149ec-171">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="149ec-172">Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="149ec-172">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="149ec-173">В примере кода ниже показана инициализация буфера `StringBuilder` с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="149ec-173">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="149ec-174">См. также</span><span class="sxs-lookup"><span data-stu-id="149ec-174">See also</span></span>

- [<span data-ttu-id="149ec-175">Характеристики маршалинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="149ec-175">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="149ec-176">Mаршалинг строк</span><span class="sxs-lookup"><span data-stu-id="149ec-176">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="149ec-177">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="149ec-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="149ec-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)</span><span class="sxs-lookup"><span data-stu-id="149ec-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="149ec-179">Копирование и закрепление</span><span class="sxs-lookup"><span data-stu-id="149ec-179">Copying and Pinning</span></span>](copying-and-pinning.md)
