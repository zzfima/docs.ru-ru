---
title: Маршалинг по умолчанию для строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47543056eaa538b008db3332dda776c0f300108d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078477"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="46a4a-102">Маршалинг по умолчанию для строк</span><span class="sxs-lookup"><span data-stu-id="46a4a-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="46a4a-103">Классы <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> ведут себя при маршалинге одинаково.</span><span class="sxs-lookup"><span data-stu-id="46a4a-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="46a4a-104">Строки маршалируются как тип `BSTR` стиля COM или как строка (массив символов), заканчивающаяся символом null.</span><span class="sxs-lookup"><span data-stu-id="46a4a-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="46a4a-105">Символы в строке могут маршалироваться как символы Юникода (по умолчанию в системах Windows) или символы в кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="46a4a-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="46a4a-106">В этом разделе представлена следующая информация о маршалинге строковых типов:</span><span class="sxs-lookup"><span data-stu-id="46a4a-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="46a4a-107">Строки, используемые в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="46a4a-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="46a4a-108">Строки, используемые в вызовах неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="46a4a-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="46a4a-109">Строки, используемые в структурах</span><span class="sxs-lookup"><span data-stu-id="46a4a-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="46a4a-110">Буферы строк фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="46a4a-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="46a4a-111">Строки, используемые в интерфейсах</span><span class="sxs-lookup"><span data-stu-id="46a4a-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="46a4a-112">В таблице ниже показаны варианты маршалинга данных строкового типа в неуправляемый код в качестве аргумента метода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="46a4a-113">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в COM-интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="46a4a-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="46a4a-114">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="46a4a-114">Enumeration type</span></span>|<span data-ttu-id="46a4a-115">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="46a4a-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="46a4a-116">`UnmanagedType.BStr` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="46a4a-116">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="46a4a-117">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="46a4a-118">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="46a4a-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="46a4a-119">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="46a4a-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="46a4a-120">Эта таблица применяется к строкам.</span><span class="sxs-lookup"><span data-stu-id="46a4a-120">This table applies to strings.</span></span> <span data-ttu-id="46a4a-121">Однако для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `UnmanagedType.LPStr` и `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="46a4a-122">В примере ниже показаны строки, объявленные в интерфейсе `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

