---
title: Вызываемая оболочка COM
ms.date: 10/23/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CCW
- COM interop, COM wrappers
- COM wrappers
- callable wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: d04be3b5-27b9-4f5b-8469-a44149fabf78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e2cab36c1dd990a1bf848067e7ae81baeb9ed8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355055"
---
# <a name="com-callable-wrapper"></a><span data-ttu-id="531ec-102">Вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="531ec-102">COM Callable Wrapper</span></span>

<span data-ttu-id="531ec-103">Когда клиент COM вызывает объект .NET, среда CLR создает для этого объекта управляемый объект и вызываемую оболочку COM.</span><span class="sxs-lookup"><span data-stu-id="531ec-103">When a COM client calls a .NET object, the common language runtime creates the managed object and a COM callable wrapper (CCW) for the object.</span></span> <span data-ttu-id="531ec-104">Не имея возможности обращаться к объекту .NET напрямую, клиенты COM используют вызываемую оболочку COM в качестве посредника для управляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="531ec-104">Unable to reference a .NET object directly, COM clients use the CCW as a proxy for the managed object.</span></span>

<span data-ttu-id="531ec-105">Среда выполнения создает одну вызываемую оболочку COM для управляемого объекта независимо от числа клиентов COM, которым требуются его службы.</span><span class="sxs-lookup"><span data-stu-id="531ec-105">The runtime creates exactly one CCW for a managed object, regardless of the number of COM clients requesting its services.</span></span> <span data-ttu-id="531ec-106">Как показано на рисунке ниже, несколько клиентов COM могут содержать ссылку на вызываемую оболочку COM, предоставляющую интерфейс INew.</span><span class="sxs-lookup"><span data-stu-id="531ec-106">As the following illustration shows, multiple COM clients can hold a reference to the CCW that exposes the INew interface.</span></span> <span data-ttu-id="531ec-107">Вызываемая оболочка COM, в свою очередь, содержит единственную ссылку на управляемый объект, который реализует интерфейс и обрабатывается сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="531ec-107">The CCW, in turn, holds a single reference to the managed object that implements the interface and is garbage collected.</span></span> <span data-ttu-id="531ec-108">Клиенты COM и .NET могут одновременно выполнять запросы к одному и тому же управляемому объекту.</span><span class="sxs-lookup"><span data-stu-id="531ec-108">Both COM and .NET clients can make requests on the same managed object simultaneously.</span></span>

<span data-ttu-id="531ec-109">![Вызываемая оболочка COM](./media/ccw.gif "ccw") Доступ к объектам .NET с помощью вызываемой оболочки COM</span><span class="sxs-lookup"><span data-stu-id="531ec-109">![COM callable wrapper](./media/ccw.gif "ccw") Accessing .NET objects through COM callable wrapper</span></span>

<span data-ttu-id="531ec-110">Вызываемые оболочки COM невидимы для других классов, работающих в среде .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="531ec-110">COM callable wrappers are invisible to other classes running within the .NET Framework.</span></span> <span data-ttu-id="531ec-111">Их основной целью является маршалинг вызовов между управляемым и неуправляемым кодом. Однако вызываемые оболочки COM также управляют идентификацией и временем жизни управляемых объектов, которые в них упакованы.</span><span class="sxs-lookup"><span data-stu-id="531ec-111">Their primary purpose is to marshal calls between managed and unmanaged code; however, CCWs also manage the object identity and object lifetime of the managed objects they wrap.</span></span>

## <a name="object-identity"></a><span data-ttu-id="531ec-112">Идентификация объектов</span><span class="sxs-lookup"><span data-stu-id="531ec-112">Object Identity</span></span>

<span data-ttu-id="531ec-113">Для объекта .NET среда выполнения выделяет память  в куче, обработанной сборщиком мусора, что позволяет при необходимости перемещать объект в памяти.</span><span class="sxs-lookup"><span data-stu-id="531ec-113">The runtime allocates memory for the .NET object from its garbage-collected heap, which enables the runtime to move the object around in memory as necessary.</span></span> <span data-ttu-id="531ec-114">Для вызываемой же оболочки COM среда выполнения выделяет память из кучи, не обработанной сборщиком мусора, благодаря чему клиенты COM могут напрямую обращаться к оболочке.</span><span class="sxs-lookup"><span data-stu-id="531ec-114">In contrast, the runtime allocates memory for the CCW from a noncollected heap, making it possible for COM clients to reference the wrapper directly.</span></span>

