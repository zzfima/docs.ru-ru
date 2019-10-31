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
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="09ea2-102">Маршалинг по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="09ea2-102">Default Marshaling for Objects</span></span>

<span data-ttu-id="09ea2-103">Параметры и поля, типизированные как <xref:System.Object?displayProperty=nameWithType>, могут предоставляться в неуправляемый код в виде одного из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="09ea2-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>

- <span data-ttu-id="09ea2-104">Вариант, если объект является параметром.</span><span class="sxs-lookup"><span data-stu-id="09ea2-104">A variant when the object is a parameter.</span></span>

- <span data-ttu-id="09ea2-105">Интерфейс, если объект является полем структуры.</span><span class="sxs-lookup"><span data-stu-id="09ea2-105">An interface when the object is a structure field.</span></span>

<span data-ttu-id="09ea2-106">Маршалинг для типов объектов поддерживается только для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="09ea2-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="09ea2-107">По умолчанию выполняется маршалинг объектов в варианты COM.</span><span class="sxs-lookup"><span data-stu-id="09ea2-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="09ea2-108">Эти правила применяются только к типу **Object** и не относятся к строго типизированным объектам, производным от класса **Object**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>

## <a name="marshaling-options"></a><span data-ttu-id="09ea2-109">Маршалинг параметров</span><span class="sxs-lookup"><span data-stu-id="09ea2-109">Marshaling Options</span></span>

<span data-ttu-id="09ea2-110">В следующей таблице показаны параметры маршалинга для типа данных **Object**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-110">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="09ea2-111">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга объектов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-111">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>

|<span data-ttu-id="09ea2-112">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="09ea2-112">Enumeration type</span></span>|<span data-ttu-id="09ea2-113">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="09ea2-113">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="09ea2-114">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="09ea2-114">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="09ea2-115">(по умолчанию для параметров)</span><span class="sxs-lookup"><span data-stu-id="09ea2-115">(default for parameters)</span></span>|<span data-ttu-id="09ea2-116">Вариант в стиле COM.</span><span class="sxs-lookup"><span data-stu-id="09ea2-116">A COM-style variant.</span></span>|
|<span data-ttu-id="09ea2-117">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="09ea2-117">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="09ea2-118">Интерфейс **IDispatch**, если возможно. В противном случае интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-118">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|
|<span data-ttu-id="09ea2-119">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="09ea2-119">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="09ea2-120">(по умолчанию для полей)</span><span class="sxs-lookup"><span data-stu-id="09ea2-120">(default for fields)</span></span>|<span data-ttu-id="09ea2-121">Интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-121">An **IUnknown** interface.</span></span>|
|<span data-ttu-id="09ea2-122">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="09ea2-122">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="09ea2-123">Интерфейс **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-123">An **IDispatch** interface.</span></span>|