<span data-ttu-id="46a4a-123">В примере ниже показан соответствующий интерфейс, описанный в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="46a4a-123">The following example shows the corresponding interface described in a type library.</span></span>

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="46a4a-124">Строки, используемые в вызовах неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="46a4a-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="46a4a-125">Вызов неуправляемого кода копирует строковые аргументы, выполняя преобразование из формата .NET Framework (Юникод) в неуправляемый формат платформы.</span><span class="sxs-lookup"><span data-stu-id="46a4a-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="46a4a-126">При возврате из вызова строки не изменяются и не копируются обратно из неуправляемой памяти в управляемую.</span><span class="sxs-lookup"><span data-stu-id="46a4a-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="46a4a-127">В таблице ниже перечислены варианты маршалинга для строк, маршалируемых в качестве аргумента метода при вызове неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="46a4a-128">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк.</span><span class="sxs-lookup"><span data-stu-id="46a4a-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="46a4a-129">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="46a4a-129">Enumeration type</span></span>|<span data-ttu-id="46a4a-130">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="46a4a-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="46a4a-131">Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="46a4a-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="46a4a-132">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="46a4a-133">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="46a4a-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="46a4a-134">Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.</span><span class="sxs-lookup"><span data-stu-id="46a4a-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="46a4a-135">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="46a4a-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="46a4a-136">Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке, зависящей от платформы.</span><span class="sxs-lookup"><span data-stu-id="46a4a-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="46a4a-137">Значение, позволяющее Visual Basic .NET изменять строку в неуправляемом коде и получать результаты, отраженные в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="46a4a-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="46a4a-138">Это значение поддерживается только для вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="46a4a-139">Это значение по умолчанию для строк `ByVal` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46a4a-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="46a4a-140">Эта таблица применяется к строкам.</span><span class="sxs-lookup"><span data-stu-id="46a4a-140">This table applies to strings.</span></span> <span data-ttu-id="46a4a-141">Однако для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `LPStr`, `LPTStr` и `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="46a4a-142">В определении типа ниже показано правильное использование атрибута `MarshalAsAttribute` для вызовов неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="46a4a-143">Строки, используемые в структурах</span><span class="sxs-lookup"><span data-stu-id="46a4a-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="46a4a-144">Строки являются допустимыми элементами структур, но буферы <xref:System.Text.StringBuilder> недопустимы в структурах.</span><span class="sxs-lookup"><span data-stu-id="46a4a-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="46a4a-145">В таблице ниже показаны варианты маршалинга для строкового типа данных при маршалинге типа как поля.</span><span class="sxs-lookup"><span data-stu-id="46a4a-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="46a4a-146">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в поле.</span><span class="sxs-lookup"><span data-stu-id="46a4a-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="46a4a-147">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="46a4a-147">Enumeration type</span></span>|<span data-ttu-id="46a4a-148">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="46a4a-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="46a4a-149">Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.</span><span class="sxs-lookup"><span data-stu-id="46a4a-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="46a4a-150">Указатель на массив символов в кодировке ANSI, завершающийся значением null.</span><span class="sxs-lookup"><span data-stu-id="46a4a-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="46a4a-151">Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.</span><span class="sxs-lookup"><span data-stu-id="46a4a-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="46a4a-152">Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="46a4a-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="46a4a-153">Массив символов фиксированной длины; тип массива определяется кодировкой содержащей его структуры.</span><span class="sxs-lookup"><span data-stu-id="46a4a-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="46a4a-154">Тип `ByValTStr` используется для встроенных массивов символов фиксированной длины, расположенных в структуре.</span><span class="sxs-lookup"><span data-stu-id="46a4a-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="46a4a-155">Другие типы применяются к ссылкам на строки, включенным в структуры, содержащие указатели на строки.</span><span class="sxs-lookup"><span data-stu-id="46a4a-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="46a4a-156">Аргумент `CharSet` атрибута <xref:System.Runtime.InteropServices.StructLayoutAttribute>, применяемого к содержащей указатели структуре, определяет формат символов строк в структурах.</span><span class="sxs-lookup"><span data-stu-id="46a4a-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="46a4a-157">Ниже приведены примеры структур, содержащих ссылки на строки и встроенные строки, а также символы в кодировках ANSI, Юникод и кодировке, зависящей от платформы.</span><span class="sxs-lookup"><span data-stu-id="46a4a-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="46a4a-158">Представление библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="46a4a-158">Type Library Representation</span></span>  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="46a4a-159">В примере кода ниже показано, как с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> определить одну и ту же структуру в различных форматах.</span><span class="sxs-lookup"><span data-stu-id="46a4a-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
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
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="46a4a-160">Буферы строк фиксированной длины</span><span class="sxs-lookup"><span data-stu-id="46a4a-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="46a4a-161">При некоторых обстоятельствах необходимо передавать в неуправляемый код для обработки символьные буферы фиксированной длины.</span><span class="sxs-lookup"><span data-stu-id="46a4a-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="46a4a-162">Простая передача строки в этом случае не работает, так как вызываемый объект не может изменять содержимое переданного буфера.</span><span class="sxs-lookup"><span data-stu-id="46a4a-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="46a4a-163">Даже если строка передается по ссылке, не существует способа инициализации буфера заданного размера.</span><span class="sxs-lookup"><span data-stu-id="46a4a-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="46a4a-164">Решением является передача в качестве аргумента буфера <xref:System.Text.StringBuilder> вместо строки.</span><span class="sxs-lookup"><span data-stu-id="46a4a-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="46a4a-165">Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="46a4a-166">Его также можно инициализировать с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="46a4a-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="46a4a-167">Например, если вы инициализируете буфер `StringBuilder` емкостью `N`, упаковщик предоставляет буфер размером (`N`+1) символов.</span><span class="sxs-lookup"><span data-stu-id="46a4a-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="46a4a-168">Дополнительный символ объясняется тем, что неуправляемая строка заканчивается символом null, а буфер `StringBuilder` нет.</span><span class="sxs-lookup"><span data-stu-id="46a4a-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="46a4a-169">Например, функция `GetWindowText` интерфейса Microsoft Windows API (определенная в Windows.h) является буфером символов фиксированной длины, который должен быть передан в неуправляемый код для обработки.</span><span class="sxs-lookup"><span data-stu-id="46a4a-169">For example, the Microsoft Windows API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="46a4a-170">`LpString` указывает на выделенный вызывающим объектом буфер размером `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="46a4a-171">Предполагается, что вызывающий объект выделяет буфер и задает аргумент `nMaxCount` равным размеру выделяемого буфера.</span><span class="sxs-lookup"><span data-stu-id="46a4a-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="46a4a-172">В приведенном ниже коде показано объявление функции `GetWindowText`, определенное в файле Windows.h.</span><span class="sxs-lookup"><span data-stu-id="46a4a-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="46a4a-173">Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="46a4a-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="46a4a-174">В примере кода ниже показана инициализация буфера `StringBuilder` с фиксированной длиной.</span><span class="sxs-lookup"><span data-stu-id="46a4a-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="46a4a-175">См. также</span><span class="sxs-lookup"><span data-stu-id="46a4a-175">See also</span></span>

- [<span data-ttu-id="46a4a-176">Характеристики маршалинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="46a4a-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="46a4a-177">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="46a4a-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="46a4a-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)</span><span class="sxs-lookup"><span data-stu-id="46a4a-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="46a4a-179">Копирование и закрепление</span><span class="sxs-lookup"><span data-stu-id="46a4a-179">Copying and Pinning</span></span>](copying-and-pinning.md)
