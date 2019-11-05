---
title: Маршалинг по умолчанию для объектов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- objects, interop marshaling
- interop marshaling, objects
ms.assetid: c2ef0284-b061-4e12-b6d3-6a502b9cc558
ms.openlocfilehash: e0de715a3ed33eedf212fc3e0e9930c9cbaa0a38
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123589"
---
# <a name="default-marshaling-for-objects"></a>Маршалинг по умолчанию для объектов

Параметры и поля, типизированные как <xref:System.Object?displayProperty=nameWithType>, могут предоставляться в неуправляемый код в виде одного из следующих типов:

- Вариант, если объект является параметром.

- Интерфейс, если объект является полем структуры.

Маршалинг для типов объектов поддерживается только для COM-взаимодействия. По умолчанию выполняется маршалинг объектов в варианты COM. Эти правила применяются только к типу **Object** и не относятся к строго типизированным объектам, производным от класса **Object**.

## <a name="marshaling-options"></a>Маршалинг параметров

В следующей таблице показаны параметры маршалинга для типа данных **Object**. Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга объектов.

|Тип перечисления|Описание неуправляемого формата|
|----------------------|-------------------------------------|
|**UnmanagedType.Struct**<br /><br /> (по умолчанию для параметров)|Вариант в стиле COM.|
|**UnmanagedType.Interface**|Интерфейс **IDispatch**, если возможно. В противном случае интерфейс **IUnknown**.|
|**UnmanagedType.IUnknown**<br /><br /> (по умолчанию для полей)|Интерфейс **IUnknown**.|
|**UnmanagedType.IDispatch**|Интерфейс **IDispatch**.|

В следующем примере показано определение управляемого интерфейса для `MarshalObject`.

```vb
Interface MarshalObject
   Sub SetVariant(o As Object)
   Sub SetVariantRef(ByRef o As Object)
   Function GetVariant() As Object

   Sub SetIDispatch( <MarshalAs(UnmanagedType.IDispatch)> o As Object)
   Sub SetIDispatchRef(ByRef <MarshalAs(UnmanagedType.IDispatch)> o _
      As Object)
   Function GetIDispatch() As <MarshalAs(UnmanagedType.IDispatch)> Object
   Sub SetIUnknown( <MarshalAs(UnmanagedType.IUnknown)> o As Object)
   Sub SetIUnknownRef(ByRef <MarshalAs(UnmanagedType.IUnknown)> o _
      As Object)
   Function GetIUnknown() As <MarshalAs(UnmanagedType.IUnknown)> Object
End Interface
```

```csharp
interface MarshalObject {
   void SetVariant(Object o);
   void SetVariantRef(ref Object o);
   Object GetVariant();

   void SetIDispatch ([MarshalAs(UnmanagedType.IDispatch)]Object o);
   void SetIDispatchRef([MarshalAs(UnmanagedType.IDispatch)]ref Object o);
   [MarshalAs(UnmanagedType.IDispatch)] Object GetIDispatch();
   void SetIUnknown ([MarshalAs(UnmanagedType.IUnknown)]Object o);
   void SetIUnknownRef([MarshalAs(UnmanagedType.IUnknown)]ref Object o);
   [MarshalAs(UnmanagedType.IUnknown)] Object GetIUnknown();
}
```

Следующий пример кода экспортирует интерфейс `MarshalObject` в библиотеку типов.

```cpp
interface MarshalObject {
   HRESULT SetVariant([in] VARIANT o);
   HRESULT SetVariantRef([in,out] VARIANT *o);
   HRESULT GetVariant([out,retval] VARIANT *o)
   HRESULT SetIDispatch([in] IDispatch *o);
   HRESULT SetIDispatchRef([in,out] IDispatch **o);
   HRESULT GetIDispatch([out,retval] IDispatch **o)
   HRESULT SetIUnknown([in] IUnknown *o);
   HRESULT SetIUnknownRef([in,out] IUnknown **o);
   HRESULT GetIUnknown([out,retval] IUnknown **o)
}
```

> [!NOTE]
> Маршалер взаимодействия после вызова автоматически высвобождает любой выделенный объект внутри варианта.

В следующем примере показан форматированный тип значения.

