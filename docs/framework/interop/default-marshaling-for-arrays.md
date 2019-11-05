---
title: Маршалинг по умолчанию для массивов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
ms.openlocfilehash: 8505f4c742fb002be249ab069708f7f768c672df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123581"
---
# <a name="default-marshaling-for-arrays"></a>Маршалинг по умолчанию для массивов
Если приложение полностью состоит из управляемого кода, общеязыковая среда выполнения (CLR) передает типы массивов в качестве параметров ввода-вывода. В отличие от этого, маршалер взаимодействия по умолчанию передает массив в качестве параметров ввода.  
  
 В рамках [оптимизации закрепления](copying-and-pinning.md) непреобразуемый массив может выступать в качестве параметра ввода-вывода при взаимодействии с объектами в том же подразделении. Тем не менее при последующем экспорте кода в библиотеку типов, используемую для создания учетной записи посредника между компьютерами, если эта библиотека используется для маршалинга вызовов между подразделениями, вызовы могут получать фактические характеристики параметра ввода.  
  
 Массивы имеют сложную структуру, поэтому для проведения различий между управляемыми и неуправляемыми массивами требуется больше информации, чем для других преобразуемых типов.  
  
## <a name="managed-arrays"></a>Управляемые массивы  
 Управляемые массивы могут иметь разные типы, однако базовым для всех этих типов является класс <xref:System.Array?displayProperty=nameWithType>. Класс **System.Array** имеет свойства, определяющие ранг, длину, нижнюю и верхнюю границы массива, а также методы доступа, сортировки, поиска, копирования и создания массивов.  
  
 Эти типы массивов являются динамическими и не имеют соответствующих статических типов в библиотеке базовых классов. В качестве уникального типа массива удобно рассматривать сочетание типа элементов и ранга. Соответственно, тип одномерного массива целых чисел отличается от типа одномерного массива чисел типа double. Аналогичным образом, его тип будет отличаться от типа двухмерного массива целых чисел. При сравнении типов не учитываются границы массивов.  
  
 Как показано в следующей таблице, любой экземпляр управляемого массива должен иметь заданные тип элементов, ранг и нижнюю границу.  
  
|Тип управляемого массива|Тип элемента|Ранг|Нижняя граница|Нотация сигнатуры|  
|------------------------|------------------|----------|-----------------|------------------------|  
|**ELEMENT_TYPE_ARRAY**|Задается по типу.|Задается по рангу.|При необходимости задается границами.|*type* **[** *n*,*m* **]**|  
|**ELEMENT_TYPE_CLASS**|Неизвестно|Неизвестно|Неизвестно|**System.Array**|  
|**ELEMENT_TYPE_SZARRAY**|Задается по типу.|1|0|*type* **[** *n* **]**|  
  
## <a name="unmanaged-arrays"></a>Неуправляемые массивы  
 Неуправляемыми могут быть безопасные массивы в стиле COM или массивы в стиле C фиксированной или переменной длины. Безопасный массив — это описывающий сам себя массив, передающий тип, ранг и границы соответствующего массива данных. Массивы в стиле C — это одномерные типизированные массивы с фиксированной нижней границей, равной 0. Служба маршалинга обеспечивает ограниченную поддержку обоих типов массивов.  
  
## <a name="passing-array-parameters-to-net-code"></a>Передача параметров массива в код .NET  
 Массивы в стиле языка C и безопасные массивы могут передаваться в код .NET из неуправляемого кода в виде безопасных массивов или массивов в стиле C. В следующей таблице показаны значения неуправляемого типа и соответствующих импортируемых типов.  
  
|Неуправляемый тип|Импортируемый тип|  
|--------------------|-------------------|  
|**SafeArray(** *Type* **)**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Ранг = 1, нижняя граница = 0. Размер известен только в том случае, если он предоставлен в управляемой сигнатуре. Безопасные массивы, ранг которых не равен 1, а нижняя граница не равна 0, не поддерживают маршалинг в виде **SZARRAY**.|  
|*Type*  **[]**|**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**<br /><br /> Ранг = 1, нижняя граница = 0. Размер известен только в том случае, если он предоставлен в управляемой сигнатуре.|  
  
