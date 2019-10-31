---
title: Поведение маршалинга по умолчанию
ms.date: 06/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
ms.openlocfilehash: abb8b507b21ca8f40461192c37e6c2fbe73b684e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123605"
---
# <a name="default-marshaling-behavior"></a>Поведение маршалинга по умолчанию
Маршалинг взаимодействия работает по правилам, которые определяют поведение данных, связанных с параметрами метода, при их передаче между управляемой и неуправляемой памятью. Эти встроенные правила определяют такие операции маршалинга, как преобразования типов данных, возможность изменения вызываемым объектом переданных ему данных и возврата этих изменений вызывающему объекту, а также обстоятельства, при которых упаковщик обеспечивает оптимизацию производительности.  
  
 В этом разделе описаны стандартные характеристики службы маршалинга взаимодействия. Представлены подробные сведения о маршалинге массивов, логических типов, символьных типов, делегатов, классов, объектов, строк и структур.  
  
> [!NOTE]
> Маршалинг универсальных типов не поддерживается. Дополнительные сведения см. в разделе [Взаимодействие с помощью универсальных типов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229590(v=vs.100)).  
  
## <a name="memory-management-with-the-interop-marshaler"></a>Управление памятью с помощью упаковщика взаимодействия  
 Упаковщик взаимодействия всегда пытается освободить память, распределенную неуправляемым кодом. Такое поведение согласуется с правилами управления памятью COM, но отличается от правил, присущих C++.  
  
 Путаница может возникать, если ожидается поведение в стиле C++ (память не освобождается) при вызове неуправляемого кода, при котором память автоматически освобождается для указателей. Например, вызов приведенного ниже неуправляемого метода из библиотеки DLL C++ не освобождает память автоматически.  
  
### <a name="unmanaged-signature"></a>Неуправляемая сигнатура  
  