## <a name="object-lifetime"></a><span data-ttu-id="531ec-115">Время жизни объекта</span><span class="sxs-lookup"><span data-stu-id="531ec-115">Object Lifetime</span></span>

<span data-ttu-id="531ec-116">В отличие от клиента .NET, учет ссылок для вызываемой оболочки COM, в которую инкапсулирован клиент, ведется обычным для модели COM образом.</span><span class="sxs-lookup"><span data-stu-id="531ec-116">Unlike the .NET client it wraps, the CCW is reference-counted in traditional COM fashion.</span></span> <span data-ttu-id="531ec-117">Когда счетчик ссылок на вызываемую оболочку COM достигает нуля, оболочка освобождает свою ссылку на управляемый объект.</span><span class="sxs-lookup"><span data-stu-id="531ec-117">When the reference count on the CCW reaches zero, the wrapper releases its reference on the managed object.</span></span> <span data-ttu-id="531ec-118">Управляемый объект, на который не осталось ссылок, обрабатывается сборщиком мусора в течение следующего цикла.</span><span class="sxs-lookup"><span data-stu-id="531ec-118">A managed object with no remaining references is collected during the next garbage-collection cycle.</span></span>

## <a name="simulating-com-interfaces"></a><span data-ttu-id="531ec-119">Имитация COM-интерфейсов</span><span class="sxs-lookup"><span data-stu-id="531ec-119">Simulating COM interfaces</span></span>

<span data-ttu-id="531ec-120">Вызываемая оболочка COM предоставляет клиентам COM доступ ко всем открытым и видимым COM-интерфейсам, типам данных и возвращаемым значениям способом, совместимым с реализацией средствами COM взаимодействия на основе интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="531ec-120">CCW exposes all public, COM-visible interfaces, data types, and return values to COM clients in a manner that is consistent with COM's enforcement of interface-based interaction.</span></span> <span data-ttu-id="531ec-121">Для клиента COM вызов методов в объекте .NET Framework идентичен вызову методов в COM-объекте.</span><span class="sxs-lookup"><span data-stu-id="531ec-121">For a COM client, invoking methods on a .NET Framework object is identical to invoking methods on a COM object.</span></span>

<span data-ttu-id="531ec-122">Для обеспечения такой унификации вызываемая оболочка COM создает традиционные COM-интерфейсы, такие как **IUnknown** и **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="531ec-122">To create this seamless approach, the CCW manufactures traditional COM interfaces, such as **IUnknown** and **IDispatch**.</span></span> <span data-ttu-id="531ec-123">Как показано на рисунке ниже, вызываемая оболочка COM содержит единственную ссылку на инкапсулируемый в нее объект .NET.</span><span class="sxs-lookup"><span data-stu-id="531ec-123">As the following illustration shows, the CCW maintains a single reference on the .NET object that it wraps.</span></span> <span data-ttu-id="531ec-124">Клиент COM и объект .NET взаимодействуют друг с другом с помощью посредника и создания заглушки вызываемой оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="531ec-124">Both the COM client and .NET object interact with each other through the proxy and stub construction of the CCW.</span></span>

<span data-ttu-id="531ec-125">![COM-интерфейсы](./media/ccwwithinterfaces.gif "ccwwithinterfaces") COM-интерфейсы и вызываемая оболочка COM</span><span class="sxs-lookup"><span data-stu-id="531ec-125">![COM interfaces](./media/ccwwithinterfaces.gif "ccwwithinterfaces") COM interfaces and the COM callable wrapper</span></span>