### <a name="safe-arrays"></a>Безопасные массивы  
 При импорте безопасного массива из библиотеки типов в сборку .NET он преобразуется в одномерный массив известного типа (например, **int**). К элементам массива применяются те же правила преобразования типов, что и к параметрам. Например, безопасный массив типов **BSTR** преобразуется в управляемый массив строк, а безопасный массив вариантов — в управляемый массив объектов. Тип элементов **SAFEARRAY** получается из библиотеки типов и сохраняется в значении **SAFEARRAY** перечисления <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
 Поскольку ранг и границы безопасного массива нельзя определить из библиотеки типов, предполагается, что ранг равен 1, а нижняя граница — 0. Ранг и границы должны быть определены в управляемой сигнатуре, которая создается с помощью [программы импорта библиотек типов (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md). Если ранг, переданный в метод во время выполнения, отличается, возникает исключение <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>. Если тип массива, переданный во время выполнения, отличается, возникает исключение <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>. В следующем примере показано применение безопасных массивов в управляемом и неуправляемом коде.  
  
 **Неуправляемая сигнатура**  
  
```cpp
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 **Управляемая сигнатура**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 Многомерные массивы или безопасные массивы с отличной от нуля границей могут маршалироваться в управляемый код, если сигнатура метода, создаваемая с помощью программы Tlbimp.exe, изменяется, указывая на тип элементов **ELEMENT_TYPE_ARRAY** вместо **ELEMENT_TYPE_SZARRAY**. Кроме того, можно использовать параметр **/sysarray** с программой Tlbimp.exe для импорта всех массивов в качестве объектов <xref:System.Array?displayProperty=nameWithType>. Если передаваемый массив заведомо является многомерным, можно изменить код MSIL, создаваемый программой Tlbimp.exe, а затем повторно скомпилировать его. Дополнительные сведения об изменении кода MSIL см. в разделе [Настройка вызываемых оболочек времени выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)).  
  
### <a name="c-style-arrays"></a>Массивы в стиле C  
 При импорте массива в стиле C из библиотеки типов в сборку .NET массив преобразуется в **ELEMENT_TYPE_SZARRAY**.  
  
 Тип элемента массива определяется из библиотеки типов и сохраняется во время импорта. К элементам массива применяются те же правила преобразования, что и к параметрам. Например, массив типов **LPStr** преобразуется в массив типов **String**. Программа Tlbimp.exe получает тип элементов массива и применяет к параметру атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  
  
 Ранг массива принимается равным 1. Если ранг больше 1, массив маршалируется как одномерный массив в развертывании по столбцам. Нижняя граница всегда равна 0.  
  
 Библиотеки типов могут содержать массивы фиксированной или переменной длины. Поскольку в библиотеках типов содержится недостаточно информации для маршалинга массивов переменной длины, программа Tlbimp.exe может импортировать из них только массивы фиксированной длины. Для массивов фиксированной длины размер импортируется из библиотеки типов и сохраняется в атрибуте **MarshalAsAttribute**, который применяется к параметру.  
  
 Библиотеки типов, содержащие массивы переменной длины, необходимо определять вручную, как показано в следующем примере.  
  
 **Неуправляемая сигнатура**  
  
```cpp
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 **Управляемая сигнатура**  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 Несмотря на то, что с помощью атрибутов **size_is** или **length_is** массива в исходном коде на языке IDL можно передать сведения о размере клиенту, компилятор MIDL не передает эту информацию в библиотеку типов. Не зная размера, служба маршалинга взаимодействия не может маршалировать элементы массива. Таким образом, массивы переменной длины импортируются в виде ссылочных аргументов. Пример:  
  
 **Неуправляемая сигнатура**  
  
```cpp
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 **Управляемая сигнатура**  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 Чтобы предоставить размер массива маршалеру, можно изменить код на языке MSIL, создаваемый программой Tlbimp.exe, после чего повторно скомпилировать его. Дополнительные сведения об изменении кода MSIL см. в разделе [Настройка вызываемых оболочек времени выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100)). Чтобы указать число элементов в массиве, примените тип <xref:System.Runtime.InteropServices.MarshalAsAttribute> к параметру массива в определении управляемого метода одним из следующих способов:  
  
- Определите еще один параметр, который содержит число элементов в массиве. Параметры определяются по позиции, начиная с первого, который получает номер 0.     
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
- Определите размер массива в виде константы. Пример:  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 При маршалинге массивов из неуправляемого в управляемый код маршалер проверяет связанный с параметром атрибут **MarshalAsAttribute**, чтобы определить размер массива. Если размер массива не указан, выполняется маршалинг только одного элемента.  
  
> [!NOTE]
> Атрибут **MarshalAsAttribute** не учитывается при маршалинге управляемых массивов в неуправляемый код. В этом направлении размер массива определяется с помощью проверки. Маршалинг подмножества управляемого массива невозможен.  
  
 Маршалер взаимодействия использует методы **CoTaskMemAlloc** и **CoTaskMemFree** для выделения и высвобождения памяти. Эти методы также необходимо использовать при выделении памяти в неуправляемом коде.  
  
## <a name="passing-arrays-to-com"></a>Передача массивов в COM  
 Все типы управляемых массивов можно передавать в неуправляемый код из управляемого кода. В зависимости от управляемого типа и примененных к нему атрибутов, доступ к массиву осуществляется как к безопасному массиву или как к массиву в стиле C, как показано в следующей таблице.  
  
|Тип управляемого массива|Экспортируется как|  
|------------------------|-----------------|  
|**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Тип предоставляется в сигнатуре. Ранг всегда равен 1, а нижняя граница всегда — 0. Размер всегда известен во время выполнения.|  
|**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>** [ **\<** *bounds* **>** ]|**UnmanagedType.SafeArray(** *type* **)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Тип, ранг и границы предоставляются в сигнатуре. Размер всегда известен во время выполнения.|  
|**ELEMENT_TYPE_CLASS** **\<** <xref:System.Array?displayProperty=nameWithType> **>**|**UT_Interface**<br /><br /> **UnmanagedType.SafeArray(** *type* **)**<br /><br /> Тип, ранг, границы и размер всегда известны во время выполнения.|  
  
 В OLE-автоматизации существует ограничение в отношении массивов структур, которые содержат LPSTR или LPWSTR.  Таким образом, поля **String** должны маршалироваться как **UnmanagedType.BSTR**. В противном случае будет создаваться исключение.  
  
### <a name="element_type_szarray"></a>ELEMENT_TYPE_SZARRAY  
 При экспорте метода, содержащего параметр **ELEMENT_TYPE_SZARRAY** (одномерный массив), из сборки .NET в библиотеку типов параметр массива преобразуется в массив **SAFEARRAY** заданного типа. Те же правила преобразования применяются к типам элементов массива. Содержимое управляемого массива автоматически копируется из управляемой памяти в **SAFEARRAY**. Пример:  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Ранг безопасных массивов всегда равен 1, а нижняя граница —0. Размер определяется во время выполнения на основе размера передаваемого управляемого массива.  
  
 Массив также может маршалироваться как массив в стиле C с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Пример:  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(BSTR ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Несмотря на то, что маршалеру известна длина, необходимая для маршалинга массива, длина массива обычно передается вызываемому объекту в отдельном аргументе.  
  
### <a name="element_type_array"></a>ELEMENT_TYPE_ARRAY  
 При экспорте метода, содержащего параметр **ELEMENT_TYPE_ARRAY**, из сборки .NET в библиотеку типов параметр массива преобразуется в массив **SAFEARRAY** заданного типа. Содержимое управляемого массива автоматически копируется из управляемой памяти в **SAFEARRAY**. Пример:  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp
HRESULT New([in] SAFEARRAY( long ) ar);
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Ранг, размер и границы безопасного массива определяются во время выполнения на основе характеристик управляемого массива.  
  
 Массив также может маршалироваться как массив в стиле C с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Пример:  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp
HRESULT New(long ar[]);
HRESULT New(LPStr ar[]);  
```  
  
 Вложенные массивы не поддерживают маршалирование. Например, при экспорте с использованием [программы экспорта библиотеки типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) следующая сигнатура приводит к возникновению ошибки.  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="element_type_class-systemarray"></a>ELEMENT_TYPE_CLASS \<System.Array>  
 При экспорте метода, содержащего параметр <xref:System.Array?displayProperty=nameWithType>, из сборки .NET в библиотеку типов параметр массива преобразуется в интерфейс **_Array**. Содержимое этого управляемого массива доступно только через методы и свойства интерфейса **_Array**. Массив **System.Array** также может маршалироваться как **SAFEARRAY** с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute>. При маршалинге безопасного массива его элементы маршалируются как варианты. Пример:  
  
#### <a name="managed-signature"></a>Управляемая сигнатура  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp
HRESULT New([in] _Array *ar);
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a>Массивы внутри структур  
 Неуправляемые структуры могут содержать вложенные массивы. По умолчанию эти вложенные поля массива маршалируются как SAFEARRAY. В следующем примере `s1` — это вложенный массив, который выделяется непосредственно в структуре.  
  
#### <a name="unmanaged-representation"></a>Неуправляемое представление  
  
```cpp
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Массивы могут маршалироваться как <xref:System.Runtime.InteropServices.UnmanagedType>, для чего необходимо установить поле <xref:System.Runtime.InteropServices.MarshalAsAttribute>. Размер может задаваться только в виде константы. В коде ниже показаны соответствующие управляемые определения `MyStruct`.  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a>См. также

- [Характеристики маршалинга по умолчанию](default-marshaling-behavior.md)
- [Преобразуемые и непреобразуемые типы](blittable-and-non-blittable-types.md)
- [Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)
- [Копирование и закрепление](copying-and-pinning.md)