```vb
Public Structure ObjectHolder
   Dim o1 As Object
   <MarshalAs(UnmanagedType.IDispatch)> Public o2 As Object
End Structure
```

```csharp
public struct ObjectHolder {
   Object o1;
   [MarshalAs(UnmanagedType.IDispatch)]public Object o2;
}
```

Следующий пример кода экспортирует форматированный тип в библиотеку типов.

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a>Маршалинг объекта в интерфейс

Если объект предоставляется модели COM в виде интерфейса, это будет интерфейс класса для управляемого типа <xref:System.Object> (интерфейс **_Object**). В полученной библиотеке типов этот интерфейс типизируется как **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) или **IUnknown** (**UnmanagedType.IUnknown**). Клиенты COM могут динамически вызывать члены управляемого класса или любые члены, реализуемые его производными классами, используя интерфейс **_Object**. Клиент также может вызывать **QueryInterface** для получения любого другого интерфейса, явно реализуемого управляемым типом.

## <a name="marshaling-object-to-variant"></a>Маршалинг объекта в вариант

При маршалинге объекта в вариант внутренний тип варианта определяется во время выполнения на основе следующих правил:

- Если ссылка на объект имеет значение NULL (**Nothing** в Visual Basic), выполняется маршалинг объекта в вариант типа **VT_EMPTY**.

- Если объект является экземпляром любого типа, представленного в следующей таблице, итоговый тип варианта определяется встроенными правилами маршалера, которые показаны в таблице.

- Другие объекты, которым требуется явное управление поведением маршалинга, могут реализовывать интерфейс <xref:System.IConvertible>. В этом случае тип варианта определяется в соответствии с кодом типа, возвращаемым из метода <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>. В противном случае выполняется маршалинг объекта в виде варианта типа **VT_UNKNOWN**.

### <a name="marshaling-system-types-to-variant"></a>Маршалинг системных типов в вариант

В следующей таблице показаны управляемые типы объектов и соответствующие им варианты модели COM. Эти типы преобразуются только в том случае, если сигнатура вызываемого метода относится к типу <xref:System.Object?displayProperty=nameWithType>.

|Тип объекта|Тип варианта COM|
|-----------------|----------------------|
|Ссылка на объект NULL (**Nothing** в Visual Basic).|**VT_EMPTY**|
|<xref:System.DBNull?displayProperty=nameWithType>|**VT_NULL**|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|**VT_ERROR**|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|**VT_ERROR** с **E_PARAMNOTFOUND**|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|**VT_DISPATCH**|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|**VT_UNKNOWN**|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|**VT_CY**|
|<xref:System.Boolean?displayProperty=nameWithType>|**VT_BOOL**|
|<xref:System.SByte?displayProperty=nameWithType>|**VT_I1**|
|<xref:System.Byte?displayProperty=nameWithType>|**VT_UI1**|
|<xref:System.Int16?displayProperty=nameWithType>|**VT_I2**|
|<xref:System.UInt16?displayProperty=nameWithType>|**VT_UI2**|
|<xref:System.Int32?displayProperty=nameWithType>|**VT_I4**|
|<xref:System.UInt32?displayProperty=nameWithType>|**VT_UI4**|
|<xref:System.Int64?displayProperty=nameWithType>|**VT_I8**|
|<xref:System.UInt64?displayProperty=nameWithType>|**VT_UI8**|
|<xref:System.Single?displayProperty=nameWithType>|**VT_R4**|
|<xref:System.Double?displayProperty=nameWithType>|**VT_R8**|
|<xref:System.Decimal?displayProperty=nameWithType>|**VT_DECIMAL**|
|<xref:System.DateTime?displayProperty=nameWithType>|**VT_DATE**|
|<xref:System.String?displayProperty=nameWithType>|**VT_BSTR**|
|<xref:System.IntPtr?displayProperty=nameWithType>|**VT_INT**|
|<xref:System.UIntPtr?displayProperty=nameWithType>|**VT_UINT**|
|<xref:System.Array?displayProperty=nameWithType>|**VT_ARRAY**|

В следующем примере кода с помощью интерфейса `MarshalObject` демонстрируется передача различных типов вариантов на COM-сервер.

