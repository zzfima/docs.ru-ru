---
title: "Default Marshaling for Arrays | Microsoft Docs"
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
  - "interop marshaling, arrays"
  - "arrays, interop marshaling"
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Default Marshaling for Arrays
В приложении, целиком состоящем из управляемого кода, среда CLR передает типы массивов как параметры In\/Out.  В противоположность этому, упаковщик взаимодействия по умолчанию передает массив как параметры In.  
  
 При использовании [оптимизации закрепления](../../../docs/framework/interop/copying-and-pinning.md) непреобразуемый тип при взаимодействии с объектами в том же подразделении может выглядеть \(с точки зрения обработки\) как параметр In\/Out.  Но, если позднее экспортировать этот код в библиотеку типов, использованную для создания межкомпьютерного посредника и использовать эту библиотеку для маршалинга вызовов между подразделениями, эти вызовы могут вернуться к истинному поведению параметра In.  
  
 Массивы сложны по своей природе, и различия между управляемым и неуправляемым массивами обуславливают необходимость большего количества данных, чем для других преобразуемых типов.  В данном разделе представлены следующие сведения о маршалинге массивов.  
  
-   [Управляемые массивы](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [Неуправляемые массивы](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [Передача параметров массива в код .NET](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [Передача массивов в COM](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## Управляемые массивы  
 Типы управляемых массивов могут быть различны, но базовым классом для всех типов массивов является класс <xref:System.Array?displayProperty=fullName>.  В классе **System.Array** предусмотрены свойства для определения ранга, длины и верхней и нижней границ массива, а также методы для доступа, сортировки, поиска, копирования и создания массивов.  
  
 Эти типы массива являются динамическими и не имеют соответствующих статических типов, определенных в библиотеке базовых классов.  Каждое сочетание типа элемента и ранга удобно представлять себе как отдельный тип массива.  Таким образом, одномерный массив целых чисел и одномерный массив чисел двойной точности — это разные типы.  Аналогично двумерный массив целых чисел отличается от одномерного массива целых чисел.  При сравнении типов границы массива не учитываются.  
  
 Как показано в следующей таблице, любой экземпляр управляемого массива должен описываться определенным набором данных: тип элемента, ранг и нижняя граница.  
  
|Тип управляемого массива|Тип элемента|Ранг|Нижняя граница|Запись сигнатуры|  
|------------------------------|------------------|----------|--------------------|----------------------|  
|**ELEMENT\_TYPE\_ARRAY**|Задается типом.|Задается рангом.|Задается границами \(необязательно\)|*type* **\[** *n*,*m* **\]**|  
|**ELEMENT\_TYPE\_CLASS**|Нет данных|Нет данных|Нет данных|**System.Array**|  
|**ELEMENT\_TYPE\_SZARRAY**|Задается типом.|1|0|*type* **\[** *n* **\]**|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## Неуправляемые массивы  
 Неуправляемые массивы — это любые безопасные массивы в COM\-стиле или массивы в стиле языка C с фиксированной или переменной длиной.  Безопасные массивы — это массивы с самоописанием, хранящие данные о своем типе, ранге и границах связанного массива.  Массивы в стиле языка C — это одномерные типизированные массивы с фиксированной нижней границей, равной 0.  Служба маршалинга обеспечивает ограниченную поддержку для обоих типов массивов.  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## Передача параметров массива в код .NET  
 И массив в стиле языка C, и безопасный массив можно передать в код .NET из неуправляемого кода либо как безопасный массив, либо как массив в стиле языка C.  В следующей таблице показаны значение неуправляемого типа и импортированный тип.  
  
|Неуправляемый тип|Импортированный тип|  
|-----------------------|-------------------------|  
|**SafeArray\(** *Type* **\)**|**ELEMENT\_TYPE\_SZARRAY** **\<** *ПреобразованныйТип* **\>**<br /><br /> Ранг \= 1, нижняя граница \= 0.  Размер известен только в том случае, если он указан в управляемой сигнатуре.  Маршалинг в **SZARRAY** безопасных массивов, ранг которых не равна 1 или нижняя граница не равна 0, не может быть выполнен.|  
|*Type*  **\[\]**|**ELEMENT\_TYPE\_SZARRAY** **\<** *ПреобразованныйТип* **\>**<br /><br /> Ранг \= 1, нижняя граница \= 0.  Размер известен только в том случае, если он указан в управляемой сигнатуре.|  
  
### Безопасные массивы  
 При импорте безопасного массива из библиотеки типов в сборку .NET он преобразуется в одномерный массив известного типа \(такого как **int**\).  Те же самые правила преобразования типов, которые применяются для параметров, применимы и к элементам массива.  Например, безопасный массив элементов типа **BSTR** становится управляемым массивом строк, а безопасный массив типа variant становится управляемым массивом объектов.  Тип элемента **SAFEARRAY** извлекается и библиотеки типов и сохраняется в значении **SAFEARRAY** перечисления <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
 Поскольку ранг и границы безопасного массива не могут быть определены по информации из библиотеки типов, предполагается, что ранг равен 1, а нижняя граница равна 0.  Ранг и границы должны быть определены в управляемой сигнатуре, которая создается [программой импорта библиотек типов \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).  В случае отличия ранг, переданного в метод во время выполнения, вызывается исключение <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>.  Если тип массива, переданный во время выполнения, оказывается иным, вызывается исключение <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>.  В следующем примере показаны безопасные массивы в управляемом и неуправляемом кодах.  
  
 **Неуправляемая сигнатура**  
  
```  
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
  
 Маршалинг многомерных массивов или массивов с ненулевой нижней границей в управляемый код может быть выполнен, если сигнатура метода, полученная с помощью Tlbimp.exe, изменена таким образом, чтобы она показывала тип элемента **ELEMENT\_TYPE\_ARRAY** вместо **ELEMENT\_TYPE\_SZARRAY**.  Либо можно использовать переключатель **\/sysarray** с программой Tlbimp.exe, чтобы импортировать все массивы как объекты <xref:System.Array?displayProperty=fullName>.  В тех случаях, когда известно, что передаваемый массив является многомерным, можно исправить код на промежуточном языке MSIL, созданный Tlbimp.exe, и затем перекомпилировать его.  Сведения об изменении кода на языке MSIL см. в разделе [Настройка вызываемых оболочек времени выполнения](http://msdn.microsoft.com/ru-ru/4652beaf-77d0-4f37-9687-ca193288c0be).  
  
### Массивы в стиле языка C  
 При импорте массива в стиле языка C из библиотеки типов в сборку .NET он преобразуется в **ELEMENT\_TYPE\_SZARRAY**.  
  
 Тип элемента массива определяется из библиотеки типов и сохраняется в течение импорта.  Те же самые правила, которые применяются для параметров, применимы и к элементам массива.  Например, массив типов **LPStr** становится массивом типов **String**.  Tlbimp.exe извлекает тип элементов массива и применяет к этому параметру атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  
  
 Ранг массива полагается равным 1.  Если ранг больше 1, массив маршалируется как одномерный с соблюдением порядка по столбцам.  Нижняя граница всегда равна 0.  
  
 Библиотеки типов могут содержать массивы фиксированной или переменной длины.  Tlbimp.exe может импортировать из библиотек типов только массивы фиксированной длины, потому что в библиотеках отсутствуют сведения, необходимые для маршалинга массивов переменной длины.  Для массивов фиксированной длины размер импортируется из библиотеки типов и сохраняется в атрибуте **MarshalAsAttribute**, применяемом к параметру.  
  
 Библиотеки типов, содержащие массивы переменной длины, необходимо описать вручную, как показано в примере ниже.  
  
 **Неуправляемая сигнатура**  
  
```  
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
  
 Хотя для передачи размера клиенту к массиву в исходном коде на языке IDL можно применить атрибуты **size\_is** или **length\_is**, компилятор языка MIDL не передает эти данные в библиотеку типов.  Без знания размера служба маршалинга взаимодействия не может выполнить маршалинг элементов массива.  Соответственно, массивы переменной длины импортируются как ссылочные аргументы.  Примеры.  
  
 **Неуправляемая сигнатура**  
  
```  
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
  
 Размер массива можно предоставить упаковщику, отредактировав код на промежуточном языке MSIL, полученный с помощью Tlbimp.exe, и затем перекомпилировав его.  Сведения об изменении кода на языке MSIL см. в разделе [Настройка вызываемых оболочек времени выполнения](http://msdn.microsoft.com/ru-ru/4652beaf-77d0-4f37-9687-ca193288c0be).  Чтобы указать число элементов в массиве, следует применить тип <xref:System.Runtime.InteropServices.MarshalAsAttribute> к параметру массива в определении управляемого метода одним из следующих способов:  
  
-   Определите другой параметр, содержащий число элементов в массиве.  Параметры идентифицируются по позиции, начиная с первого параметра, которому приписывается позиция 0.  \[Visual Basic\]  
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       <MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   Определите размер массива как константу.  Примеры.  
  
    ```vb  
    Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 При маршалинге массивов из неуправляемого в управляемый код упаковщик, чтобы определить размер массива, проверяет атрибут **MarshalAsAttribute**, связанный с параметром.  Если размер массива не задан, выполняется маршалинг только одного элемента.  
  
> [!NOTE]
>  Атрибут **MarshalAsAttribute** не влияет на маршалинг управляемых массивов в неуправляемый код.  В этом направлении размер массива определяется с помощью проверки.  Не существует способа выполнить маршалинг части управляемого массива.  
  
 Упаковщик взаимодействия использует методы **CoTaskMemAlloc** и **CoTaskMemFree** для выделения и освобождения памяти.  Выделение памяти, выполняемое неуправляемым кодом, также должно использовать эти методы.  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## Передача массивов в COM  
 Все типы управляемых массивов могут передаваться в неуправляемый код из управляемого кода.  Как показано в следующей таблице, в зависимости от управляемого типа и примененных к нему атрибутов, доступ к массиву может быть осуществлен как к безопасному массиву или как к массиву в стиле языка C.  
  
|Тип управляемого массива|Экспортируется как|  
|------------------------------|------------------------|  
|**ELEMENT\_TYPE\_SZARRAY** **\<** *тип* **\>**|<xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Тип предоставляется в сигнатуре.  Ранг всегда равен 1, нижняя граница всегда равна 0.  Размер всегда известен во время выполнения.|  
|**ELEMENT\_TYPE\_ARRAY** **\<** *тип* **\>** **\<** *ранг* **\>**\[**\<** *граница* **\>**\]|**UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> **UnmanagedType.LPArray**<br /><br /> Тип, ранг и границы предоставляются в сигнатуре.  Размер всегда известен во время выполнения.|  
|**ELEMENT\_TYPE\_CLASS** **\<**<xref:System.Array?displayProperty=fullName>**\>**|**UT\_Interface**<br /><br /> **UnmanagedType.SafeArray\(** *type* **\)**<br /><br /> Тип, ранг, границы и размер всегда известны во время выполнения.|  
  
 У OLE\-автоматизации имеется ограничение, связанное с массивами структур, которые содержат LPSTR или LPWSTR.  Поэтому поля **String** должны маршалироваться как **UnmanagedType.BSTR**.  В противном случае будет создаваться исключение.  
  
### ELEMENT\_TYPE\_SZARRAY  
 При экспорте метода, содержащего параметр **ELEMENT\_TYPE\_SZARRAY** \(одномерный массив\) из сборки .NET в библиотеку типов, этот параметр массива преобразуется в **SAFEARRAY** заданного типа.  Те же самые правила преобразования применимы к типам элемента массива.  Содержимое управляемого массива автоматически копируется из управляемой памяти в **SAFEARRAY**.  Примеры.  
  
#### Управляемая сигнатура  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### Неуправляемая сигнатура  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Ранг безопасных массивов всегда равен 1, а нижняя граница всегда равна 0.  Размер определяется во время выполнения по размеру передаваемого управляемого массива.  
  
 С помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> массив также может быть маршалирован как массив стиля C.  Примеры.  
  
#### Управляемая сигнатура  
  
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
  
#### Неуправляемая сигнатура  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 Хотя этот упаковщик обладает сведениями о длине, необходимыми для маршалинга массива, длина массива обычно передается как отдельный аргумент, сообщающий эту длину вызываемому объекту.  
  
### ELEMENT\_TYPE\_ARRAY  
 При экспорте метода, содержащего параметр **ELEMENT\_TYPE\_ARRAY** из сборки .NET в библиотеку типов, этот параметр массива преобразуется в **SAFEARRAY** заданного типа.  Содержимое управляемого массива автоматически копируется из управляемой памяти в **SAFEARRAY**.  Примеры.  
  
#### Управляемая сигнатура  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### Неуправляемая сигнатура  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 Ранг, размер и границы безопасных массивов определяются во время выполнения из характеристик управляемого массива.  
  
 С помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> массив также может быть маршалирован как массив стиля C.  Примеры.  
  
#### Управляемая сигнатура  
  
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
  
#### Неуправляемая сигнатура  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 Маршалинг вложенных массивов невозможен.  Например, следующая сигнатура вызовет ошибку при экспорте с помощью [программы экспорта библиотеки типов \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).  
  
#### Управляемая сигнатура  
  
```vb  
Sub [New](ar()()() As Long)  
  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### ELEMENT\_TYPE\_CLASS \<System.Array\>  
 При экспорте метода, содержащего параметр <xref:System.Array?displayProperty=fullName>, из сборки .NET в библиотеку типов, этот параметр массива преобразуется в интерфейс **\_Array**.  Содержимое этого управляемого массива доступно только через методы и свойства интерфейса **\_Array**.  **System.Array** также может быть маршалирован как **SAFEARRAY** с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  При маршалинге в качестве безопасного массива элементы массива упаковываются и передаются как объекты variant.  Примеры.  
  
#### Управляемая сигнатура  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### Неуправляемая сигнатура  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### Массивы внутри структур  
 Неуправляемые структуры могут содержать вложенные массивы.  По умолчанию эти вложенные поля массива маршалируются как SAFEARRAY.  В следующем примере `s1` — это вложенный массив, распределенный непосредственно в самой структуре.  
  
#### Неуправляемое представление  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 Массивы могут быть маршалированы как [UnmanagedType.ByValArray](frlrfSystemRuntimeInteropServicesUnmanagedTypeClassTopic), что требует от разработчика установки поля [MarshalAsAttribute.SizeConst](frlrfSystemRuntimeInteropServicesMarshalAsAttributeClassTopic).  Размер может быть передан только как константа.  В следующем коде представлено соответствующее управляемое определение `MyStruct`.  
  
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
  
## См. также  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)   
 [Directional Attributes](http://msdn.microsoft.com/ru-ru/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md)