<span data-ttu-id="531ec-126">Платформа .NET Framework не только обеспечивает доступ к интерфейсам, которые явным образом реализуются классом в управляемой среде, но и от имени объекта предоставляет реализации COM-интерфейсов, перечисленных в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="531ec-126">In addition to exposing the interfaces that are explicitly implemented by a class in the managed environment, the .NET Framework supplies implementations of the COM interfaces listed in the following table on behalf of the object.</span></span> <span data-ttu-id="531ec-127">Класс .NET может переопределять заданное по умолчанию поведение, предоставляя собственную реализацию этих интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="531ec-127">A .NET class can override the default behavior by providing its own implementation of these interfaces.</span></span> <span data-ttu-id="531ec-128">Однако среда выполнения всегда предоставляет реализацию интерфейсов **IUnknown** и **IDispatch**.</span><span class="sxs-lookup"><span data-stu-id="531ec-128">However, the runtime always provides the implementation for the **IUnknown** and **IDispatch** interfaces.</span></span>

|<span data-ttu-id="531ec-129">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="531ec-129">Interface</span></span>|<span data-ttu-id="531ec-130">Описание</span><span class="sxs-lookup"><span data-stu-id="531ec-130">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="531ec-131">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="531ec-131">**IDispatch**</span></span>|<span data-ttu-id="531ec-132">Предоставляет механизм позднего связывания с типом.</span><span class="sxs-lookup"><span data-stu-id="531ec-132">Provides a mechanism for late binding to type.</span></span>|
|<span data-ttu-id="531ec-133">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="531ec-133">**IErrorInfo**</span></span>|<span data-ttu-id="531ec-134">Предоставляет текстовое описание ошибки, ее источник, файл справки, контекст справки и идентификатор GUID интерфейса, определившего ошибку (для классов .NET всегда **GUID_NULL**).</span><span class="sxs-lookup"><span data-stu-id="531ec-134">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|
|<span data-ttu-id="531ec-135">**IProvideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="531ec-135">**IProvideClassInfo**</span></span>|<span data-ttu-id="531ec-136">Позволяет клиентам COM получать доступ к интерфейсу **ITypeInfo**, реализованному управляемым классом.</span><span class="sxs-lookup"><span data-stu-id="531ec-136">Enables COM clients to gain access to the **ITypeInfo** interface implemented by a managed class.</span></span>|
|<span data-ttu-id="531ec-137">**ISupportErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="531ec-137">**ISupportErrorInfo**</span></span>|<span data-ttu-id="531ec-138">Позволяет клиенту COM определить, поддерживает ли управляемый объект интерфейс **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="531ec-138">Enables a COM client to determine whether the managed object supports the **IErrorInfo** interface.</span></span> <span data-ttu-id="531ec-139">Если это так, то клиент может получить указатель на последний по времени объект исключения.</span><span class="sxs-lookup"><span data-stu-id="531ec-139">If so, enables the client to obtain a pointer to the latest exception object.</span></span> <span data-ttu-id="531ec-140">Все управляемые типы поддерживают интерфейс **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="531ec-140">All managed types support the **IErrorInfo** interface.</span></span>|
|<span data-ttu-id="531ec-141">**ITypeInfo**</span><span class="sxs-lookup"><span data-stu-id="531ec-141">**ITypeInfo**</span></span>|<span data-ttu-id="531ec-142">Предоставляет для класса сведения о типе, которые совпадают со сведениями о типе, предоставленными Tlbexp.exe.</span><span class="sxs-lookup"><span data-stu-id="531ec-142">Provides type information for a class that is exactly the same as the type information produced by Tlbexp.exe.</span></span>|
|<span data-ttu-id="531ec-143">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="531ec-143">**IUnknown**</span></span>|<span data-ttu-id="531ec-144">Предоставляет стандартную реализацию интерфейса **IUnknown**, с помощью которой клиент COM управляет временем жизни вызываемой оболочки COM и обеспечивает приведение типов.</span><span class="sxs-lookup"><span data-stu-id="531ec-144">Provides the standard implementation of the **IUnknown** interface with which the COM client manages the lifetime of the CCW and provides type coercion.</span></span>|

 <span data-ttu-id="531ec-145">Управляемый класс также может предоставлять COM-интерфейсы, описанные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="531ec-145">A managed class can also provide the COM interfaces described in the following table.</span></span>