```vb
Dim mo As New MarshalObject()
mo.SetVariant(Nothing)         ' Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value) ' Marshal as variant of type VT_NULL.
mo.SetVariant(CInt(27))        ' Marshal as variant of type VT_I2.
mo.SetVariant(CLng(27))        ' Marshal as variant of type VT_I4.
mo.SetVariant(CSng(27.0))      ' Marshal as variant of type VT_R4.
mo.SetVariant(CDbl(27.0))      ' Marshal as variant of type VT_R8.
```

```csharp
MarshalObject mo = new MarshalObject();
mo.SetVariant(null);            // Marshal as variant of type VT_EMPTY.
mo.SetVariant(System.DBNull.Value); // Marshal as variant of type VT_NULL.
mo.SetVariant((int)27);          // Marshal as variant of type VT_I2.
mo.SetVariant((long)27);          // Marshal as variant of type VT_I4.
mo.SetVariant((single)27.0);   // Marshal as variant of type VT_R4.
mo.SetVariant((double)27.0);   // Marshal as variant of type VT_R8.
```

Маршалинг типов COM, у которых нет соответствующих управляемых типов, может осуществляться с использованием классов-оболочек, таких как <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> и <xref:System.Runtime.InteropServices.CurrencyWrapper>. В следующем примере кода демонстрируется использование этих классов-оболочек для передачи различных типов вариантов на COM-сервер.

```vb
Imports System.Runtime.InteropServices
' Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(New UnknownWrapper(inew))
' Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(New DispatchWrapper(inew))
' Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(New ErrorWrapper(&H80054002))
' Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(New CurrencyWrapper(New Decimal(5.25)))
```

```csharp
using System.Runtime.InteropServices;
// Pass inew as a variant of type VT_UNKNOWN interface.
mo.SetVariant(new UnknownWrapper(inew));
// Pass inew as a variant of type VT_DISPATCH interface.
mo.SetVariant(new DispatchWrapper(inew));
// Pass a value as a variant of type VT_ERROR interface.
mo.SetVariant(new ErrorWrapper(0x80054002));
// Pass a value as a variant of type VT_CURRENCY interface.
mo.SetVariant(new CurrencyWrapper(new Decimal(5.25)));
```

Классы-оболочки определяются в пространстве имен <xref:System.Runtime.InteropServices>.

### <a name="marshaling-the-iconvertible-interface-to-variant"></a>Маршалинг интерфейса IConvertible в вариант

Типы, которые не приведены в предыдущем разделе, могут управлять маршалингом посредством реализации интерфейса <xref:System.IConvertible>. Если объект реализует интерфейс **IConvertible**, тип варианта COM определяется во время выполнения на основе значения перечисления <xref:System.TypeCode>, которое возвращается методом <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.

В следующей таблице показаны возможные значения перечисления **TypeCode** и соответствующие им типы вариантов COM.

|Код типа|Тип варианта COM|
|--------------|----------------------|
|**TypeCode.Empty**|**VT_EMPTY**|
|**TypeCode.Object**|**VT_UNKNOWN**|
|**TypeCode.DBNull**|**VT_NULL**|
|**TypeCode.Boolean**|**VT_BOOL**|
|**TypeCode.Char**|**VT_UI2**|
|**TypeCode.Sbyte**|**VT_I1**|
|**TypeCode.Byte**|**VT_UI1**|
|**TypeCode.Int16**|**VT_I2**|
|**TypeCode.UInt16**|**VT_UI2**|
|**TypeCode.Int32**|**VT_I4**|
|**TypeCode.UInt32**|**VT_UI4**|
|**TypeCode.Int64**|**VT_I8**|
|**TypeCode.UInt64**|**VT_UI8**|
|**TypeCode.Single**|**VT_R4**|
|**TypeCode.Double**|**VT_R8**|
|**TypeCode.Decimal**|**VT_DECIMAL**|
|**TypeCode.DateTime**|**VT_DATE**|
|**TypeCode.String**|**VT_BSTR**|
|Не поддерживается.|**VT_INT**|
|Не поддерживается.|**VT_UINT**|
|Не поддерживается.|**VT_ARRAY**|
|Не поддерживается.|**VT_RECORD**|
|Не поддерживается.|**VT_CY**|
|Не поддерживается.|**VT_VARIANT**|

