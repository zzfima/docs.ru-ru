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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94377fb2079689e7b6af2c94fa24ca2214a5c729
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2018
ms.locfileid: "34312187"
---
# <a name="default-marshaling-for-objects"></a><span data-ttu-id="72d80-102">Маршалинг по умолчанию для объектов</span><span class="sxs-lookup"><span data-stu-id="72d80-102">Default Marshaling for Objects</span></span>
<span data-ttu-id="72d80-103">Параметры и поля, типизированные как <xref:System.Object?displayProperty=nameWithType>, могут предоставляться в неуправляемый код в виде одного из следующих типов:</span><span class="sxs-lookup"><span data-stu-id="72d80-103">Parameters and fields typed as <xref:System.Object?displayProperty=nameWithType> can be exposed to unmanaged code as one of the following types:</span></span>  
  
-   <span data-ttu-id="72d80-104">Вариант, если объект является параметром.</span><span class="sxs-lookup"><span data-stu-id="72d80-104">A variant when the object is a parameter.</span></span>  
  
-   <span data-ttu-id="72d80-105">Интерфейс, если объект является полем структуры.</span><span class="sxs-lookup"><span data-stu-id="72d80-105">An interface when the object is a structure field.</span></span>  
  
 <span data-ttu-id="72d80-106">Маршалинг для типов объектов поддерживается только для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="72d80-106">Only COM interop supports marshaling for object types.</span></span> <span data-ttu-id="72d80-107">По умолчанию выполняется маршалинг объектов в варианты COM.</span><span class="sxs-lookup"><span data-stu-id="72d80-107">The default behavior is to marshal objects to COM variants.</span></span> <span data-ttu-id="72d80-108">Эти правила применяются только к типу **Object** и не относятся к строго типизированным объектам, производным от класса **Object**.</span><span class="sxs-lookup"><span data-stu-id="72d80-108">These rules apply only to the type **Object** and do not apply to strongly typed objects that derive from the **Object** class.</span></span>  
  
 <span data-ttu-id="72d80-109">В этом разделе приводятся следующие дополнительные сведения о маршалинге типов объектов:</span><span class="sxs-lookup"><span data-stu-id="72d80-109">This topic provides the following additional information about marshaling object types:</span></span>  
  