|<span data-ttu-id="531ec-146">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="531ec-146">Interface</span></span>|<span data-ttu-id="531ec-147">Описание</span><span class="sxs-lookup"><span data-stu-id="531ec-147">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="531ec-148">Интерфейс класса (\_*classname*)</span><span class="sxs-lookup"><span data-stu-id="531ec-148">The (\_*classname*) class interface</span></span>|<span data-ttu-id="531ec-149">Интерфейс, предоставляемый средой выполнения и не определенный явным образом, который обеспечивает доступ ко всем открытым интерфейсам, методам, свойствам и полям, явно предоставляемым в управляемом объекте.</span><span class="sxs-lookup"><span data-stu-id="531ec-149">Interface, exposed by the runtime and not explicitly defined, that exposes all public interfaces, methods, properties, and fields that are explicitly exposed on a managed object.</span></span>|
|<span data-ttu-id="531ec-150">**IConnectionPoint** и **IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="531ec-150">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="531ec-151">Интерфейс для объектов, которые являются источниками событий на основе делегатов (интерфейс для регистрации подписчиков событий).</span><span class="sxs-lookup"><span data-stu-id="531ec-151">Interface for objects that source delegate-based events (an interface for registering event subscribers).</span></span>|
|<span data-ttu-id="531ec-152">**IDispatchEx**</span><span class="sxs-lookup"><span data-stu-id="531ec-152">**IDispatchEx**</span></span>|<span data-ttu-id="531ec-153">Интерфейс, предоставляемый средой выполнения, если класс реализует интерфейс **IExpando**.</span><span class="sxs-lookup"><span data-stu-id="531ec-153">Interface supplied by the runtime if the class implements **IExpando**.</span></span> <span data-ttu-id="531ec-154">Интерфейс **IDispatchEx** является расширением интерфейса **IDispatch**, который, в отличие от интерфейса **IDispatch**, позволяет перечислять, добавлять, удалять и вызывать члены с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="531ec-154">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch**, enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|
|<span data-ttu-id="531ec-155">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="531ec-155">**IEnumVARIANT**</span></span>|<span data-ttu-id="531ec-156">Интерфейс для классов типа коллекции, в которых перечислены ее объекты, если класс реализует интерфейс **IEnumerable**.</span><span class="sxs-lookup"><span data-stu-id="531ec-156">Interface for collection-type classes, which enumerates the objects in the collection if the class implements **IEnumerable**.</span></span>|

## <a name="introducing-the-class-interface"></a><span data-ttu-id="531ec-157">Введение в интерфейс класса</span><span class="sxs-lookup"><span data-stu-id="531ec-157">Introducing the class interface</span></span>

<span data-ttu-id="531ec-158">Интерфейс класса, не определенный явным образом в управляемом коде, — это интерфейс, который предоставляет доступ ко всем открытым методам, свойствам, полям и событиям, к которым предоставлен явный доступ в объекте .NET.</span><span class="sxs-lookup"><span data-stu-id="531ec-158">The class interface, which is not explicitly defined in managed code, is an interface that exposes all public methods, properties, fields, and events that are explicitly exposed on the .NET object.</span></span> <span data-ttu-id="531ec-159">Этот интерфейс может быть сдвоенным или интерфейсом диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="531ec-159">This interface can be a dual or dispatch-only interface.</span></span> <span data-ttu-id="531ec-160">Интерфейс класса получает имя самого класса .NET с символом подчеркивания впереди.</span><span class="sxs-lookup"><span data-stu-id="531ec-160">The class interface receives the name of the .NET class itself, preceded by an underscore.</span></span> <span data-ttu-id="531ec-161">Например, если имя класса — Mammal, интерфейс класса получит имя \_Mammal.</span><span class="sxs-lookup"><span data-stu-id="531ec-161">For example, for class Mammal, the class interface is \_Mammal.</span></span>

<span data-ttu-id="531ec-162">В случае с производными классами интерфейс класса также предоставляет доступ ко всем открытым методам, свойствам и полям базового класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-162">For derived classes, the class interface also exposes all public methods, properties, and fields of the base class.</span></span> <span data-ttu-id="531ec-163">Производный класс также предоставляет доступ к интерфейсу класса для каждого базового класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-163">The derived class also exposes a class interface for each base class.</span></span> <span data-ttu-id="531ec-164">Например, если класс Mammal является расширением класса MammalSuperclass, который, в свою очередь, является расширением класса System.Object, объект .NET предоставляет клиентам COM доступ к трем интерфейсам классов с именами \_Mammal, \_MammalSuperclass и \_Object.</span><span class="sxs-lookup"><span data-stu-id="531ec-164">For example, if class Mammal extends class MammalSuperclass, which itself extends System.Object, the .NET object exposes to COM clients three class interfaces named \_Mammal, \_MammalSuperclass, and \_Object.</span></span>