Значение варианта COM определяется посредством вызова интерфейса **IConvertible.To** *Type*, в котором **To** *Type* — это подпрограмма преобразования, которая соответствует типу, возвращаемому из **IConvertible.GetTypeCode**. Например, объект, который возвращает **TypeCode.Double** из **IConvertible.GetTypeCode**, маршалируется как вариант COM типа **VT_R8**. Чтобы получить значение варианта (хранится в поле **dblVal** варианта COM), можно выполнить приведение к интерфейсу **IConvertible** и вызвать метод <xref:System.IConvertible.ToDouble%2A>.

## <a name="marshaling-variant-to-object"></a>Маршалинг варианта в объект

При маршалинге варианта в объект тип (а в некоторых случаях и значение) маршалированного варианта определяет тип получаемого объекта. В следующей таблице показаны типы вариантов и соответствующие им типы объектов, которые создаются маршалером при передаче варианта из COM в .NET Framework.

|Тип варианта COM|Тип объекта|
|----------------------|-----------------|
|**VT_EMPTY**|Ссылка на объект NULL (**Nothing** в Visual Basic).|
|**VT_NULL**|<xref:System.DBNull?displayProperty=nameWithType>|
|**VT_DISPATCH**|**System.__ComObject** или значение NULL если (pdispVal == null)|
|**VT_UNKNOWN**|**System.__ComObject** или значение NULL если (punkVal == null)|
|**VT_ERROR**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_BOOL**|<xref:System.Boolean?displayProperty=nameWithType>|
|**VT_I1**|<xref:System.SByte?displayProperty=nameWithType>|
|**VT_UI1**|<xref:System.Byte?displayProperty=nameWithType>|
|**VT_I2**|<xref:System.Int16?displayProperty=nameWithType>|
|**VT_UI2**|<xref:System.UInt16?displayProperty=nameWithType>|
|**VT_I4**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UI4**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_I8**|<xref:System.Int64?displayProperty=nameWithType>|
|**VT_UI8**|<xref:System.UInt64?displayProperty=nameWithType>|
|**VT_R4**|<xref:System.Single?displayProperty=nameWithType>|
|**VT_R8**|<xref:System.Double?displayProperty=nameWithType>|
|**VT_DECIMAL**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_DATE**|<xref:System.DateTime?displayProperty=nameWithType>|
|**VT_BSTR**|<xref:System.String?displayProperty=nameWithType>|
|**VT_INT**|<xref:System.Int32?displayProperty=nameWithType>|
|**VT_UINT**|<xref:System.UInt32?displayProperty=nameWithType>|
|**VT_ARRAY** &#124; **VT_** \*|<xref:System.Array?displayProperty=nameWithType>|
|**VT_CY**|<xref:System.Decimal?displayProperty=nameWithType>|
|**VT_RECORD**|Соответствующий тип упакованного значения.|
|**VT_VARIANT**|Не поддерживается.|

Типы вариантов, передаваемые из модели COM в управляемый код и обратно в COM, могут не сохранять тип варианта во время вызова. Рассмотрим, что произойдет при передаче типа варианта **VT_DISPATCH** из модели COM в .NET Framework. Во время маршалинга вариант преобразуется в <xref:System.Object?displayProperty=nameWithType>. Если затем **Object** возвращается в COM, выполняется его обратный маршалинг в вариант типа **VT_UNKNOWN**. При этом не гарантируется, что вариант, полученный при маршалинге объекта из управляемого кода в COM, будет иметь тот же тип, что и вариант, изначально использованный для создания объекта.

## <a name="marshaling-byref-variants"></a>Маршалинг вариантов ByRef

Сами по себе варианты могут передаваться по значению или по ссылке. Несмотря на это, также можно использовать флаг **VT_BYREF** с любым типом варианта, чтобы указать, что содержимое варианта передается по ссылке, а не по значению. Разница между маршалингом вариантов по ссылке и с установленным флагом **VT_BYREF** может показаться не очевидной. На следующем рисунке показаны различия между этими способами:

![Схема, показывающая вариант, передающийся по стеку.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)
Варианты, передаваемые по значению и по ссылке

**Поведение по умолчанию при маршалинге объектов и вариантов по значению**