```cpp  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 Однако если при определении метода в качестве прототипа вызова неуправляемого кода заменить каждый тип **BSTR** на тип <xref:System.String> и вызвать `MethodOne`, среда CLR дважды попытается освободить `b`. Поведение маршалинга можно изменить с помощью типов <xref:System.IntPtr>, а не типов **String**.  
  
 Среда выполнения всегда использует метод **CoTaskMemFree** для освобождения памяти. Если память, с которой работает программа, не была выделена с помощью метода **CoTaskMemAlloc**, то необходимо использовать **IntPtr** и освободить память вручную с применением подходящего метода. Аналогичным образом можно избежать автоматического освобождения памяти в ситуациях, когда память ни при каких обстоятельствах не должна освобождаться, например при использовании функции **GetCommandLine** из Kernel32.dll, которая возвращает указатель в память ядра. Подробнее об освобождении памяти вручную см. в разделе [Пример буферов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x3txb6xc(v=vs.100)).  
  
## <a name="default-marshaling-for-classes"></a>Маршалинг по умолчанию для классов  
 Маршалинг классов может выполняться только с помощью COM-взаимодействия и только в качестве интерфейсов. Иногда интерфейс, используемый для маршалинга класса, называют интерфейсом класса. Подробнее о переопределении интерфейса класса другим выбранным интерфейсом см. в статье [Introducing the class interface](../../standard/native-interop/com-callable-wrapper.md#introducing-the-class-interface) (Введение в интерфейс класса).  
  
### <a name="passing-classes-to-com"></a>Передача классов в COM  
 При передаче управляемого класса в COM упаковщик взаимодействия автоматически инкапсулирует этот класс, используя COM-прокси, и передает интерфейс класса, полученный с помощью прокси, в вызов метода COM. Затем прокси делегирует все вызовы для интерфейса класса назад в управляемый объект. Прокси также предоставляет другие интерфейсы, которые не реализованы классом явным образом. Прокси от имени класса автоматически реализует такие интерфейсы, как **IUnknown** и **IDispatch**.  
  
### <a name="passing-classes-to-net-code"></a>Передача классов в код .NET  
 В COM коклассы обычно не используются в качестве аргументов метода. Вместо кокласса обычно передается интерфейс по умолчанию.  
  
 При передаче интерфейса в управляемый код упаковщик взаимодействия отвечает за инкапсуляцию интерфейса в соответствующую оболочку и за передачу этой оболочки в управляемый метод. Выбор используемой оболочки может вызывать затруднения. У каждого экземпляра COM-объекта есть одна уникальная оболочка вне зависимости от числа интерфейсов, реализуемых объектом. Например, COM-объект, реализующий пять различных интерфейсов, имеет только одну оболочку. Одна и та же оболочка предоставляет все пять интерфейсов. Если создаются два экземпляра COM-объекта, то создаются и два экземпляра оболочки.  
  
 Чтобы тип оболочки не менялся в течение всего времени ее существования, упаковщик взаимодействия должен выбрать правильную оболочку при первой передаче интерфейса, предоставляемого данным объектом, через упаковщик. Упаковщик идентифицирует объект, просматривая один из интерфейсов, реализуемых объектом.  
  
 Например, упаковщик определяет, что оболочка класса должна использоваться для инкапсуляции интерфейса, переданного в управляемый код. При первой передаче этого интерфейса через упаковщик последний проверяет, поступил ли этот интерфейс от известного объекта. Эта проверка выполняется в двух случаях:  
  
- Интерфейс реализуется другим управляемым объектом, переданным в COM где-то в другом месте. Упаковщик может легко идентифицировать интерфейсы, предоставляемые управляемыми объектами, и может находить соответствие между интерфейсом и управляемым объектом, предоставившим реализацию. Затем управляемый объект передается в метод, и никакой оболочки не требуется.  
  
- Интерфейс реализуется объектом, который уже инкапсулирован. Чтобы определить, так ли это, упаковщик запрашивает у объекта его интерфейс **IUnknown** и сравнивает возвращенный интерфейс с интерфейсами других, уже инкапсулированных объектов. Если интерфейс совпадает с интерфейсом другой оболочки, то объекты имеют одинаковые идентификаторы и существующая оболочка передается методу.  
  
 Если интерфейс не является интерфейсом известного объекта, упаковщик выполняет указанные ниже действия.  
  
1. Упаковщик запрашивает у объекта интерфейс **IProvideClassInfo2**. Если он предоставлен, то упаковщик использует значение CLSID, возвращенное из **IProvideClassInfo2.GetGUID**, для идентификации кокласса, предоставляющего интерфейс. Используя идентификатор CLSID, упаковщик может найти оболочку в реестре, если перед этим сборка была зарегистрирована.  
  
2. Упаковщик запрашивает у этого интерфейса интерфейс **IProvideClassInfo**. Если он предоставлен, упаковщик использует интерфейс **ITypeInfo**, возвращенный из метода **IProvideClassInfo.GetClassinfo**, для определения значения CLSID класса, предоставляющего интерфейс. Упаковщик может использовать значение CLSID для нахождения метаданных оболочки.  
  
3. Если упаковщик все еще не может идентифицировать класс, то он инкапсулирует интерфейс в оболочку универсального класса с именем **System.__ComObject**.  
  
## <a name="default-marshaling-for-delegates"></a>Маршалинг по умолчанию для делегатов  
 Управляемый делегат маршалируется как COM-интерфейс или как указатель на функцию на основе описанного ниже механизма вызовов.  
  
- Для вызова неуправляемого кода делегат по умолчанию маршалируется как указатель на функцию.  
  
- Для COM-взаимодействия делегат по умолчанию маршалируется как COM-интерфейс типа **_Delegate**. Интерфейс **_Delegate** определяется в библиотеке типов Mscorlib.tlb и содержит метод <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType>, который позволяет вызывать метод, на который ссылается делегат.  
  
 В таблице ниже показаны варианты маршалинга для типа данных управляемого делегата. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга делегатов.  
  
|Тип перечисления|Описание неуправляемого формата|  
|----------------------|-------------------------------------|  
|**UnmanagedType.FunctionPtr**|Указатель на неуправляемую функцию.|  
|**UnmanagedType.Interface**|Интерфейс типа **_Delegate**, как определено в Mscorlib.tlb.|  
  
 Рассмотрим пример кода, в котором методы `DelegateTestInterface` экспортируются в библиотеку типов COM. Обратите внимание на то, что только делегаты, помеченные ключевым словом **ref** (или **ByRef**), передаются как параметры In/Out.  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);     
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);    
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);   
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);     
}  
```  
  
