---
title: "Маршалинг по умолчанию для строк"
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
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34cd8194f5f36c2f9c93517403aa27f6bbbcb698
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="default-marshaling-for-strings"></a>Маршалинг по умолчанию для строк
Классы <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> ведут себя при маршалинге одинаково.  
  
 Строки маршалируются как тип `BSTR` стиля COM или как строка (массив символов), заканчивающаяся символом null. Символы в строке могут маршалироваться как символы Юникода (по умолчанию в системах Windows) или символы в кодировке ANSI.  
  
 В этом разделе представлена следующая информация о маршалинге строковых типов:  
  
-   [Строки, используемые в интерфейсах](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [Строки, используемые в вызовах неуправляемого кода](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [Строки, используемые в структурах](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [Буферы строк фиксированной длины](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>   
## <a name="strings-used-in-interfaces"></a>Строки, используемые в интерфейсах  
 В таблице ниже показаны варианты маршалинга данных строкового типа в неуправляемый код в качестве аргумента метода. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в COM-интерфейсы.  
  
|Тип перечисления|Описание неуправляемого формата|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr` (по умолчанию)|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|  
|`UnmanagedType.LPStr`|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|  
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|  
  
 Эта таблица применяется к строкам. Однако для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `UnmanagedType.LPStr` и `UnmanagedType.LPWStr`.  
  
 В примере ниже показаны строки, объявленные в интерфейсе `IStringWorker`.  
  
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
  
 В примере ниже показан соответствующий интерфейс, описанный в библиотеке типов.  
  
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
## <a name="strings-used-in-platform-invoke"></a>Строки, используемые в вызовах неуправляемого кода  
 Вызов неуправляемого кода копирует строковые аргументы, выполняя преобразование из формата .NET Framework (Юникод) в неуправляемый формат платформы. При возврате из вызова строки не изменяются и не копируются обратно из неуправляемой памяти в управляемую.  
  
 В таблице ниже перечислены варианты маршалинга для строк, маршалируемых в качестве аргумента метода при вызове неуправляемого кода. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк.  
  
|Тип перечисления|Описание неуправляемого формата|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке ANSI.|  
|`UnmanagedType.BStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|  
|`UnmanagedType.LPStr`|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|  
|`UnmanagedType.LPTStr`|Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.|  
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|  
|`UnmanagedType.TBStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами в кодировке, зависящей от платформы.|  
|`VBByRefStr`|Значение, позволяющее Visual Basic .NET изменять строку в неуправляемом коде и получать результаты, отраженные в управляемом коде. Это значение поддерживается только для вызова неуправляемого кода. Это значение по умолчанию для строк `ByVal` в Visual Basic.|  
  
 Эта таблица применяется к строкам. Однако для <xref:System.Text.StringBuilder> единственными допустимыми вариантами являются `LPStr`, `LPTStr` и `LPWStr`.  
  
 В определении типа ниже показано правильное использование атрибута `MarshalAsAttribute` для вызовов неуправляемого кода.  
  
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
## <a name="strings-used-in-structures"></a>Строки, используемые в структурах  
 Строки являются допустимыми элементами структур, но буферы <xref:System.Text.StringBuilder> недопустимы в структурах. В таблице ниже показаны варианты маршалинга для строкового типа данных при маршалинге типа как поля. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга строк в поле.  
  
|Тип перечисления|Описание неуправляемого формата|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|Тип `BSTR` стиля COM с фиксированной длиной и символами Юникода.|  
|`UnmanagedType.LPStr`|Указатель на массив символов в кодировке ANSI, завершающийся значением null.|  
|`UnmanagedType.LPTStr`|Указатель на массив символов, завершающийся значением null, в зависящей от платформы кодировке.|  
|`UnmanagedType.LPWStr`|Указатель на строку знаков в кодировке Юникод, завершающуюся нулевым значением.|  
|`UnmanagedType.ByValTStr`|Массив символов фиксированной длины; тип массива определяется кодировкой содержащей его структуры.|  
  
 Тип `ByValTStr` используется для встроенных массивов символов фиксированной длины, расположенных в структуре. Другие типы применяются к ссылкам на строки, включенным в структуры, содержащие указатели на строки.  
  
 Аргумент `CharSet` атрибута <xref:System.Runtime.InteropServices.StructLayoutAttribute>, применяемого к содержащей указатели структуре, определяет формат символов строк в структурах. Ниже приведены примеры структур, содержащих ссылки на строки и встроенные строки, а также символы в кодировках ANSI, Юникод и кодировке, зависящей от платформы.  
  
### <a name="type-library-representation"></a>Представление библиотеки типов  
  
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
  
 В примере кода ниже показано, как с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> определить одну и ту же структуру в различных форматах.  
  
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
## <a name="fixed-length-string-buffers"></a>Буферы строк фиксированной длины  
 При некоторых обстоятельствах необходимо передавать в неуправляемый код для обработки символьные буферы фиксированной длины. Простая передача строки в этом случае не работает, так как вызываемый объект не может изменять содержимое переданного буфера. Даже если строка передается по ссылке, не существует способа инициализации буфера заданного размера.  
  
 Решением является передача в качестве аргумента буфера <xref:System.Text.StringBuilder> вместо строки. Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`. Его также можно инициализировать с фиксированной длиной. Например, если вы инициализируете буфер `StringBuilder` емкостью `N`, упаковщик предоставляет буфер размером (`N`+1) символов. Дополнительный символ объясняется тем, что неуправляемая строка заканчивается символом null, а буфер `StringBuilder` нет.  
  
 Например, функция `GetWindowText` интерфейса Microsoft Win32 API (определенная в Windows.h) является буфером символов фиксированной длины, который должен быть передан в неуправляемый код для обработки. `LpString` указывает на выделенный вызывающим объектом буфер размером `nMaxCount`. Предполагается, что вызывающий объект выделяет буфер и задает аргумент `nMaxCount` равным размеру выделяемого буфера. В приведенном ниже коде показано объявление функции `GetWindowText`, определенное в файле Windows.h.  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 Буфер `StringBuilder` может быть разыменован и изменен вызываемым объектом при условии, что он не превышает емкость `StringBuilder`. В примере кода ниже показана инициализация буфера `StringBuilder` с фиксированной длиной.  
  
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
  
## <a name="see-also"></a>См. также  
 [Характеристики маршалинга по умолчанию](../../../docs/framework/interop/default-marshaling-behavior.md)  
 [Преобразуемые и непреобразуемые типы](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [Атрибуты направления](http://msdn.microsoft.com/en-us/241ac5b5-928e-4969-8f58-1dbc048f9ea2)  
 [Копирование и закрепление](../../../docs/framework/interop/copying-and-pinning.md)