- При передаче объектов из управляемого кода в COM содержимое объекта копируется в новый вариант, создаваемый маршалером, с использованием правил, которые определены в разделе [Маршалинг объекта в вариант](#marshaling-object-to-variant). Изменения, внесенные в вариант в неуправляемом коде, не применяются к исходному объекту после возврата из вызова.

- При передаче вариантов из COM в управляемый код содержимое варианта копируется в создаваемый объект с использованием правил, которые определены в разделе [Маршалинг варианта в объект](#marshaling-variant-to-object). Изменения, внесенные в объект в управляемом коде, не применяются к исходному варианту после возврата из вызова.

**Поведение по умолчанию при маршалинге объектов и вариантов по ссылке**

Для распространения изменений в вызывающем объекте параметры необходимо передавать по ссылке. Например, можно использовать ключевое слово **ref** в C# (или **ByRef** в управляемом коде Visual Basic) для передачи параметров по ссылке. В модели COM ссылочные параметры передаются с использованием указателя, например **variant \*** .

- При передаче объекта в COM по ссылке маршалер создает новый вариант и копирует содержимое ссылки на объект в вариант до того, как будет выполнен вызов. Вариант передается в неуправляемую функцию, в которой пользователь может изменять его содержимое. После возврата из вызова изменения, внесенные в вариант в неуправляемом коде, применяются к исходному объекту. Если тип варианта отличается от типа варианта, переданного в вызов, изменения применяются к объекту другого типа. Таким образом, тип переданного в вызов объекта может отличаться от типа объекта, возвращаемого из вызова.

- При передаче варианта в управляемый код по ссылке маршалер создает новый объект и копирует содержимое варианта в объект до того, как будет выполнен вызов. Ссылка на объект передается в управляемую функцию, в которой пользователь может изменять сам объект. После возврата из вызова изменения, внесенные в указываемый по ссылке объект, применяются к исходному варианту. Если тип объекта отличается от типа объекта, переданного в вызов, тип исходного варианта изменяется и значение передается обратно в вариант. Аналогичным образом, тип переданного в вызов варианта может отличаться от типа варианта, возвращаемого из вызова.

 **Поведение по умолчанию при маршалинге варианта с установленным флагом VT_BYREF**

- Для варианта, передаваемого в управляемый код по значению, может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит ссылку вместо значения. В этом случае вариант по-прежнему маршалируется в объект, поскольку вариант передается по значению. Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов. После этого объект передается в управляемую функцию. Тем не менее при возврате из вызова объект не применяется к исходному варианту. Изменения, внесенные в управляемый объект, утрачиваются.

  > [!CAUTION]
  > Изменить значение варианта, переданного по значению, нельзя, даже если для варианта установлен флаг **VT_BYREF**.

- Для варианта, передаваемого в управляемый код по ссылке, также может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит еще одну ссылку. В этом случае вариант маршалируется в объект **ref**, поскольку вариант передается по ссылке. Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов. При возврате из вызова значение объекта возвращается по ссылке с исходным вариантом только в том случае, если тип объекта совпадает с типом переданного объекта. Таким образом, при передаче не изменяется тип варианта с установленным флагом **VT_BYREF**. Если во время вызова тип объекта изменяется, при возврате из него возникает исключение <xref:System.InvalidCastException>.

В следующей таблице описываются общие правила распространения для вариантов и объектов.

|Исходный тип|Целевой тип|Возвращаемые изменения|
|----------|--------|-----------------------------|
|**Вариант**  *v*|**Объект**  *o*|Никогда|
|**Объект**  *o*|**Вариант**  *v*|Никогда|
|**Вариант**   ***\****  *pv*|**Ссылочный объект**  *o*|Всегда|
|**Ссылочный объект**  *o*|**Вариант**   ***\****  *pv*|Всегда|
|**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_\*)**|**Объект**  *o*|Никогда|
|**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_)**|**Ссылочный объект**  *o*|Только если тип не был изменен.|

## <a name="see-also"></a>См. также

- [Характеристики маршалинга по умолчанию](default-marshaling-behavior.md)
- [Преобразуемые и непреобразуемые типы](blittable-and-non-blittable-types.md)
- [Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)
- [Копирование и закрепление](copying-and-pinning.md)