### <a name="type-library-representation"></a>Представление библиотеки типов  
  
```cpp  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 Указатель на функцию может быть разыменован, так же как и любой другой указатель на неуправляемую функцию.  

В этом примере при маршалировании двух делегатов в качестве <xref:System.Runtime.InteropServices.UnmanagedType.FunctionPtr?displayProperty=nameWithType> будет получен результат `int` и указатель на `int`. Поскольку типы делегатов маршалируются, `int` здесь представляет указатель на void (`void*`), то есть адрес делегата в памяти. Другими словами, этот результат относится к 32-разрядным системам Windows, поскольку `int` здесь представляет размер указателя на функцию.

> [!NOTE]
> Ссылка на указатель на функцию в управляемом делегате, хранимая в неуправляемом коде, не препятствует выполнению средой CLR сборки мусора для управляемого объекта.  
  
 Например, приведенный ниже код некорректен, так как ссылка на объект `cb`, передаваемая методу `SetChangeHandler`, не сохраняет объект `cb` в активном состоянии по окончании времени существования метода `Test`. После применения к объекту `cb` процедуры сборки мусора указатель на функцию, переданный в `SetChangeHandler`, становится недействительным.  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the   
      // object from being garbage collected after the Main method   
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));     
   }  
}  
```  
  
 Чтобы компенсировать неожиданную сборку мусора, вызывающий объект должен гарантировать, что объект `cb` будет находиться в активном состоянии до тех пор, пока используется указатель на неуправляемую функцию. Как показано в примере ниже, при необходимости можно настроить передачу уведомлений от неуправляемого кода в управляемый о том, что указатель на функцию больше не нужен.  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is   
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a>Маршалинг по умолчанию для типов значений  
 Большинство типов значений, такие как целые числа и числа с плавающей запятой, являются [непреобразуемыми](blittable-and-non-blittable-types.md) и не требуют маршалинга. [Преобразуемые](blittable-and-non-blittable-types.md) типы представлены в управляемой и неуправляемой памяти по-разному и требуют маршалинга. Другие типы требуют явного форматирования при пересечении границы взаимодействия.  
  
 В этом разделе представлены сведения о следующих форматированных типах значений:  
  