-   [<span data-ttu-id="72d80-110">Маршалинг параметров</span><span class="sxs-lookup"><span data-stu-id="72d80-110">Marshaling Options</span></span>](#cpcondefaultmarshalingforobjectsanchor7)  
  
-   [<span data-ttu-id="72d80-111">Маршалинг объекта в интерфейс</span><span class="sxs-lookup"><span data-stu-id="72d80-111">Marshaling Object to Interface</span></span>](#cpcondefaultmarshalingforobjectsanchor2)  
  
-   [<span data-ttu-id="72d80-112">Маршалинг объекта в вариант</span><span class="sxs-lookup"><span data-stu-id="72d80-112">Marshaling Object to Variant</span></span>](#cpcondefaultmarshalingforobjectsanchor3)  
  
-   [<span data-ttu-id="72d80-113">Маршалинг варианта в объект</span><span class="sxs-lookup"><span data-stu-id="72d80-113">Marshaling Variant to Object</span></span>](#cpcondefaultmarshalingforobjectsanchor4)  
  
-   [<span data-ttu-id="72d80-114">Маршалинг вариантов ByRef</span><span class="sxs-lookup"><span data-stu-id="72d80-114">Marshaling ByRef Variants</span></span>](#cpcondefaultmarshalingforobjectsanchor6)  
  
<a name="cpcondefaultmarshalingforobjectsanchor7"></a>   
## <a name="marshaling-options"></a><span data-ttu-id="72d80-115">Маршалинг параметров</span><span class="sxs-lookup"><span data-stu-id="72d80-115">Marshaling Options</span></span>  
 <span data-ttu-id="72d80-116">В следующей таблице показаны параметры маршалинга для типа данных **Object**.</span><span class="sxs-lookup"><span data-stu-id="72d80-116">The following table shows the marshaling options for the **Object** data type.</span></span> <span data-ttu-id="72d80-117">Атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> предоставляет несколько значений перечисления <xref:System.Runtime.InteropServices.UnmanagedType> для маршалинга объектов.</span><span class="sxs-lookup"><span data-stu-id="72d80-117">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal objects.</span></span>  
  
|<span data-ttu-id="72d80-118">Тип перечисления</span><span class="sxs-lookup"><span data-stu-id="72d80-118">Enumeration type</span></span>|<span data-ttu-id="72d80-119">Описание неуправляемого формата</span><span class="sxs-lookup"><span data-stu-id="72d80-119">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="72d80-120">**UnmanagedType.Struct**</span><span class="sxs-lookup"><span data-stu-id="72d80-120">**UnmanagedType.Struct**</span></span><br /><br /> <span data-ttu-id="72d80-121">(по умолчанию для параметров)</span><span class="sxs-lookup"><span data-stu-id="72d80-121">(default for parameters)</span></span>|<span data-ttu-id="72d80-122">Вариант в стиле COM.</span><span class="sxs-lookup"><span data-stu-id="72d80-122">A COM-style variant.</span></span>|  
|<span data-ttu-id="72d80-123">**UnmanagedType.Interface**</span><span class="sxs-lookup"><span data-stu-id="72d80-123">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="72d80-124">Интерфейс **IDispatch**, если возможно. В противном случае интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="72d80-124">An **IDispatch** interface, if possible; otherwise, an **IUnknown** interface.</span></span>|  
|<span data-ttu-id="72d80-125">**UnmanagedType.IUnknown**</span><span class="sxs-lookup"><span data-stu-id="72d80-125">**UnmanagedType.IUnknown**</span></span><br /><br /> <span data-ttu-id="72d80-126">(по умолчанию для полей)</span><span class="sxs-lookup"><span data-stu-id="72d80-126">(default for fields)</span></span>|<span data-ttu-id="72d80-127">Интерфейс **IUnknown**.</span><span class="sxs-lookup"><span data-stu-id="72d80-127">An **IUnknown** interface.</span></span>|  
|<span data-ttu-id="72d80-128">**UnmanagedType.IDispatch**</span><span class="sxs-lookup"><span data-stu-id="72d80-128">**UnmanagedType.IDispatch**</span></span>|<span data-ttu-id="72d80-129">Интерфейс **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="72d80-129">An **IDispatch** interface.</span></span>|  
  
 <span data-ttu-id="72d80-130">В следующем примере показано определение управляемого интерфейса для `MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="72d80-130">The following example shows the managed interface definition for `MarshalObject`.</span></span>  
  
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
  
 <span data-ttu-id="72d80-131">Следующий пример кода экспортирует интерфейс `MarshalObject` в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="72d80-131">The following code exports the `MarshalObject` interface to a type library.</span></span>  
  
```  
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
>  <span data-ttu-id="72d80-132">Маршалер взаимодействия после вызова автоматически высвобождает любой выделенный объект внутри варианта.</span><span class="sxs-lookup"><span data-stu-id="72d80-132">The interop marshaler automatically frees any allocated object inside the variant after the call.</span></span>  
  
 <span data-ttu-id="72d80-133">В следующем примере показан форматированный тип значения.</span><span class="sxs-lookup"><span data-stu-id="72d80-133">The following example shows a formatted value type.</span></span>  
  
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
  
 <span data-ttu-id="72d80-134">Следующий пример кода экспортирует форматированный тип в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="72d80-134">The following code exports the formatted type to a type library.</span></span>  
  
```  
struct ObjectHolder {  
   VARIANT o1;  
   IDispatch *o2;  
}  
```  
  
<a name="cpcondefaultmarshalingforobjectsanchor2"></a>   
## <a name="marshaling-object-to-interface"></a><span data-ttu-id="72d80-135">Маршалинг объекта в интерфейс</span><span class="sxs-lookup"><span data-stu-id="72d80-135">Marshaling Object to Interface</span></span>  
 <span data-ttu-id="72d80-136">Если объект предоставляется модели COM в виде интерфейса, это будет интерфейс класса для управляемого типа <xref:System.Object> (интерфейс **_Object**).</span><span class="sxs-lookup"><span data-stu-id="72d80-136">When an object is exposed to COM as an interface, that interface is the class interface for the managed type <xref:System.Object> (the **_Object** interface).</span></span> <span data-ttu-id="72d80-137">В полученной библиотеке типов этот интерфейс типизируется как **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) или **IUnknown** (**UnmanagedType.IUnknown**).</span><span class="sxs-lookup"><span data-stu-id="72d80-137">This interface is typed as an **IDispatch** (<xref:System.Runtime.InteropServices.UnmanagedType>) or an **IUnknown** (**UnmanagedType.IUnknown**) in the resulting type library.</span></span> <span data-ttu-id="72d80-138">Клиенты COM могут динамически вызывать члены управляемого класса или любые члены, реализуемые его производными классами, используя интерфейс **_Object**.</span><span class="sxs-lookup"><span data-stu-id="72d80-138">COM clients can dynamically invoke the members of the managed class or any members implemented by its derived classes through the **_Object** interface.</span></span> <span data-ttu-id="72d80-139">Клиент также может вызывать **QueryInterface** для получения любого другого интерфейса, явно реализуемого управляемым типом.</span><span class="sxs-lookup"><span data-stu-id="72d80-139">The client can also call **QueryInterface** to obtain any other interface explicitly implemented by the managed type.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor3"></a>   
## <a name="marshaling-object-to-variant"></a><span data-ttu-id="72d80-140">Маршалинг объекта в вариант</span><span class="sxs-lookup"><span data-stu-id="72d80-140">Marshaling Object to Variant</span></span>  
 <span data-ttu-id="72d80-141">При маршалинге объекта в вариант внутренний тип варианта определяется во время выполнения на основе следующих правил:</span><span class="sxs-lookup"><span data-stu-id="72d80-141">When an object is marshaled to a variant, the internal variant type is determined at run time, based on the following rules:</span></span>  
  
-   <span data-ttu-id="72d80-142">Если ссылка на объект имеет значение NULL (**Nothing** в Visual Basic), выполняется маршалинг объекта в вариант типа **VT_EMPTY**.</span><span class="sxs-lookup"><span data-stu-id="72d80-142">If the object reference is null (**Nothing** in Visual Basic), the object is marshaled to a variant of type **VT_EMPTY**.</span></span>  
  
-   <span data-ttu-id="72d80-143">Если объект является экземпляром любого типа, представленного в следующей таблице, итоговый тип варианта определяется встроенными правилами маршалера, которые показаны в таблице.</span><span class="sxs-lookup"><span data-stu-id="72d80-143">If the object is an instance of any type listed in the following table, the resulting variant type is determined by the rules built into the marshaler and shown in the table.</span></span>  
  
-   <span data-ttu-id="72d80-144">Другие объекты, которым требуется явное управление поведением маршалинга, могут реализовывать интерфейс <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="72d80-144">Other objects that need to explicitly control the marshaling behavior can implement the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="72d80-145">В этом случае тип варианта определяется в соответствии с кодом типа, возвращаемым из метода <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72d80-145">In that case, the variant type is determined by the type code returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="72d80-146">В противном случае выполняется маршалинг объекта в виде варианта типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="72d80-146">Otherwise, the object is marshaled as a variant of type **VT_UNKNOWN**.</span></span>  
  
### <a name="marshaling-system-types-to-variant"></a><span data-ttu-id="72d80-147">Маршалинг системных типов в вариант</span><span class="sxs-lookup"><span data-stu-id="72d80-147">Marshaling System Types to Variant</span></span>  
 <span data-ttu-id="72d80-148">В следующей таблице показаны управляемые типы объектов и соответствующие им варианты модели COM.</span><span class="sxs-lookup"><span data-stu-id="72d80-148">The following table shows managed object types and their corresponding COM variant types.</span></span> <span data-ttu-id="72d80-149">Эти типы преобразуются только в том случае, если сигнатура вызываемого метода относится к типу <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72d80-149">These types are converted only when the signature of the method being called is of type <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
|<span data-ttu-id="72d80-150">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="72d80-150">Object type</span></span>|<span data-ttu-id="72d80-151">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="72d80-151">COM variant type</span></span>|  
|-----------------|----------------------|  
|<span data-ttu-id="72d80-152">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="72d80-152">Null object reference (**Nothing** in Visual Basic).</span></span>|<span data-ttu-id="72d80-153">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="72d80-153">**VT_EMPTY**</span></span>|  
|<xref:System.DBNull?displayProperty=nameWithType>|<span data-ttu-id="72d80-154">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="72d80-154">**VT_NULL**</span></span>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>|<span data-ttu-id="72d80-155">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="72d80-155">**VT_ERROR**</span></span>|  
|<xref:System.Reflection.Missing?displayProperty=nameWithType>|<span data-ttu-id="72d80-156">**VT_ERROR** с **E_PARAMNOTFOUND**</span><span class="sxs-lookup"><span data-stu-id="72d80-156">**VT_ERROR** with **E_PARAMNOTFOUND**</span></span>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>|<span data-ttu-id="72d80-157">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="72d80-157">**VT_DISPATCH**</span></span>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>|<span data-ttu-id="72d80-158">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="72d80-158">**VT_UNKNOWN**</span></span>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>|<span data-ttu-id="72d80-159">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="72d80-159">**VT_CY**</span></span>|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="72d80-160">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="72d80-160">**VT_BOOL**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="72d80-161">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="72d80-161">**VT_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="72d80-162">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="72d80-162">**VT_UI1**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="72d80-163">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="72d80-163">**VT_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="72d80-164">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="72d80-164">**VT_UI2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="72d80-165">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="72d80-165">**VT_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="72d80-166">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="72d80-166">**VT_UI4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="72d80-167">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="72d80-167">**VT_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="72d80-168">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="72d80-168">**VT_UI8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="72d80-169">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="72d80-169">**VT_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="72d80-170">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="72d80-170">**VT_R8**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="72d80-171">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="72d80-171">**VT_DECIMAL**</span></span>|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="72d80-172">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="72d80-172">**VT_DATE**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="72d80-173">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="72d80-173">**VT_BSTR**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="72d80-174">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="72d80-174">**VT_INT**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="72d80-175">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="72d80-175">**VT_UINT**</span></span>|  
|<xref:System.Array?displayProperty=nameWithType>|<span data-ttu-id="72d80-176">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="72d80-176">**VT_ARRAY**</span></span>|  
  
 <span data-ttu-id="72d80-177">В следующем примере кода с помощью интерфейса `MarshalObject` демонстрируется передача различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="72d80-177">Using the `MarshalObject` interface defined in the previous example, the following code example demonstrates how to pass various types of variants to a COM server.</span></span>  
  
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
  
 <span data-ttu-id="72d80-178">Маршалинг типов COM, у которых нет соответствующих управляемых типов, может осуществляться с использованием классов-оболочек, таких как <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper> и <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span><span class="sxs-lookup"><span data-stu-id="72d80-178">COM types that do not have corresponding managed types can be marshaled using wrapper classes such as <xref:System.Runtime.InteropServices.ErrorWrapper>, <xref:System.Runtime.InteropServices.DispatchWrapper>, <xref:System.Runtime.InteropServices.UnknownWrapper>, and <xref:System.Runtime.InteropServices.CurrencyWrapper>.</span></span> <span data-ttu-id="72d80-179">В следующем примере кода демонстрируется использование этих классов-оболочек для передачи различных типов вариантов на COM-сервер.</span><span class="sxs-lookup"><span data-stu-id="72d80-179">The following code example demonstrates how to use these wrappers to pass various types of variants to a COM server.</span></span>  
  
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
  
 <span data-ttu-id="72d80-180">Классы-оболочки определяются в пространстве имен <xref:System.Runtime.InteropServices>.</span><span class="sxs-lookup"><span data-stu-id="72d80-180">The wrapper classes are defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
### <a name="marshaling-the-iconvertible-interface-to-variant"></a><span data-ttu-id="72d80-181">Маршалинг интерфейса IConvertible в вариант</span><span class="sxs-lookup"><span data-stu-id="72d80-181">Marshaling the IConvertible Interface to Variant</span></span>  
 <span data-ttu-id="72d80-182">Типы, которые не приведены в предыдущем разделе, могут управлять маршалингом посредством реализации интерфейса <xref:System.IConvertible>.</span><span class="sxs-lookup"><span data-stu-id="72d80-182">Types other than those listed in the previous section can control how they are marshaled by implementing the <xref:System.IConvertible> interface.</span></span> <span data-ttu-id="72d80-183">Если объект реализует интерфейс **IConvertible**, тип варианта COM определяется во время выполнения на основе значения перечисления <xref:System.TypeCode>, которое возвращается методом <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72d80-183">If the object implements the **IConvertible** interface, the COM variant type is determined at run time by the value of the <xref:System.TypeCode> enumeration returned from the <xref:System.IConvertible.GetTypeCode%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="72d80-184">В следующей таблице показаны возможные значения перечисления **TypeCode** и соответствующие им типы вариантов COM.</span><span class="sxs-lookup"><span data-stu-id="72d80-184">The following table shows the possible values for the **TypeCode** enumeration and the corresponding COM variant type for each value.</span></span>  
  
|<span data-ttu-id="72d80-185">Код типа</span><span class="sxs-lookup"><span data-stu-id="72d80-185">TypeCode</span></span>|<span data-ttu-id="72d80-186">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="72d80-186">COM variant type</span></span>|  
|--------------|----------------------|  
|<span data-ttu-id="72d80-187">**TypeCode.Empty**</span><span class="sxs-lookup"><span data-stu-id="72d80-187">**TypeCode.Empty**</span></span>|<span data-ttu-id="72d80-188">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="72d80-188">**VT_EMPTY**</span></span>|  
|<span data-ttu-id="72d80-189">**TypeCode.Object**</span><span class="sxs-lookup"><span data-stu-id="72d80-189">**TypeCode.Object**</span></span>|<span data-ttu-id="72d80-190">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="72d80-190">**VT_UNKNOWN**</span></span>|  
|<span data-ttu-id="72d80-191">**TypeCode.DBNull**</span><span class="sxs-lookup"><span data-stu-id="72d80-191">**TypeCode.DBNull**</span></span>|<span data-ttu-id="72d80-192">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="72d80-192">**VT_NULL**</span></span>|  
|<span data-ttu-id="72d80-193">**TypeCode.Boolean**</span><span class="sxs-lookup"><span data-stu-id="72d80-193">**TypeCode.Boolean**</span></span>|<span data-ttu-id="72d80-194">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="72d80-194">**VT_BOOL**</span></span>|  
|<span data-ttu-id="72d80-195">**TypeCode.Char**</span><span class="sxs-lookup"><span data-stu-id="72d80-195">**TypeCode.Char**</span></span>|<span data-ttu-id="72d80-196">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="72d80-196">**VT_UI2**</span></span>|  
|<span data-ttu-id="72d80-197">**TypeCode.Sbyte**</span><span class="sxs-lookup"><span data-stu-id="72d80-197">**TypeCode.Sbyte**</span></span>|<span data-ttu-id="72d80-198">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="72d80-198">**VT_I1**</span></span>|  
|<span data-ttu-id="72d80-199">**TypeCode.Byte**</span><span class="sxs-lookup"><span data-stu-id="72d80-199">**TypeCode.Byte**</span></span>|<span data-ttu-id="72d80-200">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="72d80-200">**VT_UI1**</span></span>|  
|<span data-ttu-id="72d80-201">**TypeCode.Int16**</span><span class="sxs-lookup"><span data-stu-id="72d80-201">**TypeCode.Int16**</span></span>|<span data-ttu-id="72d80-202">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="72d80-202">**VT_I2**</span></span>|  
|<span data-ttu-id="72d80-203">**TypeCode.UInt16**</span><span class="sxs-lookup"><span data-stu-id="72d80-203">**TypeCode.UInt16**</span></span>|<span data-ttu-id="72d80-204">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="72d80-204">**VT_UI2**</span></span>|  
|<span data-ttu-id="72d80-205">**TypeCode.Int32**</span><span class="sxs-lookup"><span data-stu-id="72d80-205">**TypeCode.Int32**</span></span>|<span data-ttu-id="72d80-206">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="72d80-206">**VT_I4**</span></span>|  
|<span data-ttu-id="72d80-207">**TypeCode.UInt32**</span><span class="sxs-lookup"><span data-stu-id="72d80-207">**TypeCode.UInt32**</span></span>|<span data-ttu-id="72d80-208">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="72d80-208">**VT_UI4**</span></span>|  
|<span data-ttu-id="72d80-209">**TypeCode.Int64**</span><span class="sxs-lookup"><span data-stu-id="72d80-209">**TypeCode.Int64**</span></span>|<span data-ttu-id="72d80-210">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="72d80-210">**VT_I8**</span></span>|  
|<span data-ttu-id="72d80-211">**TypeCode.UInt64**</span><span class="sxs-lookup"><span data-stu-id="72d80-211">**TypeCode.UInt64**</span></span>|<span data-ttu-id="72d80-212">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="72d80-212">**VT_UI8**</span></span>|  
|<span data-ttu-id="72d80-213">**TypeCode.Single**</span><span class="sxs-lookup"><span data-stu-id="72d80-213">**TypeCode.Single**</span></span>|<span data-ttu-id="72d80-214">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="72d80-214">**VT_R4**</span></span>|  
|<span data-ttu-id="72d80-215">**TypeCode.Double**</span><span class="sxs-lookup"><span data-stu-id="72d80-215">**TypeCode.Double**</span></span>|<span data-ttu-id="72d80-216">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="72d80-216">**VT_R8**</span></span>|  
|<span data-ttu-id="72d80-217">**TypeCode.Decimal**</span><span class="sxs-lookup"><span data-stu-id="72d80-217">**TypeCode.Decimal**</span></span>|<span data-ttu-id="72d80-218">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="72d80-218">**VT_DECIMAL**</span></span>|  
|<span data-ttu-id="72d80-219">**TypeCode.DateTime**</span><span class="sxs-lookup"><span data-stu-id="72d80-219">**TypeCode.DateTime**</span></span>|<span data-ttu-id="72d80-220">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="72d80-220">**VT_DATE**</span></span>|  
|<span data-ttu-id="72d80-221">**TypeCode.String**</span><span class="sxs-lookup"><span data-stu-id="72d80-221">**TypeCode.String**</span></span>|<span data-ttu-id="72d80-222">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="72d80-222">**VT_BSTR**</span></span>|  
|<span data-ttu-id="72d80-223">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-223">Not supported.</span></span>|<span data-ttu-id="72d80-224">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="72d80-224">**VT_INT**</span></span>|  
|<span data-ttu-id="72d80-225">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-225">Not supported.</span></span>|<span data-ttu-id="72d80-226">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="72d80-226">**VT_UINT**</span></span>|  
|<span data-ttu-id="72d80-227">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-227">Not supported.</span></span>|<span data-ttu-id="72d80-228">**VT_ARRAY**</span><span class="sxs-lookup"><span data-stu-id="72d80-228">**VT_ARRAY**</span></span>|  
|<span data-ttu-id="72d80-229">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-229">Not supported.</span></span>|<span data-ttu-id="72d80-230">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="72d80-230">**VT_RECORD**</span></span>|  
|<span data-ttu-id="72d80-231">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-231">Not supported.</span></span>|<span data-ttu-id="72d80-232">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="72d80-232">**VT_CY**</span></span>|  
|<span data-ttu-id="72d80-233">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-233">Not supported.</span></span>|<span data-ttu-id="72d80-234">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="72d80-234">**VT_VARIANT**</span></span>|  
  
 <span data-ttu-id="72d80-235">Значение варианта COM определяется посредством вызова интерфейса **IConvertible.To** *Type*, в котором **To** *Type* — это подпрограмма преобразования, которая соответствует типу, возвращаемому из **IConvertible.GetTypeCode**.</span><span class="sxs-lookup"><span data-stu-id="72d80-235">The value of the COM variant is determined by calling the **IConvertible.To** *Type* interface, where **To** *Type* is the conversion routine that corresponds to the type that was returned from **IConvertible.GetTypeCode**.</span></span> <span data-ttu-id="72d80-236">Например, объект, который возвращает **TypeCode.Double** из **IConvertible.GetTypeCode**, маршалируется как вариант COM типа **VT_R8**.</span><span class="sxs-lookup"><span data-stu-id="72d80-236">For example, an object that returns **TypeCode.Double** from **IConvertible.GetTypeCode** is marshaled as a COM variant of type **VT_R8**.</span></span> <span data-ttu-id="72d80-237">Чтобы получить значение варианта (хранится в поле **dblVal** варианта COM), можно выполнить приведение к интерфейсу **IConvertible** и вызвать метод <xref:System.IConvertible.ToDouble%2A>.</span><span class="sxs-lookup"><span data-stu-id="72d80-237">You can obtain the value of the variant (stored in the **dblVal** field of the COM variant) by casting to the **IConvertible** interface and calling the <xref:System.IConvertible.ToDouble%2A> method.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor4"></a>   
## <a name="marshaling-variant-to-object"></a><span data-ttu-id="72d80-238">Маршалинг варианта в объект</span><span class="sxs-lookup"><span data-stu-id="72d80-238">Marshaling Variant to Object</span></span>  
 <span data-ttu-id="72d80-239">При маршалинге варианта в объект тип (а в некоторых случаях и значение) маршалированного варианта определяет тип получаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="72d80-239">When marshaling a variant to an object, the type, and sometimes the value, of the marshaled variant determines the type of object produced.</span></span> <span data-ttu-id="72d80-240">В следующей таблице показаны типы вариантов и соответствующие им типы объектов, которые создаются маршалером при передаче варианта из COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72d80-240">The following table identifies each variant type and the corresponding object type that the marshaler creates when a variant is passed from COM to the .NET Framework.</span></span>  
  
|<span data-ttu-id="72d80-241">Тип варианта COM</span><span class="sxs-lookup"><span data-stu-id="72d80-241">COM variant type</span></span>|<span data-ttu-id="72d80-242">Тип объекта</span><span class="sxs-lookup"><span data-stu-id="72d80-242">Object type</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="72d80-243">**VT_EMPTY**</span><span class="sxs-lookup"><span data-stu-id="72d80-243">**VT_EMPTY**</span></span>|<span data-ttu-id="72d80-244">Ссылка на объект NULL (**Nothing** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="72d80-244">Null object reference (**Nothing** in Visual Basic).</span></span>|  
|<span data-ttu-id="72d80-245">**VT_NULL**</span><span class="sxs-lookup"><span data-stu-id="72d80-245">**VT_NULL**</span></span>|<xref:System.DBNull?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-246">**VT_DISPATCH**</span><span class="sxs-lookup"><span data-stu-id="72d80-246">**VT_DISPATCH**</span></span>|<span data-ttu-id="72d80-247">**System.__ComObject** или значение NULL если (pdispVal == null)</span><span class="sxs-lookup"><span data-stu-id="72d80-247">**System.__ComObject** or null if (pdispVal == null)</span></span>|  
|<span data-ttu-id="72d80-248">**VT_UNKNOWN**</span><span class="sxs-lookup"><span data-stu-id="72d80-248">**VT_UNKNOWN**</span></span>|<span data-ttu-id="72d80-249">**System.__ComObject** или значение NULL если (punkVal == null)</span><span class="sxs-lookup"><span data-stu-id="72d80-249">**System.__ComObject** or null if (punkVal == null)</span></span>|  
|<span data-ttu-id="72d80-250">**VT_ERROR**</span><span class="sxs-lookup"><span data-stu-id="72d80-250">**VT_ERROR**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-251">**VT_BOOL**</span><span class="sxs-lookup"><span data-stu-id="72d80-251">**VT_BOOL**</span></span>|<xref:System.Boolean?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-252">**VT_I1**</span><span class="sxs-lookup"><span data-stu-id="72d80-252">**VT_I1**</span></span>|<xref:System.SByte?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-253">**VT_UI1**</span><span class="sxs-lookup"><span data-stu-id="72d80-253">**VT_UI1**</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-254">**VT_I2**</span><span class="sxs-lookup"><span data-stu-id="72d80-254">**VT_I2**</span></span>|<xref:System.Int16?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-255">**VT_UI2**</span><span class="sxs-lookup"><span data-stu-id="72d80-255">**VT_UI2**</span></span>|<xref:System.UInt16?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-256">**VT_I4**</span><span class="sxs-lookup"><span data-stu-id="72d80-256">**VT_I4**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-257">**VT_UI4**</span><span class="sxs-lookup"><span data-stu-id="72d80-257">**VT_UI4**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-258">**VT_I8**</span><span class="sxs-lookup"><span data-stu-id="72d80-258">**VT_I8**</span></span>|<xref:System.Int64?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-259">**VT_UI8**</span><span class="sxs-lookup"><span data-stu-id="72d80-259">**VT_UI8**</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-260">**VT_R4**</span><span class="sxs-lookup"><span data-stu-id="72d80-260">**VT_R4**</span></span>|<xref:System.Single?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-261">**VT_R8**</span><span class="sxs-lookup"><span data-stu-id="72d80-261">**VT_R8**</span></span>|<xref:System.Double?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-262">**VT_DECIMAL**</span><span class="sxs-lookup"><span data-stu-id="72d80-262">**VT_DECIMAL**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-263">**VT_DATE**</span><span class="sxs-lookup"><span data-stu-id="72d80-263">**VT_DATE**</span></span>|<xref:System.DateTime?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-264">**VT_BSTR**</span><span class="sxs-lookup"><span data-stu-id="72d80-264">**VT_BSTR**</span></span>|<xref:System.String?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-265">**VT_INT**</span><span class="sxs-lookup"><span data-stu-id="72d80-265">**VT_INT**</span></span>|<xref:System.Int32?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-266">**VT_UINT**</span><span class="sxs-lookup"><span data-stu-id="72d80-266">**VT_UINT**</span></span>|<xref:System.UInt32?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-267">**VT_ARRAY** &#124; **VT_**\*</span><span class="sxs-lookup"><span data-stu-id="72d80-267">**VT_ARRAY** &#124; **VT_**\*</span></span>|<xref:System.Array?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-268">**VT_CY**</span><span class="sxs-lookup"><span data-stu-id="72d80-268">**VT_CY**</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  
|<span data-ttu-id="72d80-269">**VT_RECORD**</span><span class="sxs-lookup"><span data-stu-id="72d80-269">**VT_RECORD**</span></span>|<span data-ttu-id="72d80-270">Соответствующий тип упакованного значения.</span><span class="sxs-lookup"><span data-stu-id="72d80-270">Corresponding boxed value type.</span></span>|  
|<span data-ttu-id="72d80-271">**VT_VARIANT**</span><span class="sxs-lookup"><span data-stu-id="72d80-271">**VT_VARIANT**</span></span>|<span data-ttu-id="72d80-272">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="72d80-272">Not supported.</span></span>|  
  
 <span data-ttu-id="72d80-273">Типы вариантов, передаваемые из модели COM в управляемый код и обратно в COM, могут не сохранять тип варианта во время вызова.</span><span class="sxs-lookup"><span data-stu-id="72d80-273">Variant types passed from COM to managed code and then back to COM might not retain the same variant type for the duration of the call.</span></span> <span data-ttu-id="72d80-274">Рассмотрим, что произойдет при передаче типа варианта **VT_DISPATCH** из модели COM в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="72d80-274">Consider what happens when a variant of type **VT_DISPATCH** is passed from COM to the .NET Framework.</span></span> <span data-ttu-id="72d80-275">Во время маршалинга вариант преобразуется в <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72d80-275">During marshaling, the variant is converted to a <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="72d80-276">Если затем **Object** возвращается в COM, выполняется его обратный маршалинг в вариант типа **VT_UNKNOWN**.</span><span class="sxs-lookup"><span data-stu-id="72d80-276">If the **Object** is then passed back to COM, it is marshaled back to a variant of type **VT_UNKNOWN**.</span></span> <span data-ttu-id="72d80-277">При этом не гарантируется, что вариант, полученный при маршалинге объекта из управляемого кода в COM, будет иметь тот же тип, что и вариант, изначально использованный для создания объекта.</span><span class="sxs-lookup"><span data-stu-id="72d80-277">There is no guarantee that the variant produced when an object is marshaled from managed code to COM will be the same type as the variant initially used to produce the object.</span></span>  
  
<a name="cpcondefaultmarshalingforobjectsanchor6"></a>   
## <a name="marshaling-byref-variants"></a><span data-ttu-id="72d80-278">Маршалинг вариантов ByRef</span><span class="sxs-lookup"><span data-stu-id="72d80-278">Marshaling ByRef Variants</span></span>  
 <span data-ttu-id="72d80-279">Сами по себе варианты могут передаваться по значению или по ссылке. Несмотря на это, также можно использовать флаг **VT_BYREF** с любым типом варианта, чтобы указать, что содержимое варианта передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="72d80-279">Although variants themselves can be passed by value or by reference, the **VT_BYREF** flag can also be used with any variant type to indicate that the contents of the variant are being passed by reference instead of by value.</span></span> <span data-ttu-id="72d80-280">Разница между маршалингом вариантов по ссылке и с установленным флагом **VT_BYREF** может показаться не очевидной.</span><span class="sxs-lookup"><span data-stu-id="72d80-280">The difference between marshaling variants by reference and marshaling a variant with the **VT_BYREF** flag set can be confusing.</span></span> <span data-ttu-id="72d80-281">На следующем рисунке показаны различия между этими способами.</span><span class="sxs-lookup"><span data-stu-id="72d80-281">The following illustration clarifies the differences.</span></span>  
  
 <span data-ttu-id="72d80-282">![Вариант, передающийся по стопке](./media/interopvariant.gif "interopvariant")</span><span class="sxs-lookup"><span data-stu-id="72d80-282">![Variant passed on the stack](./media/interopvariant.gif "interopvariant")</span></span>  
<span data-ttu-id="72d80-283">Варианты, передаваемые по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="72d80-283">Variants passed by value and by reference</span></span>  
  
 <span data-ttu-id="72d80-284">**Поведение по умолчанию при маршалинге объектов и вариантов по значению**</span><span class="sxs-lookup"><span data-stu-id="72d80-284">**Default behavior for marshaling objects and variants by value**</span></span>  
  
-   <span data-ttu-id="72d80-285">При передаче объектов из управляемого кода в COM содержимое объекта копируется в новый вариант, создаваемый маршалером, с использованием правил, которые определены в разделе [Маршалинг объекта в вариант](#cpcondefaultmarshalingforobjectsanchor3).</span><span class="sxs-lookup"><span data-stu-id="72d80-285">When passing objects from managed code to COM, the contents of the object are copied into a new variant created by the marshaler, using the rules defined in [Marshaling Object to Variant](#cpcondefaultmarshalingforobjectsanchor3).</span></span> <span data-ttu-id="72d80-286">Изменения, внесенные в вариант в неуправляемом коде, не применяются к исходному объекту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="72d80-286">Changes made to the variant on the unmanaged side are not propagated back to the original object on return from the call.</span></span>  
  
-   <span data-ttu-id="72d80-287">При передаче вариантов из COM в управляемый код содержимое варианта копируется в создаваемый объект с использованием правил, которые определены в разделе [Маршалинг варианта в объект](#cpcondefaultmarshalingforobjectsanchor4).</span><span class="sxs-lookup"><span data-stu-id="72d80-287">When passing variants from COM to managed code, the contents of the variant are copied to a newly created object, using the rules defined in [Marshaling Variant to Object](#cpcondefaultmarshalingforobjectsanchor4).</span></span> <span data-ttu-id="72d80-288">Изменения, внесенные в объект в управляемом коде, не применяются к исходному варианту после возврата из вызова.</span><span class="sxs-lookup"><span data-stu-id="72d80-288">Changes made to the object on the managed side are not propagated back to the original variant on return from the call.</span></span>  
  
 <span data-ttu-id="72d80-289">**Поведение по умолчанию при маршалинге объектов и вариантов по ссылке**</span><span class="sxs-lookup"><span data-stu-id="72d80-289">**Default behavior for marshaling objects and variants by reference**</span></span>  
  
 <span data-ttu-id="72d80-290">Для распространения изменений в вызывающем объекте параметры необходимо передавать по ссылке.</span><span class="sxs-lookup"><span data-stu-id="72d80-290">To propagate changes back to the caller, the parameters must be passed by reference.</span></span> <span data-ttu-id="72d80-291">Например, можно использовать ключевое слово **ref** в C# (или **ByRef** в управляемом коде Visual Basic) для передачи параметров по ссылке.</span><span class="sxs-lookup"><span data-stu-id="72d80-291">For example, you can use the **ref** keyword in C# (or **ByRef** in Visual Basic managed code) to pass parameters by reference.</span></span> <span data-ttu-id="72d80-292">В модели COM ссылочные параметры передаются с использованием указателя, например **variant \***.</span><span class="sxs-lookup"><span data-stu-id="72d80-292">In COM, reference parameters are passed using a pointer such as a **variant \***.</span></span>  
  
-   <span data-ttu-id="72d80-293">При передаче объекта в COM по ссылке маршалер создает новый вариант и копирует содержимое ссылки на объект в вариант до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="72d80-293">When passing an object to COM by reference, the marshaler creates a new variant and copies the contents of the object reference into the variant before the call is made.</span></span> <span data-ttu-id="72d80-294">Вариант передается в неуправляемую функцию, в которой пользователь может изменять его содержимое.</span><span class="sxs-lookup"><span data-stu-id="72d80-294">The variant is passed to the unmanaged function where the user is free to change the contents of the variant.</span></span> <span data-ttu-id="72d80-295">После возврата из вызова изменения, внесенные в вариант в неуправляемом коде, применяются к исходному объекту.</span><span class="sxs-lookup"><span data-stu-id="72d80-295">On return from the call, any changes made to the variant on the unmanaged side are propagated back to the original object.</span></span> <span data-ttu-id="72d80-296">Если тип варианта отличается от типа варианта, переданного в вызов, изменения применяются к объекту другого типа.</span><span class="sxs-lookup"><span data-stu-id="72d80-296">If the type of the variant differs from the type of the variant passed to the call, then the changes are propagated back to an object of a different type.</span></span> <span data-ttu-id="72d80-297">Таким образом, тип переданного в вызов объекта может отличаться от типа объекта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="72d80-297">That is, the type of the object passed into the call can differ from the type of the object returned from the call.</span></span>  
  
-   <span data-ttu-id="72d80-298">При передаче варианта в управляемый код по ссылке маршалер создает новый объект и копирует содержимое варианта в объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="72d80-298">When passing a variant to managed code by reference, the marshaler creates a new object and copies the contents of the variant into the object before making the call.</span></span> <span data-ttu-id="72d80-299">Ссылка на объект передается в управляемую функцию, в которой пользователь может изменять сам объект.</span><span class="sxs-lookup"><span data-stu-id="72d80-299">A reference to the object is passed to the managed function, where the user is free to change the object.</span></span> <span data-ttu-id="72d80-300">После возврата из вызова изменения, внесенные в указываемый по ссылке объект, применяются к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="72d80-300">On return from the call, any changes made to the referenced object are propagated back to the original variant.</span></span> <span data-ttu-id="72d80-301">Если тип объекта отличается от типа объекта, переданного в вызов, тип исходного варианта изменяется и значение передается обратно в вариант.</span><span class="sxs-lookup"><span data-stu-id="72d80-301">If the type of the object differs from the type of the object passed in to the call, the type of the original variant is changed and the value is propagated back into the variant.</span></span> <span data-ttu-id="72d80-302">Аналогичным образом, тип переданного в вызов варианта может отличаться от типа варианта, возвращаемого из вызова.</span><span class="sxs-lookup"><span data-stu-id="72d80-302">Again, the type of the variant passed into the call can differ from the type of the variant returned from the call.</span></span>  
  
 <span data-ttu-id="72d80-303">**Поведение по умолчанию при маршалинге варианта с установленным флагом VT_BYREF**</span><span class="sxs-lookup"><span data-stu-id="72d80-303">**Default behavior for marshaling a variant with the VT_BYREF flag set**</span></span>  
  
-   <span data-ttu-id="72d80-304">Для варианта, передаваемого в управляемый код по значению, может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит ссылку вместо значения.</span><span class="sxs-lookup"><span data-stu-id="72d80-304">A variant being passed to managed code by value can have the **VT_BYREF** flag set to indicate that the variant contains a reference instead of a value.</span></span> <span data-ttu-id="72d80-305">В этом случае вариант по-прежнему маршалируется в объект, поскольку вариант передается по значению.</span><span class="sxs-lookup"><span data-stu-id="72d80-305">In this case, the variant is still marshaled to an object because the variant is being passed by value.</span></span> <span data-ttu-id="72d80-306">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="72d80-306">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="72d80-307">После этого объект передается в управляемую функцию. Тем не менее при возврате из вызова объект не применяется к исходному варианту.</span><span class="sxs-lookup"><span data-stu-id="72d80-307">The object is then passed into the managed function; however, on return from the call, the object is not propagated back into the original variant.</span></span> <span data-ttu-id="72d80-308">Изменения, внесенные в управляемый объект, утрачиваются.</span><span class="sxs-lookup"><span data-stu-id="72d80-308">Changes made to the managed object are lost.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="72d80-309">Изменить значение варианта, переданного по значению, нельзя, даже если для варианта установлен флаг **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="72d80-309">There is no way to change the value of a variant passed by value, even if the variant has the **VT_BYREF** flag set.</span></span>  
  
-   <span data-ttu-id="72d80-310">Для варианта, передаваемого в управляемый код по ссылке, также может быть установлен флаг **VT_BYREF**, который указывает, что вариант содержит еще одну ссылку.</span><span class="sxs-lookup"><span data-stu-id="72d80-310">A variant being passed to managed code by reference can also have the **VT_BYREF** flag set to indicate that the variant contains another reference.</span></span> <span data-ttu-id="72d80-311">В этом случае вариант маршалируется в объект **ref**, поскольку вариант передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="72d80-311">If it does, the variant is marshaled to a **ref** object because the variant is being passed by reference.</span></span> <span data-ttu-id="72d80-312">Маршалер автоматически разыменовывает содержимое варианта и копирует его во вновь созданный объект до того, как будет выполнен вызов.</span><span class="sxs-lookup"><span data-stu-id="72d80-312">The marshaler automatically dereferences the contents of the variant and copies it into a newly created object before making the call.</span></span> <span data-ttu-id="72d80-313">При возврате из вызова значение объекта возвращается по ссылке с исходным вариантом только в том случае, если тип объекта совпадает с типом переданного объекта.</span><span class="sxs-lookup"><span data-stu-id="72d80-313">On return from the call, the value of the object is propagated back to the reference within the original variant only if the object is the same type as the object passed in.</span></span> <span data-ttu-id="72d80-314">Таким образом, при передаче не изменяется тип варианта с установленным флагом **VT_BYREF**.</span><span class="sxs-lookup"><span data-stu-id="72d80-314">That is, propagation does not change the type of a variant with the **VT_BYREF** flag set.</span></span> <span data-ttu-id="72d80-315">Если во время вызова тип объекта изменяется, при возврате из него возникает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="72d80-315">If the type of the object is changed during the call, an <xref:System.InvalidCastException> occurs on return from the call.</span></span>  
  
 <span data-ttu-id="72d80-316">В следующей таблице описываются общие правила распространения для вариантов и объектов.</span><span class="sxs-lookup"><span data-stu-id="72d80-316">The following table summarizes the propagation rules for variants and objects.</span></span>  
  
|<span data-ttu-id="72d80-317">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="72d80-317">From</span></span>|<span data-ttu-id="72d80-318">Кому</span><span class="sxs-lookup"><span data-stu-id="72d80-318">To</span></span>|<span data-ttu-id="72d80-319">Возвращаемые изменения</span><span class="sxs-lookup"><span data-stu-id="72d80-319">Changes propagated back</span></span>|  
|----------|--------|-----------------------------|  
|<span data-ttu-id="72d80-320">**Вариант**  *v*</span><span class="sxs-lookup"><span data-stu-id="72d80-320">**Variant**  *v*</span></span>|<span data-ttu-id="72d80-321">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-321">**Object**  *o*</span></span>|<span data-ttu-id="72d80-322">Никогда</span><span class="sxs-lookup"><span data-stu-id="72d80-322">Never</span></span>|  
|<span data-ttu-id="72d80-323">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-323">**Object**  *o*</span></span>|<span data-ttu-id="72d80-324">**Вариант**  *v*</span><span class="sxs-lookup"><span data-stu-id="72d80-324">**Variant**  *v*</span></span>|<span data-ttu-id="72d80-325">Никогда</span><span class="sxs-lookup"><span data-stu-id="72d80-325">Never</span></span>|  
|<span data-ttu-id="72d80-326">**Вариант**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="72d80-326">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="72d80-327">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-327">**Ref Object**  *o*</span></span>|<span data-ttu-id="72d80-328">Всегда</span><span class="sxs-lookup"><span data-stu-id="72d80-328">Always</span></span>|  
|<span data-ttu-id="72d80-329">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-329">**Ref object**  *o*</span></span>|<span data-ttu-id="72d80-330">**Вариант**   ***\****  *pv*</span><span class="sxs-lookup"><span data-stu-id="72d80-330">**Variant**   ***\****  *pv*</span></span>|<span data-ttu-id="72d80-331">Всегда</span><span class="sxs-lookup"><span data-stu-id="72d80-331">Always</span></span>|  
|<span data-ttu-id="72d80-332">**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span><span class="sxs-lookup"><span data-stu-id="72d80-332">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_\*)**</span></span>|<span data-ttu-id="72d80-333">**Объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-333">**Object**  *o*</span></span>|<span data-ttu-id="72d80-334">Никогда</span><span class="sxs-lookup"><span data-stu-id="72d80-334">Never</span></span>|  
|<span data-ttu-id="72d80-335">**Вариант**  *v* **(VT_BYREF** *&#124;* **VT_)**</span><span class="sxs-lookup"><span data-stu-id="72d80-335">**Variant**  *v* **(VT_BYREF** *&#124;* **VT_)**</span></span>|<span data-ttu-id="72d80-336">**Ссылочный объект**  *o*</span><span class="sxs-lookup"><span data-stu-id="72d80-336">**Ref Object**  *o*</span></span>|<span data-ttu-id="72d80-337">Только если тип не был изменен.</span><span class="sxs-lookup"><span data-stu-id="72d80-337">Only if the type has not changed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72d80-338">См. также</span><span class="sxs-lookup"><span data-stu-id="72d80-338">See Also</span></span>  
 [<span data-ttu-id="72d80-339">Характеристики маршалинга по умолчанию</span><span class="sxs-lookup"><span data-stu-id="72d80-339">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)  
 [<span data-ttu-id="72d80-340">Преобразуемые и непреобразуемые типы</span><span class="sxs-lookup"><span data-stu-id="72d80-340">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)  
 <span data-ttu-id="72d80-341">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100)) (Атрибуты направления)</span><span class="sxs-lookup"><span data-stu-id="72d80-341">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>  
 [<span data-ttu-id="72d80-342">Копирование и закрепление</span><span class="sxs-lookup"><span data-stu-id="72d80-342">Copying and Pinning</span></span>](copying-and-pinning.md)
