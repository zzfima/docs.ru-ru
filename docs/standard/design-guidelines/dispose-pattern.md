---
title: Шаблон ликвидации
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Dispose method
- class library design guidelines [.NET Framework], Dispose method
- class library design guidelines [.NET Framework], Finalize method
- customizing Dispose method name
- Finalize method
ms.assetid: 31a6c13b-d6a2-492b-9a9f-e5238c983bcb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff52e17cfe4a4236e4d165c0961ca3a23fed9a72
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864648"
---
# <a name="dispose-pattern"></a><span data-ttu-id="9272d-102">Шаблон ликвидации</span><span class="sxs-lookup"><span data-stu-id="9272d-102">Dispose Pattern</span></span>
<span data-ttu-id="9272d-103">Все программы получить один или несколько системных ресурсов, таких как память, дескрипторы системы и подключения к базе данных, в ходе их выполнения.</span><span class="sxs-lookup"><span data-stu-id="9272d-103">All programs acquire one or more system resources, such as memory, system handles, or database connections, during the course of their execution.</span></span> <span data-ttu-id="9272d-104">Разработчикам нужно соблюдать осторожность при использовании таких системных ресурсов, так как они должны быть освобождены после их получения и использования.</span><span class="sxs-lookup"><span data-stu-id="9272d-104">Developers have to be careful when using such system resources, because they must be released after they have been acquired and used.</span></span>  
  
 <span data-ttu-id="9272d-105">Среда CLR поддерживает автоматическое управление памятью.</span><span class="sxs-lookup"><span data-stu-id="9272d-105">The CLR provides support for automatic memory management.</span></span> <span data-ttu-id="9272d-106">Управляемая память (память, выделенную с помощью оператора C# `new`) не должны быть сняты явно.</span><span class="sxs-lookup"><span data-stu-id="9272d-106">Managed memory (memory allocated using the C# operator `new`) does not need to be explicitly released.</span></span> <span data-ttu-id="9272d-107">Он автоматически освобождается сборщиком мусора (GC).</span><span class="sxs-lookup"><span data-stu-id="9272d-107">It is released automatically by the garbage collector (GC).</span></span> <span data-ttu-id="9272d-108">Это освобождает разработчиков от нудной и сложной задачи по освобождению памяти и была одной из основных причин для беспрецедентной производительности, обеспечиваемая платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9272d-108">This frees developers from the tedious and difficult task of releasing memory and has been one of the main reasons for the unprecedented productivity afforded by the .NET Framework.</span></span>  
  
 <span data-ttu-id="9272d-109">К сожалению управляемой памяти — один из многих типов системных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-109">Unfortunately, managed memory is just one of many types of system resources.</span></span> <span data-ttu-id="9272d-110">Ресурсов, отличных от управляемой памяти по-прежнему должны быть сняты явно и называются неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9272d-110">Resources other than managed memory still need to be released explicitly and are referred to as unmanaged resources.</span></span> <span data-ttu-id="9272d-111">Сборщик Мусора был специально не предназначен для управления таких неуправляемых ресурсов, что означает, что, отвечает за управление неуправляемыми ресурсами заключается в руках разработчиков.</span><span class="sxs-lookup"><span data-stu-id="9272d-111">The GC was specifically not designed to manage such unmanaged resources, which means that the responsibility for managing unmanaged resources lies in the hands of the developers.</span></span>  
  
 <span data-ttu-id="9272d-112">Среда CLR предоставляет помощь в освобождения неуправляемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-112">The CLR provides some help in releasing unmanaged resources.</span></span> <span data-ttu-id="9272d-113"><xref:System.Object?displayProperty=nameWithType> Объявляет виртуальный метод <xref:System.Object.Finalize%2A> (также называемый метод завершения) вызывается сборщик мусора, прежде чем памяти объекта будет удален при сборке Мусора и может быть переопределен для освобождения неуправляемых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-113"><xref:System.Object?displayProperty=nameWithType> declares a virtual method <xref:System.Object.Finalize%2A> (also called the finalizer) that is called by the GC before the object’s memory is reclaimed by the GC and can be overridden to release unmanaged resources.</span></span> <span data-ttu-id="9272d-114">Типы, которые переопределяют метод завершения, называются завершаемые типов.</span><span class="sxs-lookup"><span data-stu-id="9272d-114">Types that override the finalizer are referred to as finalizable types.</span></span>  
  
 <span data-ttu-id="9272d-115">Несмотря на то, что методы завершения эффективны в некоторых сценариях очистки, у них есть два существенные недостатки:</span><span class="sxs-lookup"><span data-stu-id="9272d-115">Although finalizers are effective in some cleanup scenarios, they have two significant drawbacks:</span></span>  
  
-   <span data-ttu-id="9272d-116">Метод finalizer вызывается, когда сборщик Мусора обнаруживает, что объект является доступным для коллекции.</span><span class="sxs-lookup"><span data-stu-id="9272d-116">The finalizer is called when the GC detects that an object is eligible for collection.</span></span> <span data-ttu-id="9272d-117">Это происходит в некоторых неопределенного периода времени после ресурс больше не нужен.</span><span class="sxs-lookup"><span data-stu-id="9272d-117">This happens at some undetermined period of time after the resource is not needed anymore.</span></span> <span data-ttu-id="9272d-118">Задержка между когда разработчик может либо вы хотите для освобождения ресурсов и времени, когда ресурс освобождается фактически финализатором может быть неприемлемо в программах, которые запрашивают много дефицитные ресурсы (ресурсы, которые можно легко исчерпать) или в случаи, в которых ресурсы довольно сложно поддерживать используется (например, буферов большого объема неуправляемой памяти).</span><span class="sxs-lookup"><span data-stu-id="9272d-118">The delay between when the developer could or would like to release the resource and the time when the resource is actually released by the finalizer might be unacceptable in programs that acquire many scarce resources (resources that can be easily exhausted) or in cases in which resources are costly to keep in use (e.g., large unmanaged memory buffers).</span></span>  
  
-   <span data-ttu-id="9272d-119">Когда среда CLR должен вызывать метод завершения, его необходимо отложенный сбор данных памяти объекта до следующей округления сбора мусора (методы завершения, выполните между коллекциями).</span><span class="sxs-lookup"><span data-stu-id="9272d-119">When the CLR needs to call a finalizer, it must postpone collection of the object’s memory until the next round of garbage collection (the finalizers run between collections).</span></span> <span data-ttu-id="9272d-120">Это означает, что памяти объекта (и все объекты, которые он ссылается) не будет освобожден для более длительного периода времени.</span><span class="sxs-lookup"><span data-stu-id="9272d-120">This means that the object’s memory (and all objects it refers to) will not be released for a longer period of time.</span></span>  
  
 <span data-ttu-id="9272d-121">Таким образом, полагаясь исключительно на методы завершения могут не подходить во многих ситуациях, когда важно освободить неуправляемые ресурсы, как можно скорее, при работе с дефицитные ресурсы, или в высокой производительности сценариев, в которых добавлена мусора выполнения финализации неприемлем.</span><span class="sxs-lookup"><span data-stu-id="9272d-121">Therefore, relying exclusively on finalizers might not be appropriate in many scenarios when it is important to reclaim unmanaged resources as quickly as possible, when dealing with scarce resources, or in highly performant scenarios in which the added GC overhead of finalization is unacceptable.</span></span>  
  
 <span data-ttu-id="9272d-122">Платформа предоставляет <xref:System.IDisposable?displayProperty=nameWithType> интерфейс, который должен быть реализован для предоставления разработчику ручной способ освободить неуправляемые ресурсы, как только они не нужны.</span><span class="sxs-lookup"><span data-stu-id="9272d-122">The Framework provides the <xref:System.IDisposable?displayProperty=nameWithType> interface that should be implemented to provide the developer a manual way to release unmanaged resources as soon as they are not needed.</span></span> <span data-ttu-id="9272d-123">Он также предоставляет <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> метод, который можно обязать сборщик Мусора, объект был вручную удален и не требует финализации, в этом случае памяти объекта могут быть освобождены ранее.</span><span class="sxs-lookup"><span data-stu-id="9272d-123">It also provides the <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> method that can tell the GC that an object was manually disposed of and does not need to be finalized anymore, in which case the object’s memory can be reclaimed earlier.</span></span> <span data-ttu-id="9272d-124">Типы, реализующие `IDisposable` интерфейса называются уничтожаемых типов.</span><span class="sxs-lookup"><span data-stu-id="9272d-124">Types that implement the `IDisposable` interface are referred to as disposable types.</span></span>  
  
 <span data-ttu-id="9272d-125">Шаблон Dispose предназначен для стандартизации использования и реализации методов завершения и `IDisposable` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9272d-125">The Dispose Pattern is intended to standardize the usage and implementation of finalizers and the `IDisposable` interface.</span></span>  
  
 <span data-ttu-id="9272d-126">Основной шаблон призвана уменьшить сложность реализации <xref:System.Object.Finalize%2A> и <xref:System.IDisposable.Dispose%2A> методы.</span><span class="sxs-lookup"><span data-stu-id="9272d-126">The main motivation for the pattern is to reduce the complexity of the implementation of the <xref:System.Object.Finalize%2A> and the <xref:System.IDisposable.Dispose%2A> methods.</span></span> <span data-ttu-id="9272d-127">Сложность состоит в том, что методы используют некоторые, но не все ветви кода (различия описаны далее в этой главе).</span><span class="sxs-lookup"><span data-stu-id="9272d-127">The complexity stems from the fact that the methods share some but not all code paths (the differences are described later in the chapter).</span></span> <span data-ttu-id="9272d-128">Кроме того являются историческим причинам, для некоторых элементов шаблона, связанными с развитием языковая поддержка управления ресурсами детерминированной.</span><span class="sxs-lookup"><span data-stu-id="9272d-128">In addition, there are historical reasons for some elements of the pattern related to the evolution of language support for deterministic resource management.</span></span>  
  
 <span data-ttu-id="9272d-129">**✓ DO** реализация базовый шаблон Dispose для типов, содержащей экземпляры высвобождаемые типы.</span><span class="sxs-lookup"><span data-stu-id="9272d-129">**✓ DO** implement the Basic Dispose Pattern on types containing instances of disposable types.</span></span> <span data-ttu-id="9272d-130">См. в разделе [базовый шаблон Dispose](#basic_pattern) Дополнительные сведения об базовый шаблон.</span><span class="sxs-lookup"><span data-stu-id="9272d-130">See the [Basic Dispose Pattern](#basic_pattern) section for details on the basic pattern.</span></span>  
  
 <span data-ttu-id="9272d-131">Если тип отвечает в течение времени существования других Уничтожаемые объекты, разработчикам необходим способ удалить, слишком.</span><span class="sxs-lookup"><span data-stu-id="9272d-131">If a type is responsible for the lifetime of other disposable objects, developers need a way to dispose of them, too.</span></span> <span data-ttu-id="9272d-132">С помощью контейнера `Dispose` метод является удобным способом для этого.</span><span class="sxs-lookup"><span data-stu-id="9272d-132">Using the container’s `Dispose` method is a convenient way to make this possible.</span></span>  
  
 <span data-ttu-id="9272d-133">**✓ DO** реализовать базовый шаблон Dispose и предоставлять метод завершения для типов, удерживающим ресурсы, которые должны быть освобождены явно и, не имеющие методов завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-133">**✓ DO** implement the Basic Dispose Pattern and provide a finalizer on types holding resources that need to be freed explicitly and that do not have finalizers.</span></span>  
  
 <span data-ttu-id="9272d-134">Например шаблон должен быть реализован для типов хранения буферов неуправляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="9272d-134">For example, the pattern should be implemented on types storing unmanaged memory buffers.</span></span> <span data-ttu-id="9272d-135">[Завершаемые типы](#finalizable_types) разделе представлены рекомендации, относящиеся к реализации методов завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-135">The [Finalizable Types](#finalizable_types) section discusses guidelines related to implementing finalizers.</span></span>  
  
 <span data-ttu-id="9272d-136">**✓ CONSIDER** реализации базовый шаблон Dispose в классах, сами не содержат неуправляемых ресурсов или высвобождаемые объекты но скорее всего имеются подтипы, которые выполняют.</span><span class="sxs-lookup"><span data-stu-id="9272d-136">**✓ CONSIDER** implementing the Basic Dispose Pattern on classes that themselves don’t hold unmanaged resources or disposable objects but are likely to have subtypes that do.</span></span>  
  
 <span data-ttu-id="9272d-137">Хорошим примером этого является <xref:System.IO.Stream?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="9272d-137">A great example of this is the <xref:System.IO.Stream?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="9272d-138">Несмотря на то, что это абстрактный базовый класс, который не содержит все ресурсы, у большинства из его подклассов, и по этой причине реализует этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="9272d-138">Although it is an abstract base class that doesn’t hold any resources, most of its subclasses do and because of this, it implements this pattern.</span></span>  
  
<a name="basic_pattern"></a>   
## <a name="basic-dispose-pattern"></a><span data-ttu-id="9272d-139">Шаблон удаления базовый</span><span class="sxs-lookup"><span data-stu-id="9272d-139">Basic Dispose Pattern</span></span>  
 <span data-ttu-id="9272d-140">Включает базовую реализацию шаблона `System.IDisposable` интерфейс и объявление `Dispose(bool)` метод, который реализует всю логику очистки ресурсов, совместный доступ к `Dispose` метод и необязательный метод завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-140">The basic implementation of the pattern involves implementing the `System.IDisposable` interface and declaring the `Dispose(bool)` method that implements all resource cleanup logic to be shared between the `Dispose` method and the optional finalizer.</span></span>  
  
 <span data-ttu-id="9272d-141">В следующем примере показана простая реализация из базового шаблона:</span><span class="sxs-lookup"><span data-stu-id="9272d-141">The following example shows a simple implementation of the basic pattern:</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    private SafeHandle resource; // handle to a resource  
  
    public DisposableResourceHolder() {  
        this.resource = ... // allocates the resource  
    }  
  
    public void Dispose() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposing) {  
            if (resource!= null) resource.Dispose();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="9272d-142">Логический параметр `disposing` указывает, был ли метод вызван из `IDisposable.Dispose` реализации или из метода завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-142">The Boolean parameter `disposing` indicates whether the method was invoked from the `IDisposable.Dispose` implementation or from the finalizer.</span></span> <span data-ttu-id="9272d-143">`Dispose(bool)` Реализации следует проверить параметр перед доступом к другим ссылаться на объекты (например, поле ресурса в предыдущем примере).</span><span class="sxs-lookup"><span data-stu-id="9272d-143">The `Dispose(bool)` implementation should check the parameter before accessing other reference objects (e.g., the resource field in the preceding sample).</span></span> <span data-ttu-id="9272d-144">Такие объекты должны быть доступны, только если метод вызывается из `IDisposable.Dispose` реализации (при `disposing` параметр имеет значение true).</span><span class="sxs-lookup"><span data-stu-id="9272d-144">Such objects should only be accessed when the method is called from the `IDisposable.Dispose` implementation (when the `disposing` parameter is equal to true).</span></span> <span data-ttu-id="9272d-145">Если метод вызывается из метода завершения (`disposing` имеет значение false), другие объекты не должны быть доступны.</span><span class="sxs-lookup"><span data-stu-id="9272d-145">If the method is invoked from the finalizer (`disposing` is false), other objects should not be accessed.</span></span> <span data-ttu-id="9272d-146">Причина в том что завершаются объекты, в непредсказуемой последовательности, и поэтому они, или любой из их зависимостей может быть уже закрыт.</span><span class="sxs-lookup"><span data-stu-id="9272d-146">The reason is that objects are finalized in an unpredictable order and so they, or any of their dependencies, might already have been finalized.</span></span>  
  
 <span data-ttu-id="9272d-147">Кроме того этот раздел относится к классам с базовым, который не реализует шаблон Dispose.</span><span class="sxs-lookup"><span data-stu-id="9272d-147">Also, this section applies to classes with a base that does not already implement the Dispose Pattern.</span></span> <span data-ttu-id="9272d-148">Если вы наследуете от класса, который уже реализует шаблон, просто заменить `Dispose(bool)` метод, чтобы предоставить логику очистки дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-148">If you are inheriting from a class that already implements the pattern, simply override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="9272d-149">**✓ DO** объявить `protected virtual void Dispose(bool disposing)` метод для централизации всю логику, связанную с освобождением неуправляемые ресурсы.</span><span class="sxs-lookup"><span data-stu-id="9272d-149">**✓ DO** declare a `protected virtual void Dispose(bool disposing)` method to centralize all logic related to releasing unmanaged resources.</span></span>  
  
 <span data-ttu-id="9272d-150">Очистка всех ресурсов должно выполняться в этом методе.</span><span class="sxs-lookup"><span data-stu-id="9272d-150">All resource cleanup should occur in this method.</span></span> <span data-ttu-id="9272d-151">Метод вызывается из оба метода завершения и `IDisposable.Dispose` метод.</span><span class="sxs-lookup"><span data-stu-id="9272d-151">The method is called from both the finalizer and the `IDisposable.Dispose` method.</span></span> <span data-ttu-id="9272d-152">Параметр будет иметь значение false, если вызван метод из внутри метода завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-152">The parameter will be false if being invoked from inside a finalizer.</span></span> <span data-ttu-id="9272d-153">Его следует использовать, чтобы убедиться, что любой код, выполняемый во время завершения не имеет доступа к другим объектам.</span><span class="sxs-lookup"><span data-stu-id="9272d-153">It should be used to ensure any code running during finalization is not accessing other finalizable objects.</span></span> <span data-ttu-id="9272d-154">В следующем разделе описываются подробности реализации методов завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-154">Details of implementing finalizers are described in the next section.</span></span>  
  
```csharp
protected virtual void Dispose(bool disposing) {  
    if (disposing) {  
        if (resource!= null) resource.Dispose();  
    }  
}  
```  
  
 <span data-ttu-id="9272d-155">**✓ DO** реализовать `IDisposable` интерфейс, просто вызвав `Dispose(true)` следуют `GC.SuppressFinalize(this)`.</span><span class="sxs-lookup"><span data-stu-id="9272d-155">**✓ DO** implement the `IDisposable` interface by simply calling `Dispose(true)` followed by `GC.SuppressFinalize(this)`.</span></span>  
  
 <span data-ttu-id="9272d-156">Вызов `SuppressFinalize` произойдет только в том случае, если `Dispose(true)` выполняется успешно.</span><span class="sxs-lookup"><span data-stu-id="9272d-156">The call to `SuppressFinalize` should only occur if `Dispose(true)` executes successfully.</span></span>  
  
```csharp
public void Dispose(){  
    Dispose(true);  
    GC.SuppressFinalize(this);  
}  
```  
  
 <span data-ttu-id="9272d-157">**X DO NOT** сделать без параметров `Dispose` виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="9272d-157">**X DO NOT** make the parameterless `Dispose` method virtual.</span></span>  
  
 <span data-ttu-id="9272d-158">`Dispose(bool)` Метод является тот, который должен переопределяться подклассами.</span><span class="sxs-lookup"><span data-stu-id="9272d-158">The `Dispose(bool)` method is the one that should be overridden by subclasses.</span></span>  
  
```csharp
// bad design  
public class DisposableResourceHolder : IDisposable {  
    public virtual void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
  
// good design  
public class DisposableResourceHolder : IDisposable {  
    public void Dispose() { ... }  
    protected virtual void Dispose(bool disposing) { ... }  
}  
```  
  
 <span data-ttu-id="9272d-159">**X DO NOT** объявлять все перегрузки `Dispose` не `Dispose()` и `Dispose(bool)`.</span><span class="sxs-lookup"><span data-stu-id="9272d-159">**X DO NOT** declare any overloads of the `Dispose` method other than `Dispose()` and `Dispose(bool)`.</span></span>  
  
 <span data-ttu-id="9272d-160">`Dispose` можно рассматривать зарезервированным словом для обозначения этот шаблон и избежать путаницы между компиляторы, разработчиков и пользователей.</span><span class="sxs-lookup"><span data-stu-id="9272d-160">`Dispose` should be considered a reserved word to help codify this pattern and prevent confusion among implementers, users, and compilers.</span></span> <span data-ttu-id="9272d-161">В некоторых языках можно автоматически реализовать этот шаблон для определенных типов.</span><span class="sxs-lookup"><span data-stu-id="9272d-161">Some languages might choose to automatically implement this pattern on certain types.</span></span>  
  
 <span data-ttu-id="9272d-162">**✓ DO** Разрешить `Dispose(bool)` метод, который вызывается несколько раз.</span><span class="sxs-lookup"><span data-stu-id="9272d-162">**✓ DO** allow the `Dispose(bool)` method to be called more than once.</span></span> <span data-ttu-id="9272d-163">Метод можно ничего не делать после первого вызова.</span><span class="sxs-lookup"><span data-stu-id="9272d-163">The method might choose to do nothing after the first call.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
  
    bool disposed = false;  
  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="9272d-164">**X AVOID** исключения изнутри `Dispose(bool)` только под критических ситуаций, где процесс, содержащий повреждена (утечки, несогласованные общее состояние и т. д.).</span><span class="sxs-lookup"><span data-stu-id="9272d-164">**X AVOID** throwing an exception from within `Dispose(bool)` except under critical situations where the containing process has been corrupted (leaks, inconsistent shared state, etc.).</span></span>  
  
 <span data-ttu-id="9272d-165">Пользователи ожидают, что вызов `Dispose` не приведет к появлению исключения.</span><span class="sxs-lookup"><span data-stu-id="9272d-165">Users expect that a call to `Dispose` will not raise an exception.</span></span>  
  
 <span data-ttu-id="9272d-166">Если `Dispose` может вызвать исключение, дальнейшей логики очистки в блок finally не будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="9272d-166">If `Dispose` could raise an exception, further finally-block cleanup logic will not execute.</span></span> <span data-ttu-id="9272d-167">Чтобы обойти эту проблему, пользователю может потребоваться перенос при каждом вызове `Dispose` (в блоке finally!) в блоке try, что приводит к очень сложные очистки обработчиков.</span><span class="sxs-lookup"><span data-stu-id="9272d-167">To work around this, the user would need to wrap every call to `Dispose` (within the finally block!) in a try block, which leads to very complex cleanup handlers.</span></span> <span data-ttu-id="9272d-168">Если выполнение `Dispose(bool disposing)` метода, никогда не выдал исключение, если disposing имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="9272d-168">If executing a `Dispose(bool disposing)` method, never throw an exception if disposing is false.</span></span> <span data-ttu-id="9272d-169">Таким образом, процесс будет прерван при выполнении внутри контекста метода завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-169">Doing so will terminate the process if executing inside a finalizer context.</span></span>  
  
 <span data-ttu-id="9272d-170">**✓ DO** throw <xref:System.ObjectDisposedException> из любой элемент, который нельзя использовать после удаления объекта.</span><span class="sxs-lookup"><span data-stu-id="9272d-170">**✓ DO** throw an <xref:System.ObjectDisposedException> from any member that cannot be used after the object has been disposed of.</span></span>  
  
```csharp
public class DisposableResourceHolder : IDisposable {  
    bool disposed = false;  
    SafeHandle resource; // handle to a resource  
  
    public void DoSomething() {  
        if (disposed) throw new ObjectDisposedException(...);  
        // now call some native methods using the resource   
        ...  
    }  
    protected virtual void Dispose(bool disposing) {  
        if (disposed) return;  
        // cleanup  
        ...  
        disposed = true;  
    }  
}  
```  
  
 <span data-ttu-id="9272d-171">**✓ CONSIDER** предоставление метода `Close()`, в дополнение к `Dispose()`, если закрыть является стандартной терминологии в области.</span><span class="sxs-lookup"><span data-stu-id="9272d-171">**✓ CONSIDER** providing method `Close()`, in addition to the `Dispose()`, if close is standard terminology in the area.</span></span>  
  
 <span data-ttu-id="9272d-172">При этом очень важно, что вносимые `Close` реализация идентична `Dispose` и рассмотрите возможность реализации `IDisposable.Dispose` метод явным образом.</span><span class="sxs-lookup"><span data-stu-id="9272d-172">When doing so, it is important that you make the `Close` implementation identical to `Dispose` and consider implementing the `IDisposable.Dispose` method explicitly.</span></span>  
  
```csharp
public class Stream : IDisposable {  
    IDisposable.Dispose() {  
        Close();  
    }  
    public void Close() {  
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
<a name="finalizable_types"></a>   
## <a name="finalizable-types"></a><span data-ttu-id="9272d-173">Финализируемое типы</span><span class="sxs-lookup"><span data-stu-id="9272d-173">Finalizable Types</span></span>  
 <span data-ttu-id="9272d-174">Финализируемое типы являются типами, которые расширяют базовый шаблон Dispose, переопределение метода завершения и предоставляя код финализации в `Dispose(bool)` метод.</span><span class="sxs-lookup"><span data-stu-id="9272d-174">Finalizable types are types that extend the Basic Dispose Pattern by overriding the finalizer and providing finalization code path in the `Dispose(bool)` method.</span></span>  
  
 <span data-ttu-id="9272d-175">Методы завершения их сложно реализовать правильно, в первую очередь потому, что нельзя сделать определенные (обычно) допущений о состоянии системы во время их выполнения.</span><span class="sxs-lookup"><span data-stu-id="9272d-175">Finalizers are notoriously difficult to implement correctly, primarily because you cannot make certain (normally valid) assumptions about the state of the system during their execution.</span></span> <span data-ttu-id="9272d-176">Тщательного анализа нужно учитывать следующие рекомендации.</span><span class="sxs-lookup"><span data-stu-id="9272d-176">The following guidelines should be taken into careful consideration.</span></span>  
  
 <span data-ttu-id="9272d-177">Обратите внимание, что некоторые рекомендации применяются не только к `Finalize` метод, но для кода, вызывается из метода завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-177">Note that some of the guidelines apply not just to the `Finalize` method, but to any code called from a finalizer.</span></span> <span data-ttu-id="9272d-178">В случае базовый шаблон Dispose определен ранее, это означает логику, которая выполняется внутри `Dispose(bool disposing)` при `disposing` параметр имеет значение false.</span><span class="sxs-lookup"><span data-stu-id="9272d-178">In the case of the Basic Dispose Pattern previously defined, this means logic that executes inside `Dispose(bool disposing)` when the `disposing` parameter is false.</span></span>  
  
 <span data-ttu-id="9272d-179">Если базовый класс уже завершаемые и реализует базовый шаблон Dispose, не следует переопределять `Finalize` еще раз.</span><span class="sxs-lookup"><span data-stu-id="9272d-179">If the base class already is finalizable and implements the Basic Dispose Pattern, you should not override `Finalize` again.</span></span> <span data-ttu-id="9272d-180">Следует вместо этого просто переопределить `Dispose(bool)` метод, чтобы предоставить логику очистки дополнительных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-180">You should instead just override the `Dispose(bool)` method to provide additional resource cleanup logic.</span></span>  
  
 <span data-ttu-id="9272d-181">Следующий код является примером завершаемые типа:</span><span class="sxs-lookup"><span data-stu-id="9272d-181">The following code shows an example of a finalizable type:</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    private IntPtr buffer; // unmanaged memory buffer  
    private SafeHandle resource; // disposable handle to a resource  
  
    public ComplexResourceHolder() {  
        this.buffer = ... // allocates memory  
        this.resource = ... // allocates the resource  
    }  
  
    protected virtual void Dispose(bool disposing) {  
            ReleaseBuffer(buffer); // release unmanaged memory  
        if (disposing) { // release other disposable objects  
            if (resource!= null) resource.Dispose();  
        }  
    }  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    public void Dispose() {
        Dispose(true);  
        GC.SuppressFinalize(this);  
    }  
}  
```  
  
 <span data-ttu-id="9272d-182">**X AVOID** внесения завершаемые типов.</span><span class="sxs-lookup"><span data-stu-id="9272d-182">**X AVOID** making types finalizable.</span></span>  
  
 <span data-ttu-id="9272d-183">Внимательно рассмотрите любой вариант, в которой вы считаете, что необходим метод завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-183">Carefully consider any case in which you think a finalizer is needed.</span></span> <span data-ttu-id="9272d-184">Что представляет собой реальное затраты, связанные с экземплярами с методы завершения, зрения сложность кода и производительности.</span><span class="sxs-lookup"><span data-stu-id="9272d-184">There is a real cost associated with instances with finalizers, from both a performance and code complexity standpoint.</span></span> <span data-ttu-id="9272d-185">Предпочитать, с помощью оболочки ресурса, например <xref:System.Runtime.InteropServices.SafeHandle> для инкапсуляции неуправляемых ресурсов, где это возможно, в этом случае метод завершения становится ненужным, так как оболочка отвечает за собственную очистки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="9272d-185">Prefer using resource wrappers such as <xref:System.Runtime.InteropServices.SafeHandle> to encapsulate unmanaged resources where possible, in which case a finalizer becomes unnecessary because the wrapper is responsible for its own resource cleanup.</span></span>  
  
 <span data-ttu-id="9272d-186">**X DO NOT** сделать завершаемые типов значений.</span><span class="sxs-lookup"><span data-stu-id="9272d-186">**X DO NOT** make value types finalizable.</span></span>  
  
 <span data-ttu-id="9272d-187">Только ссылочные типы фактически получить работу над средой CLR, и поэтому любая попытка поместить метод завершения для типа значения, будет игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="9272d-187">Only reference types actually get finalized by the CLR, and thus any attempt to place a finalizer on a value type will be ignored.</span></span> <span data-ttu-id="9272d-188">Компиляторы C# и C++ обеспечивает применение этого правила.</span><span class="sxs-lookup"><span data-stu-id="9272d-188">The C# and C++ compilers enforce this rule.</span></span>  
  
 <span data-ttu-id="9272d-189">**✓ DO** тип стал завершаемые, если тип отвечает за освобождение неуправляемых ресурсов, не имеет свой собственный метод завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-189">**✓ DO** make a type finalizable if the type is responsible for releasing an unmanaged resource that does not have its own finalizer.</span></span>  
  
 <span data-ttu-id="9272d-190">При реализации метода завершения, просто вызовите `Dispose(false)` и поместить всю логику очистки ресурсов внутри `Dispose(bool disposing)` метод.</span><span class="sxs-lookup"><span data-stu-id="9272d-190">When implementing the finalizer, simply call `Dispose(false)` and place all resource cleanup logic inside the `Dispose(bool disposing)` method.</span></span>  
  
```csharp
public class ComplexResourceHolder : IDisposable {  
  
    ~ComplexResourceHolder() {
        Dispose(false);  
    }  
  
    protected virtual void Dispose(bool disposing) {
        ...  
    }  
}  
```  
  
 <span data-ttu-id="9272d-191">**✓ DO** реализовать базовый шаблон Dispose для каждого типа подлежащим завершению.</span><span class="sxs-lookup"><span data-stu-id="9272d-191">**✓ DO** implement the Basic Dispose Pattern on every finalizable type.</span></span>  
  
 <span data-ttu-id="9272d-192">Это дает пользователям типа означает, что для явного выполнения детерминированная очистка этих же ресурсов, для которых отвечает метод завершения.</span><span class="sxs-lookup"><span data-stu-id="9272d-192">This gives users of the type a means to explicitly perform deterministic cleanup of those same resources for which the finalizer is responsible.</span></span>  
  
 <span data-ttu-id="9272d-193">**X DO NOT** доступ к любой это Завершаемые объекты в ветвь кода метода завершения, так как имеется значительный риск, что они будут уже завершен.</span><span class="sxs-lookup"><span data-stu-id="9272d-193">**X DO NOT** access any finalizable objects in the finalizer code path, because there is significant risk that they will have already been finalized.</span></span>  
  
 <span data-ttu-id="9272d-194">Например, финализируемые объект А, имеющий ссылку на другой объект завершаемые B нельзя использовать надежно B в виде метода завершения, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="9272d-194">For example, a finalizable object A that has a reference to another finalizable object B cannot reliably use B in A’s finalizer, or vice versa.</span></span> <span data-ttu-id="9272d-195">Методы завершения вызываются в произвольном порядке (хватает слабые гарантии упорядочения критическое завершение).</span><span class="sxs-lookup"><span data-stu-id="9272d-195">Finalizers are called in a random order (short of a weak ordering guarantee for critical finalization).</span></span>  
  
 <span data-ttu-id="9272d-196">Кроме того Имейте в виду, что объекты, хранящиеся в статических переменных будет собрана в определенных точках во время выгрузки домена приложения или при выходе из процесса.</span><span class="sxs-lookup"><span data-stu-id="9272d-196">Also, be aware that objects stored in static variables will get collected at certain points during an application domain unload or while exiting the process.</span></span> <span data-ttu-id="9272d-197">Доступ к статическую переменную, которая ссылается на объект завершаемые (или вызов статического метода, который может использовать значения, хранящиеся в статических переменных) не может быть безопасно if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> возвращает значение true.</span><span class="sxs-lookup"><span data-stu-id="9272d-197">Accessing a static variable that refers to a finalizable object (or calling a static method that might use values stored in static variables) might not be safe if <xref:System.Environment.HasShutdownStarted%2A?displayProperty=nameWithType> returns true.</span></span>  
  
 <span data-ttu-id="9272d-198">**✓ DO** сделать ваш `Finalize` метод, защищенный.</span><span class="sxs-lookup"><span data-stu-id="9272d-198">**✓ DO** make your `Finalize` method protected.</span></span>  
  
 <span data-ttu-id="9272d-199">Разработчики C#, C++ и VB.NET не обязательно волноваться об этом, так как компиляторы позволяют применить это правило.</span><span class="sxs-lookup"><span data-stu-id="9272d-199">C#, C++, and VB.NET developers do not need to worry about this, because the compilers help to enforce this guideline.</span></span>  
  
 <span data-ttu-id="9272d-200">**X DO NOT** escape позволяют исключения из метода завершения логики, за исключением критических системных сбоев.</span><span class="sxs-lookup"><span data-stu-id="9272d-200">**X DO NOT** let exceptions escape from the finalizer logic, except for system-critical failures.</span></span>  
  
 <span data-ttu-id="9272d-201">Если исключение из метода завершения, среда CLR будет завершать процесс работы весь процесс (начиная с .NET Framework версии 2.0), другие методы завершения, предотвращая выполнение и ресурсы от освобождения, контролируемым образом.</span><span class="sxs-lookup"><span data-stu-id="9272d-201">If an exception is thrown from a finalizer, the CLR will shut down the entire process (as of .NET Framework version 2.0), preventing other finalizers from executing and resources from being released in a controlled manner.</span></span>  
  
 <span data-ttu-id="9272d-202">**✓ CONSIDER** Создание и использование критических завершению объект (тип с типом иерархии, которая содержит <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) для ситуаций, в которых есть метод завершения абсолютно необходимо выполнить даже в случае выгрузки домена приложения принудительного и поток прерывает выполнение.</span><span class="sxs-lookup"><span data-stu-id="9272d-202">**✓ CONSIDER** creating and using a critical finalizable object (a type with a type hierarchy that contains <xref:System.Runtime.ConstrainedExecution.CriticalFinalizerObject>) for situations in which a finalizer absolutely must execute even in the face of forced application domain unloads and thread aborts.</span></span>  
  
 <span data-ttu-id="9272d-203">*Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="9272d-203">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9272d-204">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="9272d-204">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9272d-205">См. также</span><span class="sxs-lookup"><span data-stu-id="9272d-205">See also</span></span>

- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>  
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="9272d-206">Рекомендации по проектированию на основе Framework</span><span class="sxs-lookup"><span data-stu-id="9272d-206">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="9272d-207">Обычные шаблоны разработки</span><span class="sxs-lookup"><span data-stu-id="9272d-207">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
- [<span data-ttu-id="9272d-208">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="9272d-208">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