- [Типы значений, используемые в вызове неуправляемого кода](#value-types-used-in-platform-invoke)  
  
- [Типы значений, используемые в COM-взаимодействии](#value-types-used-in-com-interop)  
  
 Кроме описания форматированных типов, в этом разделе определяются [системные типы значений](#system-value-types), имеющие нестандартное поведение маршалинга.  
  
 Форматированный тип — это сложный тип, который содержит информацию, явным образом определяющую размещение его членов в памяти. Сведения о размещении членов предоставляются с помощью атрибута <xref:System.Runtime.InteropServices.StructLayoutAttribute>. Размещение может принимать одно из указанных ниже значений перечисления <xref:System.Runtime.InteropServices.LayoutKind>.  
  
- **LayoutKind.Automatic**  
  
     Указывает, что среда CLR для повышения эффективности может свободно изменять порядок членов типа. Тем не менее, когда тип значения передается в неуправляемый код, размещение членов является предсказуемым. При попытке маршалинга такой структуры автоматически вызывается исключение.  
  
- **LayoutKind.Sequential**  
  
     Указывает, что члены типа должны размещаться в неуправляемой памяти в том же порядке, в котором они появляются в определении управляемого типа.  
  
- **LayoutKind.Explicit**  
  
     Указывает, что члены располагаются в соответствии с атрибутом <xref:System.Runtime.InteropServices.FieldOffsetAttribute>, предоставляемым с каждым полем.  
  
### <a name="value-types-used-in-platform-invoke"></a>Типы значений, используемые в вызове неуправляемого кода  
 В примере ниже типы `Point` и `Rect` предоставляют сведения о размещении членов с помощью атрибута **StructLayoutAttribute**.  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
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
```  
  
 При маршалинге в неуправляемый код эти форматированные типы маршалируются как структуры стиля C. Это обеспечивает простой способ вызова неуправляемого интерфейса API с аргументами в виде структур. Например, структуры `POINT` и `RECT` могут передаваться в функцию **PtInRect** Microsoft Windows API следующим образом:  
  
```cpp  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Вы можете передать структуры с помощью следующего определения вызова неуправляемого кода:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "User32.dll" (
        ByRef r As Rect, p As Point) As Boolean
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("User32.dll")]
   internal static extern bool PtInRect(ref Rect r, Point p);
}
```
  
 Тип значения `Rect` должен передаваться по ссылке, потому что неуправляемый интерфейс API ожидает, что в функцию будет передан указатель на `RECT`. Тип значения `Point` передается по значению, так как неуправляемый интерфейс API ожидает, что `POINT` будет передан в стек. Это небольшое различие очень важно. Ссылки передаются в неуправляемый код как указатели. Значения передаются в неуправляемый код в стеке.  
  
> [!NOTE]
> При маршалинге форматированного типа в виде структуры доступны только поля внутри этого типа. Если у типа есть методы, свойства или события, то они недоступны из неуправляемого кода.  
  
 Классы тоже можно маршалировать в неуправляемый код как структуры стиля языка С при условии, что они имеют фиксированное размещение членов. Сведения о размещении членов класса также предоставляются с помощью атрибута <xref:System.Runtime.InteropServices.StructLayoutAttribute>. Основное различие между типами значений с фиксированным размещением и классами с фиксированным размещением заключает в способе маршалинга в неуправляемый код. Типы значений передаются по значению (в стеке), поэтому любые изменения, внесенные в члены этого типа вызываемым объектом, не видны вызывающему объекту. Ссылочные типы передаются по ссылке (ссылка на тип передается в стеке). Поэтому все изменения, внесенные в члены непреобразуемого типа вызываемым объектом, видны вызывающему объекту.  
  
> [!NOTE]
> Если ссылочный тип содержит члены преобразуемого типа, преобразование должно выполняться дважды: первый раз — при передаче аргумента неуправляемой стороне, а второй раз — при возврате из вызова. В связи с появлением дополнительных издержек параметры In/Out необходимо применять к аргументу в явном виде, если вызывающий объект должен учитывать изменения, внесенные вызываемым объектом.  
  
 В примере ниже класс `SystemTime` имеет последовательное размещение членов и может быть передан в функцию **GetSystemTime** API Windows.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;   
   public ushort wMonth;  
   public ushort wDayOfWeek;   
   public ushort wDay;   
   public ushort wHour;   
   public ushort wMinute;   
   public ushort wSecond;   
   public ushort wMilliseconds;   
}  
```  
  
 Функция **GetSystemTime** определяется следующим образом:  
  
```cpp  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 Эквивалентное определение вызова неуправляемого кода **GetSystemTime** выглядит следующим образом:  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        ByVal sysTime As SystemTime)
End Class
```
  
```csharp
internal static class NativeMethods
{
   [DllImport("Kernel32.dll", CharSet = CharSet.Auto)]
   internal static extern void GetSystemTime(SystemTime st);
}
```
  
 Обратите внимание на то, что аргумент `SystemTime` не типизирован как ссылочный аргумент, потому что `SystemTime` — это класс, а не тип значения. В отличие от типов значений, классы всегда передаются по ссылке.  
  
 В примере кода ниже показан другой класс `Point`, который содержит метод с именем `SetXY`. Так как этот тип имеет последовательную компоновку, он может быть передан в неуправляемый код и маршалирован как структура. Однако член `SetXY` нельзя вызвать из неуправляемого кода, даже когда объект передается по ссылке.  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){   
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
### <a name="value-types-used-in-com-interop"></a>Типы значений, используемые во COM-взаимодействии  
 Форматированные типы могут также передаваться в вызовы метода COM-взаимодействия. Фактически при экспорте в библиотеку типов типы значений автоматически преобразуются в структуры. Как показано в примере ниже, тип значения `Point` становится определением типа (typedef) с именем `Point`. Все ссылки на тип значения `Point` в любом другом месте библиотеки типов заменяются на определение типа typedef `Point`.  
  
 **Представление библиотеки типов**  
  
```cpp  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 Те же самые правила, которые используются для маршалинга значений и ссылок в вызовы неуправляемого кода, применяются и при маршалинге через COM-интерфейсы. Например, когда экземпляр типа значения `Point` передается из .NET Framework в COM, `Point` передается по значению. Если тип значения `Point` передается по ссылке, указатель на `Point` передается в стеке. Упаковщик взаимодействия не поддерживает более высокие уровни косвенного обращения (**Point** \*\*) в любом направлении.  
  
> [!NOTE]
> Структуры, для которых значение перечисления <xref:System.Runtime.InteropServices.LayoutKind> установлено равным **Explicit**, не могут использоваться в COM-взаимодействии, так как экспортированная библиотека типов не может представлять явное размещение.  
  
### <a name="system-value-types"></a>Системные типы значений  
 Пространство имен <xref:System> содержит несколько типов значений, представляющих собой упакованную форму простых типов среды выполнения. Например, структура типов значений <xref:System.Int32?displayProperty=nameWithType> представляет собой упакованную форму **ELEMENT_TYPE_I4**. Вместо маршалинга этих типов в качестве структур, как в случае с другими форматированными типами, их следует маршалировать так же, как и соответствующие простые типы. Соответственно, **System.Int32** маршалируется как **ELEMENT_TYPE_I4**, а не как структура, содержащая один член типа **long**. В таблице ниже приведен список типов значений в пространстве имен **System**, являющихся упакованными представлениями простых типов.  
  
|Системный тип значения|Тип элемента|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|**ELEMENT_TYPE_BOOLEAN**|  
|<xref:System.SByte?displayProperty=nameWithType>|**ELEMENT_TYPE_I1**|  
|<xref:System.Byte?displayProperty=nameWithType>|**ELEMENT_TYPE_UI1**|  
|<xref:System.Char?displayProperty=nameWithType>|**ELEMENT_TYPE_CHAR**|  
|<xref:System.Int16?displayProperty=nameWithType>|**ELEMENT_TYPE_I2**|  
|<xref:System.UInt16?displayProperty=nameWithType>|**ELEMENT_TYPE_U2**|  
|<xref:System.Int32?displayProperty=nameWithType>|**ELEMENT_TYPE_I4**|  
|<xref:System.UInt32?displayProperty=nameWithType>|**ELEMENT_TYPE_U4**|  
|<xref:System.Int64?displayProperty=nameWithType>|**ELEMENT_TYPE_I8**|  
|<xref:System.UInt64?displayProperty=nameWithType>|**ELEMENT_TYPE_U8**|  
|<xref:System.Single?displayProperty=nameWithType>|**ELEMENT_TYPE_R4**|  
|<xref:System.Double?displayProperty=nameWithType>|**ELEMENT_TYPE_R8**|  
|<xref:System.String?displayProperty=nameWithType>|**ELEMENT_TYPE_STRING**|  
|<xref:System.IntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_I**|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|**ELEMENT_TYPE_U**|  
  
 Некоторые типы значений в пространстве имен **System** обрабатываются по-другому. Так как неуправляемый код уже имеет хорошо определенные форматы для таких типов, у упаковщика есть специальные правила для их маршалинга. В таблице ниже представлен список этих специальных типов значений в пространстве имен **System**, а также неуправляемых типов, в которые они маршалируются.  
  
|Системный тип значения|Тип IDL|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|**DATE**|  
|<xref:System.Decimal?displayProperty=nameWithType>|**DECIMAL**|  
|<xref:System.Guid?displayProperty=nameWithType>|**GUID**|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|**OLE_COLOR**|  
  
 В приведенном ниже коде показано определение неуправляемых типов **DATE**, **GUID**, **DECIMAL** и **OLE_COLOR** в библиотеке типов Stdole2.  
  
#### <a name="type-library-representation"></a>Представление библиотеки типов  
  
```cpp  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 В коде ниже показаны соответствующие определения в управляемом интерфейсе `IValueTypes`.  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a>Представление библиотеки типов  
  
```cpp  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a>См. также

- [Преобразуемые и непреобразуемые типы](blittable-and-non-blittable-types.md)
- [Копирование и закрепление](copying-and-pinning.md)
- [Маршалинг по умолчанию для массивов](default-marshaling-for-arrays.md)
- [Маршалинг по умолчанию для объектов](default-marshaling-for-objects.md)
- [Маршалинг по умолчанию для строк](default-marshaling-for-strings.md)