<span data-ttu-id="531ec-165">Например, рассмотрим приведенный ниже класс .NET.</span><span class="sxs-lookup"><span data-stu-id="531ec-165">For example, consider the following .NET class:</span></span>

```vb
' Applies the ClassInterfaceAttribute to set the interface to dual.
<ClassInterface(ClassInterfaceType.AutoDual)> _
' Implicitly extends System.Object.
Public Class Mammal
    Sub Eat()
    Sub Breathe()
    Sub Sleep()
End Class
```

```csharp
// Applies the ClassInterfaceAttribute to set the interface to dual.
[ClassInterface(ClassInterfaceType.AutoDual)]
// Implicitly extends System.Object.
public class Mammal
{
    public void Eat() {}
    public void Breathe() {}
    public void Sleep() {}
}
```

<span data-ttu-id="531ec-166">Клиент COM может получить указатель на интерфейс класса с именем `_Mammal`, который описан в библиотеке типов, созданной [программой экспорта библиотек типов (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="531ec-166">The COM client can obtain a pointer to a class interface named `_Mammal`, which is described in the type library that the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) tool generates.</span></span> <span data-ttu-id="531ec-167">Если класс `Mammal` реализовал один или несколько интерфейсов, они будут отображены в коклассе.</span><span class="sxs-lookup"><span data-stu-id="531ec-167">If the `Mammal` class implemented one or more interfaces, the interfaces would appear under the coclass.</span></span>

```
[odl, uuid(…), hidden, dual, nonextensible, oleautomation]
interface _Mammal : IDispatch
{
    [id(0x00000000), propget] HRESULT ToString([out, retval] BSTR*
        pRetVal);
    [id(0x60020001)] HRESULT Equals([in] VARIANT obj, [out, retval]
        VARIANT_BOOL* pRetVal);
    [id(0x60020002)] HRESULT GetHashCode([out, retval] short* pRetVal);
    [id(0x60020003)] HRESULT GetType([out, retval] _Type** pRetVal);
    [id(0x6002000d)] HRESULT Eat();
    [id(0x6002000e)] HRESULT Breathe();
    [id(0x6002000f)] HRESULT Sleep();
}
[uuid(…)]
coclass Mammal
{
    [default] interface _Mammal;
}
```

<span data-ttu-id="531ec-168">Создавать интерфейс класса необязательно.</span><span class="sxs-lookup"><span data-stu-id="531ec-168">Generating the class interface is optional.</span></span> <span data-ttu-id="531ec-169">По умолчанию COM-взаимодействие создает для каждого класса, экспортируемого в библиотеку типов, интерфейс диспетчеризации.</span><span class="sxs-lookup"><span data-stu-id="531ec-169">By default, COM interop generates a dispatch-only interface for each class you export to a type library.</span></span> <span data-ttu-id="531ec-170">Автоматическое создание этого интерфейса можно предотвратить или изменить, применив к классу атрибут <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="531ec-170">You can prevent or modify the automatic creation of this interface by applying the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> to your class.</span></span> <span data-ttu-id="531ec-171">Хотя интерфейс класса и может упростить задачу обеспечения доступа из COM к управляемым классам, возможности его использования ограничены.</span><span class="sxs-lookup"><span data-stu-id="531ec-171">Although the class interface can ease the task of exposing managed classes to COM, its uses are limited.</span></span>

> [!CAUTION]
> <span data-ttu-id="531ec-172">Использование интерфейса класса вместо явного определения собственного интерфейса может усложнить управление версиями управляемого класса в будущем.</span><span class="sxs-lookup"><span data-stu-id="531ec-172">Using the class interface, instead of explicitly defining your own, can complicate the future versioning of your managed class.</span></span> <span data-ttu-id="531ec-173">Перед использованием интерфейса класса следует ознакомиться с приведенными ниже рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="531ec-173">Please read the following guidelines before using the class interface.</span></span>

### <a name="define-an-explicit-interface-for-com-clients-to-use-rather-than-generating-the-class-interface"></a><span data-ttu-id="531ec-174">Вместо создания интерфейса класса лучше определить явный интерфейс, который могли бы использовать клиенты COM.</span><span class="sxs-lookup"><span data-stu-id="531ec-174">Define an explicit interface for COM clients to use rather than generating the class interface.</span></span>

<span data-ttu-id="531ec-175">Так как COM-взаимодействие создает интерфейс класса автоматически, изменения, вносимые в класс в следующих версиях, могут повлиять на компоновку интерфейса класса, предоставляемого средой CLR.</span><span class="sxs-lookup"><span data-stu-id="531ec-175">Because COM interop generates a class interface automatically, post-version changes to your class can alter the layout of the class interface exposed by the common language runtime.</span></span> <span data-ttu-id="531ec-176">Так как клиенты COM обычно не готовы к изменениям в компоновке интерфейса, изменение компоновки членов класса вызовет сбой в их работе.</span><span class="sxs-lookup"><span data-stu-id="531ec-176">Since COM clients are typically unprepared to handle changes in the layout of an interface, they break if you change the member layout of the class.</span></span>

<span data-ttu-id="531ec-177">Эта рекомендация подкрепляет представление о том, что интерфейсы, предоставляемые клиентам COM, лучше оставлять неизменными.</span><span class="sxs-lookup"><span data-stu-id="531ec-177">This guideline reinforces the notion that interfaces exposed to COM clients must remain unchangeable.</span></span> <span data-ttu-id="531ec-178">Чтобы снизить риск сбоя в работе клиентов COM в результате непреднамеренного изменения компоновки интерфейса, нужно изолировать все изменения, вносимые в класс, от интерфейса путем его явного определения.</span><span class="sxs-lookup"><span data-stu-id="531ec-178">To reduce the risk of breaking COM clients by inadvertently reordering the interface layout, isolate all changes to the class from the interface layout by explicitly defining interfaces.</span></span>

<span data-ttu-id="531ec-179">С помощью атрибута **ClassInterfaceAttribute** отключите автоматическое создание интерфейса класса и реализуйте для класса явный интерфейс, как показано во фрагменте программы ниже:</span><span class="sxs-lookup"><span data-stu-id="531ec-179">Use the **ClassInterfaceAttribute** to disengage the automatic generation of the class interface and implement an explicit interface for the class, as the following code fragment shows:</span></span>

```vb
<ClassInterface(ClassInterfaceType.None)>Public Class LoanApp
    Implements IExplicit
    Sub M() Implements IExplicit.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.None)]
public class LoanApp : IExplicit
{
    int IExplicit.M() { return 0; }
}
```

<span data-ttu-id="531ec-180">Значение **ClassInterfaceType.None** предотвращает создание интерфейса класса при экспорте метаданных класса в библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="531ec-180">The **ClassInterfaceType.None** value prevents the class interface from being generated when the class metadata is exported to a type library.</span></span> <span data-ttu-id="531ec-181">В предыдущем примере клиенты COM могут получить доступ к классу `LoanApp` только через интерфейс `IExplicit`.</span><span class="sxs-lookup"><span data-stu-id="531ec-181">In the preceding example, COM clients can access the `LoanApp` class only through the `IExplicit` interface.</span></span>

### <a name="avoid-caching-dispatch-identifiers-dispids"></a><span data-ttu-id="531ec-182">Избегайте кэширования идентификаторов диспетчеризации (DispId)</span><span class="sxs-lookup"><span data-stu-id="531ec-182">Avoid caching dispatch identifiers (DispIds)</span></span>

<span data-ttu-id="531ec-183">Использование интерфейса класса является допустимым вариантом для клиентов со сценариями, клиентов Microsoft Visual Basic 6.0, а также клиентов с поздним связыванием, которые не кэшируют идентификаторы DispId членов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="531ec-183">Using the class interface is an acceptable option for scripted clients, Microsoft Visual Basic 6.0 clients, or any late-bound client that does not cache the DispIds of interface members.</span></span> <span data-ttu-id="531ec-184">Идентификаторы DispId определяют члены интерфейса, разрешающие позднее связывание.</span><span class="sxs-lookup"><span data-stu-id="531ec-184">DispIds identify interface members to enable late binding.</span></span>

<span data-ttu-id="531ec-185">Для интерфейса класса идентификаторы DispId создаются на основе позиции члена в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="531ec-185">For the class interface, generation of DispIds is based on the position of the member in the interface.</span></span> <span data-ttu-id="531ec-186">Если вы изменяете порядок членов и экспортируете класс в библиотеку типов, меняются и идентификаторы DispId, созданные в интерфейсе класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-186">If you change the order of the member and export the class to a type library, you will alter the DispIds generated in the class interface.</span></span>

<span data-ttu-id="531ec-187">Чтобы избежать нарушений в работе клиентов COM с поздним связыванием при использовании интерфейса класса, примените атрибут **ClassInterfaceAttribute** со значением **ClassInterfaceType.AutoDispatch**.</span><span class="sxs-lookup"><span data-stu-id="531ec-187">To avoid breaking late-bound COM clients when using the class interface, apply the **ClassInterfaceAttribute** with the **ClassInterfaceType.AutoDispatch** value.</span></span> <span data-ttu-id="531ec-188">Это значение реализует интерфейс диспетчеризации класса, но пропускает описание интерфейса в библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="531ec-188">This value implements a dispatch-only class interface, but omits the interface description from the type library.</span></span> <span data-ttu-id="531ec-189">Без описания интерфейса клиенты не могут кэшировать идентификаторы DispId во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="531ec-189">Without an interface description, clients are unable to cache DispIds at compile time.</span></span> <span data-ttu-id="531ec-190">Хотя это тип интерфейса по умолчанию для интерфейса класса, значение атрибута можно задать явным образом.</span><span class="sxs-lookup"><span data-stu-id="531ec-190">Although this is the default interface type for the class interface, you can apply the attribute value explicitly.</span></span>

```vb
<ClassInterface(ClassInterfaceType.AutoDispatch)> Public Class LoanApp
    Implements IAnother
    Sub M() Implements IAnother.M
…
End Class
```

```csharp
[ClassInterface(ClassInterfaceType.AutoDispatch)]
public class LoanApp
{
    public int M() { return 0; }
}
```

<span data-ttu-id="531ec-191">Чтобы получить идентификатор DispId члена интерфейса во время выполнения, клиент COM может вызвать метод **IDispatch.GetIdsOfNames**.</span><span class="sxs-lookup"><span data-stu-id="531ec-191">To get the DispId of an interface member at run time, COM clients can call **IDispatch.GetIdsOfNames**.</span></span> <span data-ttu-id="531ec-192">Чтобы вызвать метод для интерфейса, передайте возвращенный идентификатор DispId в качестве аргумента для **IDispatch.Invoke**.</span><span class="sxs-lookup"><span data-stu-id="531ec-192">To invoke a method on the interface, pass the returned DispId as an argument to **IDispatch.Invoke**.</span></span>

### <a name="restrict-using-the-dual-interface-option-for-the-class-interface"></a><span data-ttu-id="531ec-193">Ограничьте использование сдвоенного интерфейса для интерфейса класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-193">Restrict using the dual interface option for the class interface.</span></span>

<span data-ttu-id="531ec-194">Сдвоенные интерфейсы позволяют клиентам COM выполнять раннее и позднее связывание с членами интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="531ec-194">Dual interfaces enable early and late binding to interface members by COM clients.</span></span> <span data-ttu-id="531ec-195">Во время разработки и тестирования может оказаться полезным сделать интерфейс класса сдвоенным.</span><span class="sxs-lookup"><span data-stu-id="531ec-195">At design time and during testing, you might find it useful to set the class interface to dual.</span></span> <span data-ttu-id="531ec-196">Этот вариант также допустим и для управляемого класса (и его базовых классов), который никогда не будет изменяться.</span><span class="sxs-lookup"><span data-stu-id="531ec-196">For a managed class (and its base classes) that will never be modified, this option is also acceptable.</span></span> <span data-ttu-id="531ec-197">Во всех остальных случаях следует воздержаться от использования сдвоенного интерфейса класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-197">In all other cases, avoid setting the class interface to dual.</span></span>

<span data-ttu-id="531ec-198">Изредка автоматически созданный сдвоенный интерфейс может оказаться полезным, но чаще он создает трудности при работе с версиями.</span><span class="sxs-lookup"><span data-stu-id="531ec-198">An automatically generated dual interface might be appropriate in rare cases; however, more often it creates version-related complexity.</span></span> <span data-ttu-id="531ec-199">Например, внесение изменений в базовый класс легко может нарушить работу клиентов COM, использующих интерфейс производного класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-199">For example, COM clients using the class interface of a derived class can easily break with changes to the base class.</span></span> <span data-ttu-id="531ec-200">Если базовый класс предоставляется сторонним поставщиком, вы не можете контролировать компоновку интерфейса класса.</span><span class="sxs-lookup"><span data-stu-id="531ec-200">When a third party provides the base class, the layout of the class interface is out of your control.</span></span> <span data-ttu-id="531ec-201">Кроме того, в отличие от интерфейса диспетчеризации сдвоенный интерфейс (**ClassInterfaceType.AutoDual**) предоставляет описание интерфейса класса в экспортированной библиотеке типов.</span><span class="sxs-lookup"><span data-stu-id="531ec-201">Further, unlike a dispatch-only interface, a dual interface (**ClassInterfaceType.AutoDual**) provides a description of the class interface in the exported type library.</span></span> <span data-ttu-id="531ec-202">Это описание стимулирует клиентов с поздним связыванием кэшировать идентификаторы DispId во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="531ec-202">Such a description encourages late-bound clients to cache DispIds at run time.</span></span>

### <a name="ensure-that-all-com-event-notifications-are-late-bound"></a><span data-ttu-id="531ec-203">Все уведомления о событиях COM должны быть с поздним связыванием.</span><span class="sxs-lookup"><span data-stu-id="531ec-203">Ensure that all COM event notifications are late-bound.</span></span>

<span data-ttu-id="531ec-204">По умолчанию сведения о типах COM внедряются непосредственно в управляемые сборки, устраняя необходимость в использовании основных сборок взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="531ec-204">By default, COM type information is embedded directly into managed assemblies, which eliminates the need for primary interop assemblies (PIAs).</span></span> <span data-ttu-id="531ec-205">Тем не менее одним из ограничений внедренных сведений о типах является то, что доставка уведомлений о событиях COM с использованием вызовов vtable с ранним связыванием не поддерживается (в отличие от вызовов `IDispatch::Invoke` с поздним связыванием).</span><span class="sxs-lookup"><span data-stu-id="531ec-205">However, one of the limitations of embedded type information is that it does not supported delivery of COM event notifications by early-bound vtable calls, but only supports late-bound `IDispatch::Invoke` calls.</span></span>

<span data-ttu-id="531ec-206">Если для приложения требуются вызовы методов интерфейса событий COM с ранним связыванием, можно задать для свойства **Embed Interop Types** в Visual Studio значение `true` или включить следующий элемент в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="531ec-206">If your application requires early-bound calls to COM event interface methods, you can set the **Embed Interop Types** property in Visual Studio to `true`, or include the following element in your project file:</span></span>

```xml
<EmbedInteropTypes>True</EmbedInteropTypes>
```

## <a name="see-also"></a><span data-ttu-id="531ec-207">См. также</span><span class="sxs-lookup"><span data-stu-id="531ec-207">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="531ec-208">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="531ec-208">COM Wrappers</span></span>](com-wrappers.md)
- [<span data-ttu-id="531ec-209">Предоставление компонентов .NET Framework клиентам COM</span><span class="sxs-lookup"><span data-stu-id="531ec-209">Exposing .NET Framework Components to COM</span></span>](exposing-dotnet-components-to-com.md)
- [<span data-ttu-id="531ec-210">Oпределение типов .NET для взаимодействия</span><span class="sxs-lookup"><span data-stu-id="531ec-210">Qualifying .NET Types for Interoperation</span></span>](qualifying-net-types-for-interoperation.md)
- [<span data-ttu-id="531ec-211">Вызываемая оболочка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="531ec-211">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