<span data-ttu-id="09ea2-124">В следующем примере показано определение управляемого интерфейса для `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="09ea2-124">The following example shows the managed interface definition for `MarshalObject`.</span></span>

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

<span data-ttu-id="09ea2-125">Следующий пример кода экспортирует интерфейс `MarshalObject` в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-125">The following code exports the `MarshalObject` interface to a type library.</span></span>

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
> <span data-ttu-id="09ea2-126">Маршалер взаимодействия после вызова автоматически высвобождает любой выделенный объект внутри варианта.</span><span class="sxs-lookup"><span data-stu-id="09ea2-126">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>

<span data-ttu-id="09ea2-127">В следующем примере показан форматированный тип значения.</span><span class="sxs-lookup"><span data-stu-id="09ea2-127">The following example shows a formatted value type.</span></span>

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

<span data-ttu-id="09ea2-128">Следующий пример кода экспортирует форматированный тип в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-128">The following code exports the formatted type to a type library.</span></span>

```cpp
struct ObjectHolder {
   VARIANT o1;
   IDispatch *o2;
}
```

## <a name="marshaling-object-to-interface"></a><span data-ttu-id="09ea2-129">Маршалинг объекта в интерфейс</span><span class="sxs-lookup"><span data-stu-id="09ea2-129">Marshaling Object to Interface</span></span>

<span data-ttu-id="09ea2-130">Если объект предоставляется модели COM в виде интерфейса, это будет интерфейс класса для управляемого типа <xref:System.Object> (интерфейс **_Object**).</span><span class="sxs-lookup"><span data-stu-id="09ea2-130">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="09ea2-131">В полученной библиотеке типов этот интерфейс типизируется как **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) или **IUnknown** (**UnmanagedType.IUnknown**).</span><span class="sxs-lookup"><span data-stu-id="09ea2-131">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="09ea2-132">Клиенты COM могут динамически вызывать члены управляемого класса или любые члены, реализуемые его производными классами, используя интерфейс **_Object**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-132">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="09ea2-133">Клиент также может вызывать **QueryInterface** для получения любого другого интерфейса, явно реализуемого управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="09ea2-133">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>

## <a name="marshaling-object-to-variant"></a><span data-ttu-id="09ea2-134">Маршалинг объекта в вариант</span><span class="sxs-lookup"><span data-stu-id="09ea2-134">Marshaling Object to Variant</span></span>

<span data-ttu-id="09ea2-135">При маршалинге объекта в вариант внутренний тип варианта определяется во время выполнения на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="09ea2-135">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>

- <span data-ttu-id="09ea2-136">Если ссылка на объект имеет значение NULL (**Nothing** в Visual Basic), выполняется маршалинг объекта в вариант типа **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-136">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>

- <span data-ttu-id="09ea2-137">Если объект является экземпляром любого типа, представленного в следующей таблице, итоговый тип варианта определяется встроенными правилами маршалера, которые показаны в таблице.</span><span class="sxs-lookup"><span data-stu-id="09ea2-137">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>

- <span data-ttu-id="09ea2-138">Другие объекты, которым требуется явное управление поведением маршалинга, могут реализовывать интерфейс <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-138">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="09ea2-139">В этом случае тип варианта определяется в соответствии с кодом типа, возвращаемым из метода <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-139">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="09ea2-140">В противном случае выполняется маршалинг объекта в виде варианта типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-140">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>

### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="09ea2-141">Маршалинг системных типов в вариант</span><span class="sxs-lookup"><span data-stu-id="09ea2-141">Marshaling System Types to Variant</span></span>

<span data-ttu-id="09ea2-142">В следующей таблице показаны управляемые типы объектов и соответствующие им варианты модели COM.</span><span class="sxs-lookup"><span data-stu-id="09ea2-142">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="09ea2-143">Эти типы преобразуются только в том случае, если сигнатура вызываемого метода относится к типу <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-143">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>

|<span data-ttu-id="09ea2-144">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="09ea2-144">Object type</span></span>|<span data-ttu-id="09ea2-145">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="09ea2-145">COM variant type</span></span>|
|-----------------|----------------------|
|<span data-ttu-id="09ea2-146">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="09ea2-146">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="09ea2-147">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-147">**VT_EMPTY**</span></span>|
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="09ea2-148">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-148">**VT_NULL**</span></span>|
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="09ea2-149">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="09ea2-149">**VT_ERROR**</span></span>|
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="09ea2-150">**VT_ERROR** с **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="09ea2-150">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="09ea2-151">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="09ea2-151">**VT_DISPATCH**</span></span>|
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="09ea2-152">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="09ea2-152">**VT_UNKNOWN**</span></span>|
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="09ea2-153">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-153">**VT_CY**</span></span>|
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="09ea2-154">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-154">**VT_BOOL**</span></span>|
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="09ea2-155">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-155">**VT_I1**</span></span>|
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="09ea2-156">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-156">**VT_UI1**</span></span>|
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="09ea2-157">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-157">**VT_I2**</span></span>|
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="09ea2-158">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-158">**VT_UI2**</span></span>|
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="09ea2-159">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-159">**VT_I4**</span></span>|
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="09ea2-160">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-160">**VT_UI4**</span></span>|
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="09ea2-161">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-161">**VT_I8**</span></span>|
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="09ea2-162">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-162">**VT_UI8**</span></span>|
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="09ea2-163">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-163">**VT_R4**</span></span>|
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="09ea2-164">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-164">**VT_R8**</span></span>|
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="09ea2-165">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-165">**VT_DECIMAL**</span></span>|
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="09ea2-166">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="09ea2-166">**VT_DATE**</span></span>|
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="09ea2-167">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="09ea2-167">**VT_BSTR**</span></span>|
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="09ea2-168">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-168">**VT_INT**</span></span>|
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="09ea2-169">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-169">**VT_UINT**</span></span>|
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="09ea2-170">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-170">**VT_ARRAY**</span></span>|

<span data-ttu-id="09ea2-171">В следующем примере кода с помощью интерфейса `MarshalObject` демонстрируется передача различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="09ea2-171">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>

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

<span data-ttu-id="09ea2-172">Маршалинг типов COM, у которых нет соответствующих управляемых типов, может осуществляться с использованием классов-оболочек, таких как <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> и <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-172">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="09ea2-173">В следующем примере кода демонстрируется использование этих классов-оболочек для передачи различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="09ea2-173">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>

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

<span data-ttu-id="09ea2-174">Классы-оболочки определяются в пространстве имен <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-174">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>

### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="09ea2-175">Маршалинг интерфейса IConvertible в вариант</span><span class="sxs-lookup"><span data-stu-id="09ea2-175">Marshaling the IConvertible Interface to Variant</span></span>

<span data-ttu-id="09ea2-176">Типы, которые не приведены в предыдущем разделе, могут управлять маршалингом посредством реализации интерфейса <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-176">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="09ea2-177">Если объект реализует интерфейс **IConvertible**, тип варианта COM определяется во время выполнения на основе значения перечисления <xref:System.TypeCode>, которое возвращается методом <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-177">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="09ea2-178">В следующей таблице показаны возможные значения перечисления **TypeCode** и соответствующие им типы вариантов COM.</span><span class="sxs-lookup"><span data-stu-id="09ea2-178">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>

|<span data-ttu-id="09ea2-179">Код типа</span><span class="sxs-lookup"><span data-stu-id="09ea2-179">TypeCode</span></span>|<span data-ttu-id="09ea2-180">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="09ea2-180">COM variant type</span></span>|
|--------------|----------------------|
|<span data-ttu-id="09ea2-181">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="09ea2-181">**TypeCode.Empty**</span></span>|<span data-ttu-id="09ea2-182">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-182">**VT_EMPTY**</span></span>|
|<span data-ttu-id="09ea2-183">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="09ea2-183">**TypeCode.Object**</span></span>|<span data-ttu-id="09ea2-184">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="09ea2-184">**VT_UNKNOWN**</span></span>|
|<span data-ttu-id="09ea2-185">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="09ea2-185">**TypeCode.DBNull**</span></span>|<span data-ttu-id="09ea2-186">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-186">**VT_NULL**</span></span>|
|<span data-ttu-id="09ea2-187">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="09ea2-187">**TypeCode.Boolean**</span></span>|<span data-ttu-id="09ea2-188">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-188">**VT_BOOL**</span></span>|
|<span data-ttu-id="09ea2-189">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="09ea2-189">**TypeCode.Char**</span></span>|<span data-ttu-id="09ea2-190">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-190">**VT_UI2**</span></span>|
|<span data-ttu-id="09ea2-191">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="09ea2-191">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="09ea2-192">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-192">**VT_I1**</span></span>|
|<span data-ttu-id="09ea2-193">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="09ea2-193">**TypeCode.Byte**</span></span>|<span data-ttu-id="09ea2-194">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-194">**VT_UI1**</span></span>|
|<span data-ttu-id="09ea2-195">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="09ea2-195">**TypeCode.Int16**</span></span>|<span data-ttu-id="09ea2-196">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-196">**VT_I2**</span></span>|
|<span data-ttu-id="09ea2-197">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="09ea2-197">**TypeCode.UInt16**</span></span>|<span data-ttu-id="09ea2-198">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-198">**VT_UI2**</span></span>|
|<span data-ttu-id="09ea2-199">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="09ea2-199">**TypeCode.Int32**</span></span>|<span data-ttu-id="09ea2-200">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-200">**VT_I4**</span></span>|
|<span data-ttu-id="09ea2-201">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="09ea2-201">**TypeCode.UInt32**</span></span>|<span data-ttu-id="09ea2-202">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-202">**VT_UI4**</span></span>|
|<span data-ttu-id="09ea2-203">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="09ea2-203">**TypeCode.Int64**</span></span>|<span data-ttu-id="09ea2-204">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-204">**VT_I8**</span></span>|
|<span data-ttu-id="09ea2-205">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="09ea2-205">**TypeCode.UInt64**</span></span>|<span data-ttu-id="09ea2-206">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-206">**VT_UI8**</span></span>|
|<span data-ttu-id="09ea2-207">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="09ea2-207">**TypeCode.Single**</span></span>|<span data-ttu-id="09ea2-208">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-208">**VT_R4**</span></span>|
|<span data-ttu-id="09ea2-209">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="09ea2-209">**TypeCode.Double**</span></span>|<span data-ttu-id="09ea2-210">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-210">**VT_R8**</span></span>|
|<span data-ttu-id="09ea2-211">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="09ea2-211">**TypeCode.Decimal**</span></span>|<span data-ttu-id="09ea2-212">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-212">**VT_DECIMAL**</span></span>|
|<span data-ttu-id="09ea2-213">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="09ea2-213">**TypeCode.DateTime**</span></span>|<span data-ttu-id="09ea2-214">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="09ea2-214">**VT_DATE**</span></span>|
|<span data-ttu-id="09ea2-215">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="09ea2-215">**TypeCode.String**</span></span>|<span data-ttu-id="09ea2-216">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="09ea2-216">**VT_BSTR**</span></span>|
|<span data-ttu-id="09ea2-217">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-217">Not supported.</span></span>|<span data-ttu-id="09ea2-218">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-218">**VT_INT**</span></span>|
|<span data-ttu-id="09ea2-219">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-219">Not supported.</span></span>|<span data-ttu-id="09ea2-220">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-220">**VT_UINT**</span></span>|
|<span data-ttu-id="09ea2-221">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-221">Not supported.</span></span>|<span data-ttu-id="09ea2-222">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-222">**VT_ARRAY**</span></span>|
|<span data-ttu-id="09ea2-223">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-223">Not supported.</span></span>|<span data-ttu-id="09ea2-224">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="09ea2-224">**VT_RECORD**</span></span>|
|<span data-ttu-id="09ea2-225">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-225">Not supported.</span></span>|<span data-ttu-id="09ea2-226">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-226">**VT_CY**</span></span>|
|<span data-ttu-id="09ea2-227">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-227">Not supported.</span></span>|<span data-ttu-id="09ea2-228">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-228">**VT_VARIANT**</span></span>|

<span data-ttu-id="09ea2-229">Значение варианта COM определяется посредством вызова интерфейса **IConvertible.To** *Type*, в котором **To** *Type* — это подпрограмма преобразования, которая соответствует типу, возвращаемому из **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-229">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="09ea2-230">Например, объект, который возвращает **TypeCode.Double** из **IConvertible.GetTypeCode**, маршалируется как вариант COM типа **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-230">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="09ea2-231">Чтобы получить значение варианта (хранится в поле **dblVal** варианта COM), можно выполнить приведение к интерфейсу **IConvertible** и вызвать метод <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-231">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>

## <a name="marshaling-variant-to-object"></a><span data-ttu-id="09ea2-232">Маршалинг варианта в объект</span><span class="sxs-lookup"><span data-stu-id="09ea2-232">Marshaling Variant to Object</span></span>

<span data-ttu-id="09ea2-233">При маршалинге варианта в объект тип (а в некоторых случаях и значение) маршалированного варианта определяет тип получаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="09ea2-233">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="09ea2-234">В следующей таблице показаны типы вариантов и соответствующие им типы объектов, которые создаются маршалером при передаче варианта из COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09ea2-234">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>

|<span data-ttu-id="09ea2-235">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="09ea2-235">COM variant type</span></span>|<span data-ttu-id="09ea2-236">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="09ea2-236">Object type</span></span>|
|----------------------|-----------------|
|<span data-ttu-id="09ea2-237">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-237">**VT_EMPTY**</span></span>|<span data-ttu-id="09ea2-238">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="09ea2-238">Null object reference (**Nothing** in Visual Basic).</span></span>|
|<span data-ttu-id="09ea2-239">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-239">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-240">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="09ea2-240">**VT_DISPATCH**</span></span>|<span data-ttu-id="09ea2-241">**System.__ComObject** или значение NULL если (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="09ea2-241">**System.__ComObject** or null if (pdispVal == null)</span></span>|
|<span data-ttu-id="09ea2-242">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="09ea2-242">**VT_UNKNOWN**</span></span>|<span data-ttu-id="09ea2-243">**System.__ComObject** или значение NULL если (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="09ea2-243">**System.__ComObject** or null if (punkVal == null)</span></span>|
|<span data-ttu-id="09ea2-244">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="09ea2-244">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-245">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-245">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-246">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-246">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-247">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="09ea2-247">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-248">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-248">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-249">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="09ea2-249">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-250">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-250">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-251">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-251">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-252">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-252">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-253">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-253">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-254">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="09ea2-254">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-255">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="09ea2-255">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-256">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="09ea2-256">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-257">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="09ea2-257">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-258">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="09ea2-258">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-259">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-259">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-260">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-260">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-261">**VT_ARRAY** &#124; **VT_** \*</span><span class="sxs-lookup"><span data-stu-id="09ea2-261">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-262">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="09ea2-262">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|
|<span data-ttu-id="09ea2-263">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="09ea2-263">**VT_RECORD**</span></span>|<span data-ttu-id="09ea2-264">Соответствующий тип упакованного значения.</span><span class="sxs-lookup"><span data-stu-id="09ea2-264">Corresponding boxed value type.</span></span>|
|<span data-ttu-id="09ea2-265">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="09ea2-265">**VT_VARIANT**</span></span>|<span data-ttu-id="09ea2-266">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="09ea2-266">Not supported.</span></span>|

<span data-ttu-id="09ea2-267">Типы вариантов, передаваемые из модели COM в управляемый код и обратно в COM, могут не сохранять тип варианта во время вызова.</span><span class="sxs-lookup"><span data-stu-id="09ea2-267">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="09ea2-268">Рассмотрим, что произойдет при передаче типа варианта **VT_DISPATCH** из модели COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09ea2-268">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="09ea2-269">Во время маршалинга вариант преобразуется в <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-269">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="09ea2-270">Если затем **Object** возвращается в COM, выполняется его обратный маршалинг в вариант типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-270">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="09ea2-271">При этом не гарантируется, что вариант, полученный при маршалинге объекта из управляемого кода в COM, будет иметь тот же тип, что и вариант, изначально использованный для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="09ea2-271">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>

## <a name="marshaling-byref-variants"></a><span data-ttu-id="09ea2-272">Маршалинг вариантов ByRef</span><span class="sxs-lookup"><span data-stu-id="09ea2-272">Marshaling ByRef Variants</span></span>

<span data-ttu-id="09ea2-273">Сами по себе варианты могут передаваться по значению или по ссылке. Несмотря на это, также можно использовать флаг **VT_BYREF** с любым типом варианта, чтобы указать, что содержимое варианта передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="09ea2-273">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="09ea2-274">Разница между маршалингом вариантов по ссылке и с установленным флагом **VT_BYREF** может показаться не очевидной.</span><span class="sxs-lookup"><span data-stu-id="09ea2-274">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="09ea2-275">На следующем рисунке показаны различия между этими способами:</span><span class="sxs-lookup"><span data-stu-id="09ea2-275">The following illustration clarifies the differences:</span></span>

<span data-ttu-id="09ea2-276">![Схема, показывающая вариант, передающийся по стеку.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span><span class="sxs-lookup"><span data-stu-id="09ea2-276">![Diagram that shows variant passed on the stack.](./media/default-marshaling-for-objects/interop-variant-passed-value-reference.gif)</span></span>
<span data-ttu-id="09ea2-277">Варианты, передаваемые по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="09ea2-277">Variants passed by value and by reference</span></span>

<span data-ttu-id="09ea2-278">**Поведение по умолчанию при маршалинге объектов и вариантов по значению**</span><span class="sxs-lookup"><span data-stu-id="09ea2-278">**Default behavior for marshaling objects and variants by value**</span></span>

- <span data-ttu-id="09ea2-279">При передаче объектов из управляемого кода в COM содержимое объекта копируется в новый вариант, создаваемый маршалером, с использованием правил, которые определены в разделе [Маршалинг объекта в вариант](#marshaling-object-to-variant).</span><span class="sxs-lookup"><span data-stu-id="09ea2-279">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#marshaling-object-to-variant).</span></span> <span data-ttu-id="09ea2-280">Изменения, внесенные в вариант в неуправляемом коде, не применяются к исходному объекту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="09ea2-280">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>

- <span data-ttu-id="09ea2-281">При передаче вариантов из COM в управляемый код содержимое варианта копируется в создаваемый объект с использованием правил, которые определены в разделе [Маршалинг варианта в объект](#marshaling-variant-to-object).</span><span class="sxs-lookup"><span data-stu-id="09ea2-281">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#marshaling-variant-to-object).</span></span> <span data-ttu-id="09ea2-282">Изменения, внесенные в объект в управляемом коде, не применяются к исходному варианту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="09ea2-282">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>

<span data-ttu-id="09ea2-283">**Поведение по умолчанию при маршалинге объектов и вариантов по ссылке**</span><span class="sxs-lookup"><span data-stu-id="09ea2-283">**Default behavior for marshaling objects and variants by reference**</span></span>

<span data-ttu-id="09ea2-284">Для распространения изменений в вызывающем объекте параметры необходимо передавать по ссылке.</span><span class="sxs-lookup"><span data-stu-id="09ea2-284">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="09ea2-285">Например, можно использовать ключевое слово **ref** в C# (или **ByRef** в управляемом коде Visual Basic) для передачи параметров по ссылке.</span><span class="sxs-lookup"><span data-stu-id="09ea2-285">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="09ea2-286">В модели COM ссылочные параметры передаются с использованием указателя, например **variant \*** .</span><span class="sxs-lookup"><span data-stu-id="09ea2-286">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>

- <span data-ttu-id="09ea2-287">При передаче объекта в COM по ссылке маршалер создает новый вариант и копирует содержимое ссылки на объект в вариант до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-287">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="09ea2-288">Вариант передается в неуправляемую функцию, в которой пользователь может изменять его содержимое.</span><span class="sxs-lookup"><span data-stu-id="09ea2-288">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="09ea2-289">После возврата из вызова изменения, внесенные в вариант в неуправляемом коде, применяются к исходному объекту.</span><span class="sxs-lookup"><span data-stu-id="09ea2-289">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="09ea2-290">Если тип варианта отличается от типа варианта, переданного в вызов, изменения применяются к объекту другого типа.</span><span class="sxs-lookup"><span data-stu-id="09ea2-290">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="09ea2-291">Таким образом, тип переданного в вызов объекта может отличаться от типа объекта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="09ea2-291">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>

- <span data-ttu-id="09ea2-292">При передаче варианта в управляемый код по ссылке маршалер создает новый объект и копирует содержимое варианта в объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-292">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="09ea2-293">Ссылка на объект передается в управляемую функцию, в которой пользователь может изменять сам объект.</span><span class="sxs-lookup"><span data-stu-id="09ea2-293">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="09ea2-294">После возврата из вызова изменения, внесенные в указываемый по ссылке объект, применяются к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="09ea2-294">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="09ea2-295">Если тип объекта отличается от типа объекта, переданного в вызов, тип исходного варианта изменяется и значение передается обратно в вариант.</span><span class="sxs-lookup"><span data-stu-id="09ea2-295">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="09ea2-296">Аналогичным образом, тип переданного в вызов варианта может отличаться от типа варианта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="09ea2-296">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>

 <span data-ttu-id="09ea2-297">**Поведение по умолчанию при маршалинге варианта с установленным флагом VT_BYREF**</span><span class="sxs-lookup"><span data-stu-id="09ea2-297">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>

- <span data-ttu-id="09ea2-298">Для варианта, передаваемого в управляемый код по значению, может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит ссылку вместо значения.</span><span class="sxs-lookup"><span data-stu-id="09ea2-298">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="09ea2-299">В этом случае вариант по-прежнему маршалируется в объект, поскольку вариант передается по значению.</span><span class="sxs-lookup"><span data-stu-id="09ea2-299">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="09ea2-300">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-300">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="09ea2-301">После этого объект передается в управляемую функцию. Тем не менее при возврате из вызова объект не применяется к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="09ea2-301">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="09ea2-302">Изменения, внесенные в управляемый объект, утрачиваются.</span><span class="sxs-lookup"><span data-stu-id="09ea2-302">Changes made to the managed object are lost.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="09ea2-303">Изменить значение варианта, переданного по значению, нельзя, даже если для варианта установлен флаг **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-303">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>

- <span data-ttu-id="09ea2-304">Для варианта, передаваемого в управляемый код по ссылке, также может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит еще одну ссылку.</span><span class="sxs-lookup"><span data-stu-id="09ea2-304">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="09ea2-305">В этом случае вариант маршалируется в объект **ref**, поскольку вариант передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="09ea2-305">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="09ea2-306">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="09ea2-307">При возврате из вызова значение объекта возвращается по ссылке с исходным вариантом только в том случае, если тип объекта совпадает с типом переданного объекта.</span><span class="sxs-lookup"><span data-stu-id="09ea2-307">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="09ea2-308">Таким образом, при передаче не изменяется тип варианта с установленным флагом **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="09ea2-308">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="09ea2-309">Если во время вызова тип объекта изменяется, при возврате из него возникает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="09ea2-309">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>

<span data-ttu-id="09ea2-310">В следующей таблице описываются общие правила распространения для вариантов и объектов.</span><span class="sxs-lookup"><span data-stu-id="09ea2-310">The following table summarizes the propagation rules for variants and objects.</span></span>

|<span data-ttu-id="09ea2-311">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="09ea2-311">From</span></span>|<span data-ttu-id="09ea2-312">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="09ea2-312">To</span></span>|<span data-ttu-id="09ea2-313">Возвращаемые изменения</span><span class="sxs-lookup"><span data-stu-id="09ea2-313">Changes propagated back</span></span>|
|----------|--------|-----------------------------|
|<span data-ttu-id="09ea2-314">**Вариант**  *v*</span><span class="sxs-lookup"><span data-stu-id="09ea2-314">**Variant**  *v*</span></span>|<span data-ttu-id="09ea2-315">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-315">**Object**  *o*</span></span>|<span data-ttu-id="09ea2-316">Никогда</span><span class="sxs-lookup"><span data-stu-id="09ea2-316">Never</span></span>|
|<span data-ttu-id="09ea2-317">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-317">**Object**  *o*</span></span>|<span data-ttu-id="09ea2-318">**Вариант**  *v*</span><span class="sxs-lookup"><span data-stu-id="09ea2-318">**Variant**  *v*</span></span>|<span data-ttu-id="09ea2-319">Никогда</span><span class="sxs-lookup"><span data-stu-id="09ea2-319">Never</span></span>|
|<span data-ttu-id="09ea2-320">**Вариант**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="09ea2-320">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="09ea2-321">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-321">**Ref Object**  *o*</span></span>|<span data-ttu-id="09ea2-322">Всегда</span><span class="sxs-lookup"><span data-stu-id="09ea2-322">Always</span></span>|
|<span data-ttu-id="09ea2-323">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-323">**Ref object**  *o*</span></span>|<span data-ttu-id="09ea2-324">**Вариант**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="09ea2-324">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="09ea2-325">Всегда</span><span class="sxs-lookup"><span data-stu-id="09ea2-325">Always</span></span>|
|<span data-ttu-id="09ea2-326">**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="09ea2-326">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="09ea2-327">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-327">**Object**  *o*</span></span>|<span data-ttu-id="09ea2-328">Никогда</span><span class="sxs-lookup"><span data-stu-id="09ea2-328">Never</span></span>|
|<span data-ttu-id="09ea2-329">**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="09ea2-329">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="09ea2-330">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="09ea2-330">**Ref Object**  *o*</span></span>|<span data-ttu-id="09ea2-331">Только если тип не был изменен.</span><span class="sxs-lookup"><span data-stu-id="09ea2-331">Only if the type has not changed.</span></span>|

## <a name="see-also"></a><span data-ttu-id="09ea2-332">См. также</span><span class="sxs-lookup"><span data-stu-id="09ea2-332">See also</span></span>

- [<span data-ttu-id="09ea2-333">Характеристики маршалинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="09ea2-333">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="09ea2-334">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="09ea2-334">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="09ea2-335">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100)) (Атрибуты направления)</span><span class="sxs-lookup"><span data-stu-id="09ea2-335">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="09ea2-336">Копирование и закрепление</span><span class="sxs-lookup"><span data-stu-id="09ea2-336">Copying and Pinning</span></span>](copying-and-pinning.md)
