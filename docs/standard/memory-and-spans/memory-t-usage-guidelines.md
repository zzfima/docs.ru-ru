---
title: Рекомендации по использованию структур Memory<T> и Span<T>
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: 0a614f628faa98be778c627573e4dddc462c9107
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121960"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="b687a-102">Рекомендации по использованию структур Memory\<T> и Span\<T></span><span class="sxs-lookup"><span data-stu-id="b687a-102">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="b687a-103">В .NET Core есть несколько типов, представляющих произвольную непрерывную область памяти.</span><span class="sxs-lookup"><span data-stu-id="b687a-103">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="b687a-104">В .NET Core 2.0 появились типы <xref:System.Span%601> и <xref:System.ReadOnlySpan%601>, которые являются упрощенными буферами памяти, поддерживаемыми управляемой или неуправляемой памятью.</span><span class="sxs-lookup"><span data-stu-id="b687a-104">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="b687a-105">Так как эти типы могут храниться только в стеке, они непригодны для ряда сценариев, включая вызовы асинхронных методов.</span><span class="sxs-lookup"><span data-stu-id="b687a-105">Because these types can only be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="b687a-106">В .NET Core 2.1 был добавлен ряд дополнительных типов, включая <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> и <xref:System.Buffers.MemoryPool%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-106">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="b687a-107">Как и <xref:System.Span%601>, <xref:System.Memory%601> и связанные с ним типы могут поддерживаться управляемой и неуправляемой памятью.</span><span class="sxs-lookup"><span data-stu-id="b687a-107">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="b687a-108">В отличие от <xref:System.Span%601><xref:System.Memory%601> может храниться в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="b687a-108">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can be stored on the managed heap.</span></span>

<span data-ttu-id="b687a-109"><xref:System.Span%601> и <xref:System.Memory%601> являются буферами структурированных данных, которые можно использовать в конвейерах.</span><span class="sxs-lookup"><span data-stu-id="b687a-109">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="b687a-110">То есть они разработаны так, чтобы некоторые или все данные могли быть эффективно переданы компонентам в конвейере, который способен их обрабатывать и при необходимости изменять буфер.</span><span class="sxs-lookup"><span data-stu-id="b687a-110">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="b687a-111">Так как <xref:System.Memory%601> и связанные с ним типы могут быть доступными нескольким компонентам или нескольким потокам, важно, чтобы разработчик следовал некоторым общим рекомендациям для создания надежного кода.</span><span class="sxs-lookup"><span data-stu-id="b687a-111">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="b687a-112">Владельцы, объекты-получатели и управление жизненным циклом</span><span class="sxs-lookup"><span data-stu-id="b687a-112">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="b687a-113">Так как буферы можно передавать от API к API, а доступ к буферам иногда может осуществляться из нескольких потоков, необходимо управлять временем их существования.</span><span class="sxs-lookup"><span data-stu-id="b687a-113">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="b687a-114">Есть три важных момента:</span><span class="sxs-lookup"><span data-stu-id="b687a-114">There are three core concepts:</span></span>

- <span data-ttu-id="b687a-115">**Владение**.</span><span class="sxs-lookup"><span data-stu-id="b687a-115">**Ownership**.</span></span> <span data-ttu-id="b687a-116">Владелец экземпляра буфера отвечает за управление его жизненным циклом, включая удаление буфера, который больше не используется.</span><span class="sxs-lookup"><span data-stu-id="b687a-116">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="b687a-117">У буфера может быть только один владелец.</span><span class="sxs-lookup"><span data-stu-id="b687a-117">All buffers have a single owner.</span></span> <span data-ttu-id="b687a-118">Владельцем обычно является компонент, который создал буфер или получил его из фабрики.</span><span class="sxs-lookup"><span data-stu-id="b687a-118">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="b687a-119">Право владения можно передавать. **Компонент А** может передать контроль над буфером **компоненту Б**, после чего **компонент А** больше не сможет использовать буфер, а **компонент Б** будет отвечать за удаление буфера, когда необходимость в нем исчезнет.</span><span class="sxs-lookup"><span data-stu-id="b687a-119">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="b687a-120">**Использование**.</span><span class="sxs-lookup"><span data-stu-id="b687a-120">**Consumption**.</span></span> <span data-ttu-id="b687a-121">Объект-получатель экземпляра буфера может выполнять чтение и запись в буфер.</span><span class="sxs-lookup"><span data-stu-id="b687a-121">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="b687a-122">У буфера одновременно может быть только один объект-получатель, если не обеспечен какой-либо внешний механизм синхронизации.</span><span class="sxs-lookup"><span data-stu-id="b687a-122">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="b687a-123">Обратите внимание, что объектом-получателя буфера не обязательно является владелец буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-123">Note that the active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="b687a-124">**Аренда**.</span><span class="sxs-lookup"><span data-stu-id="b687a-124">**Lease**.</span></span> <span data-ttu-id="b687a-125">Аренда — это срок, в течение которого определенный компонент может быть объектом-получателем буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-125">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="b687a-126">Следующий пример псевдокода иллюстрирует три этих понятия.</span><span class="sxs-lookup"><span data-stu-id="b687a-126">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="b687a-127">Он содержит метод `Main`, который создает буфер <xref:System.Memory%601> типа <xref:System.Char>, вызывает метод `WriteInt32ToBuffer` для записи строкового представления целого числа в буфер, а затем вызывает метод `DisplayBufferToConsole` для отображения значения буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-127">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

<span data-ttu-id="b687a-128">Метод `Main` создает буфер (в этом случае экземпляр <xref:System.Span%601>), поэтому он является его владельцем.</span><span class="sxs-lookup"><span data-stu-id="b687a-128">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="b687a-129">Таким образом, `Main` отвечает за удаление буфера, когда он больше не используется.</span><span class="sxs-lookup"><span data-stu-id="b687a-129">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="b687a-130">Он выполняет это путем вызова метода буфера <xref:System.Span%601.Clear?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b687a-130">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b687a-131">(Здесь метод <xref:System.Span%601.Clear> по сути очищает память буфера. У структуры <xref:System.Span%601> нет метода для удаления буфера.)</span><span class="sxs-lookup"><span data-stu-id="b687a-131">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="b687a-132">У буфера два объекта-получателя — `WriteInt32ToBuffer` и `DisplayBufferToConsole`.</span><span class="sxs-lookup"><span data-stu-id="b687a-132">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="b687a-133">Одновременно у буфера может быть только один объект-получатель (сначала `WriteInt32ToBuffer`, а затем `DisplayBufferToConsole`), и ни один из них не является владельцем буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-133">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="b687a-134">Обратите внимание, что объект-получатель здесь имеет не только возможность чтения из буфера. Объекты-получатели могут изменять содержимое буфера, как в случае `WriteInt32ToBuffer`, если предоставлены соответствующие права.</span><span class="sxs-lookup"><span data-stu-id="b687a-134">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="b687a-135">Метод `WriteInt32ToBuffer` арендует буфер (может быть его объектом-получателем), начиная с вызова метода и до момента его возвращения.</span><span class="sxs-lookup"><span data-stu-id="b687a-135">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="b687a-136">Аналогичным образом `DisplayBufferToConsole` арендует буфер на время своего выполнения, и аренда заканчивается, когда выполнение завершается.</span><span class="sxs-lookup"><span data-stu-id="b687a-136">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="b687a-137">(Не существует API для управления арендой, так как аренда — концептуальное понятие.)</span><span class="sxs-lookup"><span data-stu-id="b687a-137">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="b687a-138">Memory\<T> и модель "владелец — объект-получатель"</span><span class="sxs-lookup"><span data-stu-id="b687a-138">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="b687a-139">Как уже сообщалось в разделе [Владельцы, объекты-получатели и управление жизненным циклом](#owners-consumers-and-lifetime-management), у буфера всегда есть владелец.</span><span class="sxs-lookup"><span data-stu-id="b687a-139">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="b687a-140">В .NET Core поддерживаются две модели владения:</span><span class="sxs-lookup"><span data-stu-id="b687a-140">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="b687a-141">Модель с единственным владельцем.</span><span class="sxs-lookup"><span data-stu-id="b687a-141">A model that supports single ownership.</span></span> <span data-ttu-id="b687a-142">У буфера есть только один владелец в течение всего его времени существования.</span><span class="sxs-lookup"><span data-stu-id="b687a-142">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="b687a-143">Модель, позволяющая передавать право владения.</span><span class="sxs-lookup"><span data-stu-id="b687a-143">A model that supports ownership transfer.</span></span> <span data-ttu-id="b687a-144">Право владения буфером может передаваться от его первоначального владельца (его создателя) другому компоненту, после чего последний отвечает за управление временем существования буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-144">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="b687a-145">Новый владелец может, в свою очередь, передать право владения другому компоненту и так далее.</span><span class="sxs-lookup"><span data-stu-id="b687a-145">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="b687a-146">С помощью интерфейса <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> можно явно управлять правом владения буфером.</span><span class="sxs-lookup"><span data-stu-id="b687a-146">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="b687a-147"><xref:System.Buffers.IMemoryOwner%601> поддерживает обе модели владения.</span><span class="sxs-lookup"><span data-stu-id="b687a-147"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="b687a-148">Владельцем буфера является компонент, на который ссылается <xref:System.Buffers.IMemoryOwner%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-148">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="b687a-149">В следующем примере используется экземпляр <xref:System.Buffers.IMemoryOwner%601?> для указания владельца буфера <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-149">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of an <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="b687a-150">Этот пример можно также написать, используя [`using`](../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b687a-150">We can also write this example with the [`using`](../../csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="b687a-151">В этом коде:</span><span class="sxs-lookup"><span data-stu-id="b687a-151">In this code:</span></span>

- <span data-ttu-id="b687a-152">Экземпляр <xref:System.Buffers.IMemoryOwner%601> ссылается на метод `Main`, поэтому метод `Main` является владельцем буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-152">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="b687a-153">Методы `WriteInt32ToBuffer` и `DisplayBufferToConsole` принимают <xref:System.Memory%601> как общедоступный API-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b687a-153">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept <xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="b687a-154">Таким образом, они являются объектами-получателями буфера,</span><span class="sxs-lookup"><span data-stu-id="b687a-154">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="b687a-155">выступая в этой роли поочередно.</span><span class="sxs-lookup"><span data-stu-id="b687a-155">And they only consume it one at a time.</span></span>

<span data-ttu-id="b687a-156">При этом метод `WriteInt32ToBuffer` позволяет выполнить запись значения в буфер, а метод `DisplayBufferToConsole` — нет.</span><span class="sxs-lookup"><span data-stu-id="b687a-156">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="b687a-157">Чтобы отобразить этот факт, последний мог бы принять аргумент типа <xref:System.ReadOnlyMemory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-157">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="b687a-158">Дополнительную информацию о <xref:System.ReadOnlyMemory%601> см. в разделе [Правило 2. Используйте ReadOnlySpan\<T> или ReadOnlyMemory\<T>, если буфер должен быть доступен только для чтения](#rule-2).</span><span class="sxs-lookup"><span data-stu-id="b687a-158">For additional information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="b687a-159">Экземпляры Memory\<T> без владельца</span><span class="sxs-lookup"><span data-stu-id="b687a-159">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="b687a-160">Можно создать экземпляр <xref:System.Memory%601>, не используя <xref:System.Buffers.IMemoryOwner%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-160">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="b687a-161">В этом случае владелец буфера указывается неявно, поэтому поддерживается только модель с единственным владельцем.</span><span class="sxs-lookup"><span data-stu-id="b687a-161">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="b687a-162">Выполнить это можно следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b687a-162">You can do this by:</span></span>

- <span data-ttu-id="b687a-163">Вызвав один из конструкторов <xref:System.Memory%601> и передав `T[]`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b687a-163">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="b687a-164">Вызвав метод расширения [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) для создания экземпляра `ReadOnlyMemory<char>`.</span><span class="sxs-lookup"><span data-stu-id="b687a-164">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="b687a-165">Метод, который первоначально создает экземпляр <xref:System.Memory%601>, является неявным владельцем буфера.</span><span class="sxs-lookup"><span data-stu-id="b687a-165">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="b687a-166">Право владения нельзя передать другому компоненту, так как отсутствует экземпляр <xref:System.Buffers.IMemoryOwner%601>, позволяющий такую передачу.</span><span class="sxs-lookup"><span data-stu-id="b687a-166">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="b687a-167">(Как вариант, можете представить, что владельцем буфера является сборщик мусора среды выполнения, а все методы — это просто объекты-получатели буфера.)</span><span class="sxs-lookup"><span data-stu-id="b687a-167">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="b687a-168">Рекомендации по использованию</span><span class="sxs-lookup"><span data-stu-id="b687a-168">Usage guidelines</span></span>

<span data-ttu-id="b687a-169">Так как блок памяти имеет владельца, но предназначен для передачи нескольким компонентам, некоторые из которых могут одновременно работать с блоком памяти, необходимо следовать рекомендациям по использованию <xref:System.Memory%601> и <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-169">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="b687a-170">Причины такого поведения следующие:</span><span class="sxs-lookup"><span data-stu-id="b687a-170">Guidelines are necessary because:</span></span>

- <span data-ttu-id="b687a-171">Компонент может сохранить ссылку на блок памяти после того, как владелец буфера ее передал.</span><span class="sxs-lookup"><span data-stu-id="b687a-171">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="b687a-172">Компоненты могут одновременно работать с буфером, что приведет к повреждению данных в буфере.</span><span class="sxs-lookup"><span data-stu-id="b687a-172">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="b687a-173">Хотя хранимая в стеке структура <xref:System.Span%601> оптимизирует производительность, что делает <xref:System.Span%601> предпочтительным типом для работы с блоком памяти, структура <xref:System.Span%601> также подвержена ряду важных ограничений.</span><span class="sxs-lookup"><span data-stu-id="b687a-173">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions.</span></span> <span data-ttu-id="b687a-174">Важно понимать, когда следует использовать <xref:System.Span%601>, а когда — <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-174">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="b687a-175">Ниже приведены наши рекомендации для успешного использования <xref:System.Memory%601> и связанных типов.</span><span class="sxs-lookup"><span data-stu-id="b687a-175">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="b687a-176">Обратите внимание, что рекомендации по использованию <xref:System.Memory%601> и <xref:System.Span%601> также касаются <xref:System.ReadOnlyMemory%601> и <xref:System.ReadOnlySpan%601>, если прямо не заявлено об обратном.</span><span class="sxs-lookup"><span data-stu-id="b687a-176">Note that guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="b687a-177">**Правило 1. Для синхронных API по возможности используйте Span\<T> вместо Memory\<T> в качестве параметра**</span><span class="sxs-lookup"><span data-stu-id="b687a-177">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="b687a-178">Структура <xref:System.Span%601> более эффективна, чем <xref:System.Memory%601>, и обеспечивает больше возможностей по работе со смежными буферами памяти.</span><span class="sxs-lookup"><span data-stu-id="b687a-178"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="b687a-179"><xref:System.Span%601> также обеспечивает лучшую производительность, чем <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-179"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>.</span></span> <span data-ttu-id="b687a-180">Наконец, вы можете использовать свойство <xref:System.Memory%601.Span?displayProperty=nameWithType> для преобразования экземпляра <xref:System.Memory%601> в <xref:System.Span%601>, тогда как нельзя преобразовать Span\<T > в Memory\<T>.</span><span class="sxs-lookup"><span data-stu-id="b687a-180">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="b687a-181">Поэтому, если у вызывающих объектов есть экземпляр <xref:System.Memory%601>, они в любом случае смогут вызвать методы с помощью параметров <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-181">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="b687a-182">Использование параметра типа <xref:System.Span%601> вместо типа <xref:System.Memory%601> также помогает выполнить правильную реализацию метода использования.</span><span class="sxs-lookup"><span data-stu-id="b687a-182">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="b687a-183">Вам нужно обеспечить автоматические проверки времени компиляции, гарантирующие, что доступ к буферу осуществляется только в период его аренды методом (подробнее об этом далее).</span><span class="sxs-lookup"><span data-stu-id="b687a-183">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="b687a-184">В некоторых случаях вам придется использовать параметр <xref:System.Memory%601> вместо параметра <xref:System.Span%601> даже в случае полной синхронизации.</span><span class="sxs-lookup"><span data-stu-id="b687a-184">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="b687a-185">Может оказаться так, что API, от которого вы зависите, принимает только аргументы <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-185">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="b687a-186">Это нормально, но следует учитывать компромиссы, связанные с синхронным использованием <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-186">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2" />

<span data-ttu-id="b687a-187">**Правило 2. Используйте ReadOnlySpan\<T> или ReadOnlyMemory\<T>, если буфер должен быть доступен только для чтения**</span><span class="sxs-lookup"><span data-stu-id="b687a-187">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="b687a-188">В предыдущих примерах метод `DisplayBufferToConsole` только считывает данные из буфера, не изменяя его содержимое.</span><span class="sxs-lookup"><span data-stu-id="b687a-188">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="b687a-189">Сигнатуру метода следует изменить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b687a-189">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="b687a-190">На самом деле, если мы объединим это правило с правилом 1, то сможем добиться лучшего результата и переписать сигнатуру метода следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b687a-190">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="b687a-191">Метод `DisplayBufferToConsole` теперь работает с практически всеми возможными типами буфера: `T[]`, блоком памяти, выделяемым с помощью ключевого слова [stackalloc](../../csharp/language-reference/operators/stackalloc.md) и т. д.</span><span class="sxs-lookup"><span data-stu-id="b687a-191">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), and so on.</span></span> <span data-ttu-id="b687a-192">Ему даже можно непосредственно передать <xref:System.String>!</span><span class="sxs-lookup"><span data-stu-id="b687a-192">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="b687a-193">**Правило 3. Если метод принимает Memory\<T> и возвращает `void`, вам не следует использовать экземпляр Memory\<T> после возврата метода**</span><span class="sxs-lookup"><span data-stu-id="b687a-193">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="b687a-194">Это относится к упомянутой ранее концепции аренды.</span><span class="sxs-lookup"><span data-stu-id="b687a-194">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="b687a-195">Аренда возвращающего слово void метода в экземпляре <xref:System.Memory%601> начинается с началом выполнения метода и заканчивается, когда он завершает работу.</span><span class="sxs-lookup"><span data-stu-id="b687a-195">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="b687a-196">Рассмотрим следующий пример, в котором вызывается `Log` в цикле на основе входных данных из консоли.</span><span class="sxs-lookup"><span data-stu-id="b687a-196">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="b687a-197">Если `Log` — это полностью синхронный метод, этот код будет работать ожидаемо, так как в любой момент времени у экземпляра памяти есть только один объект-получатель.</span><span class="sxs-lookup"><span data-stu-id="b687a-197">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="b687a-198">Но представьте себе, если реализация `Log` будет такой.</span><span class="sxs-lookup"><span data-stu-id="b687a-198">But imagine instead that `Log` has this implementation.</span></span>

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

<span data-ttu-id="b687a-199">В этом случае метод `Log` нарушает свою аренду, так как он пытается использовать экземпляр <xref:System.Memory%601> в фоновом режиме после возврата первоначального метода.</span><span class="sxs-lookup"><span data-stu-id="b687a-199">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="b687a-200">Метод `Main` может изменять буфер, когда `Log` пытается выполнить чтение из него, что может привести к повреждению данных.</span><span class="sxs-lookup"><span data-stu-id="b687a-200">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="b687a-201">Есть несколько способов устранить эту проблему.</span><span class="sxs-lookup"><span data-stu-id="b687a-201">There are several ways to resolve this:</span></span>

- <span data-ttu-id="b687a-202">Метод `Log` может возвращать <xref:System.Threading.Tasks.Task> вместо `void`, как это сделано в следующей реализации метода `Log`.</span><span class="sxs-lookup"><span data-stu-id="b687a-202">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="b687a-203">`Log` можно реализовать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b687a-203">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="b687a-204">**Правило 4. Если метод принимает Memory\<T> и возвращает Task, не следует использовать экземпляр Memory\<T> после перехода Task в конечное состояние**</span><span class="sxs-lookup"><span data-stu-id="b687a-204">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="b687a-205">Это попросту асинхронный вариант правила 3.</span><span class="sxs-lookup"><span data-stu-id="b687a-205">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="b687a-206">Метод `Log` из предыдущего примера можно записать следующим образом в соответствии с этим правилом.</span><span class="sxs-lookup"><span data-stu-id="b687a-206">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="b687a-207">Здесь "конечное состояние" означает, что выполнение Task завершается успешно или сбоем, или же отменяется.</span><span class="sxs-lookup"><span data-stu-id="b687a-207">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="b687a-208">Другими словами "конечное состояния" означает "отсутствие чего-либо, связанного с ожиданием возврата или продолжением выполнения".</span><span class="sxs-lookup"><span data-stu-id="b687a-208">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="b687a-209">Эти рекомендации относятся к методам, которые возвращают <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> или любой аналогичный тип.</span><span class="sxs-lookup"><span data-stu-id="b687a-209">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="b687a-210">**Правило 5. Если конструктор принимает Memory\<T> в качестве параметра, предполагается, что методы экземпляра созданного объекта являются объектами-получателями экземпляра Memory\<T>**</span><span class="sxs-lookup"><span data-stu-id="b687a-210">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="b687a-211">Рассмотрим следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b687a-211">Consider the following example:</span></span>

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

<span data-ttu-id="b687a-212">Здесь конструктор `OddValueExtractor` принимает `ReadOnlyMemory<int>` в качестве параметра конструктора, поэтому сам конструктор является объектом-получателем экземпляра `ReadOnlyMemory<int>`, а все методы экземпляра возвращаемого значения также являются объектами-получателями исходного экземпляра `ReadOnlyMemory<int>`.</span><span class="sxs-lookup"><span data-stu-id="b687a-212">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="b687a-213">Это означает, что `TryReadNextOddValue` — это объект-получатель экземпляра `ReadOnlyMemory<int>`, хотя экземпляр не передается непосредственно в метод `TryReadNextOddValue`.</span><span class="sxs-lookup"><span data-stu-id="b687a-213">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="b687a-214">**Правило 6. Если у вашего типа есть настраиваемое Memory\<T>-типизированное свойство (или эквивалентный метод экземпляра), предполагается, что методы экземпляра для этого объекта являются объектами-получателями экземпляра Memory\<T>**</span><span class="sxs-lookup"><span data-stu-id="b687a-214">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="b687a-215">Это всего лишь разновидность правила 5.</span><span class="sxs-lookup"><span data-stu-id="b687a-215">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="b687a-216">Это правило существует, так как предполагается, что методы задания свойств или эквивалентные методы записывают и сохраняют свои входные данные, чтобы методы экземпляра того же объекта могли использовать записанное состояние.</span><span class="sxs-lookup"><span data-stu-id="b687a-216">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="b687a-217">Это правило иллюстрирует следующий пример.</span><span class="sxs-lookup"><span data-stu-id="b687a-217">The following example triggers this rule:</span></span>

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

<span data-ttu-id="b687a-218">**Правило 7. Если в IMemoryOwner\<T> присутствует ссылка, необходимо в определенный момент исключить ее или передать ее право владения (но не одновременно).**</span><span class="sxs-lookup"><span data-stu-id="b687a-218">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="b687a-219">Так как экземпляр <xref:System.Memory%601> может обслуживаться управляемой или неуправляемой памятью, владелец должен вызвать <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>, когда завершится работа с экземпляром <xref:System.Memory%601>.</span><span class="sxs-lookup"><span data-stu-id="b687a-219">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="b687a-220">Кроме того, владелец может передать право владения экземпляром <xref:System.Buffers.IMemoryOwner%601> другому компоненту, после чего этот компонент будет отвечать за вызов <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> в соответствующее время (подробнее об этом далее).</span><span class="sxs-lookup"><span data-stu-id="b687a-220">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="b687a-221">Сбой при вызове метода <xref:System.Buffers.MemoryPool%601.Dispose%2A> может привести к утечкам неуправляемой памяти или другому снижению производительности.</span><span class="sxs-lookup"><span data-stu-id="b687a-221">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="b687a-222">Это правило также применяется к коду, который вызывает фабричные методы, такие как <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b687a-222">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b687a-223">Вызывающий объект становится владельцем возвращаемого <xref:System.Buffers.IMemoryOwner%601> и отвечает за удаление экземпляра после завершения.</span><span class="sxs-lookup"><span data-stu-id="b687a-223">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="b687a-224">**Правило 8. Если в рабочей области API у вас присутствует параметр IMemoryOwner\<T>, вы принимаете право владения этим экземпляром**</span><span class="sxs-lookup"><span data-stu-id="b687a-224">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="b687a-225">Прием экземпляра этого типа означает, что ваш компонент собирается стать владельцем этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b687a-225">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="b687a-226">Компонент будет отвечать за правильное удаление экземпляра в соответствии с правилом 7.</span><span class="sxs-lookup"><span data-stu-id="b687a-226">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="b687a-227">Любой компонент, который передает право владения экземпляром <xref:System.Buffers.IMemoryOwner%601> другому компоненту, больше не должен использовать этот экземпляр после завершения вызова метода.</span><span class="sxs-lookup"><span data-stu-id="b687a-227">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b687a-228">Если ваш конструктор принимает <xref:System.Buffers.IMemoryOwner%601> в качестве параметра, его тип должен реализовывать <xref:System.IDisposable>, а ваш метод <xref:System.IDisposable.Dispose%2A> вызывать <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b687a-228">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="b687a-229">**Правило 9. Если вы создаете оболочку для синхронного метода p/invoke, API должен принимать Span\<T> в качестве параметра.**</span><span class="sxs-lookup"><span data-stu-id="b687a-229">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="b687a-230">В соответствии с правилом 1, <xref:System.Span%601> — это тот тип, который обычно следует использовать для синхронных API.</span><span class="sxs-lookup"><span data-stu-id="b687a-230">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="b687a-231">Вы можете закрепить экземпляры <xref:System.Span%601> с помощью ключевого слова [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b687a-231">You can pin <xref:System.Span%601> instances via the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="b687a-232">В предыдущем примере `pbData` может принимать значение NULL, например, если входной диапазон пуст.</span><span class="sxs-lookup"><span data-stu-id="b687a-232">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="b687a-233">Если экспортированный метод категорически требует, чтобы параметр `pbData` не мог возвращать значение NULL, даже если `cbData` равно 0, метод может быть реализован следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b687a-233">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="b687a-234">**Правило 10. Если вы создаете оболочку для асинхронного метода p/invoke, API должен принимать Memory\<T> в качестве параметра**</span><span class="sxs-lookup"><span data-stu-id="b687a-234">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="b687a-235">Так как ключевое слово [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) нельзя использовать для асинхронных операций, используйте метод <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType>, чтобы закрепить экземпляры <xref:System.Memory%601>, независимо от вида непрерывной памяти, представленной экземпляром.</span><span class="sxs-lookup"><span data-stu-id="b687a-235">Since you cannot use the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="b687a-236">В следующем примере показано, как использовать этот API, чтобы выполнить вызов асинхронного метода p/invoke.</span><span class="sxs-lookup"><span data-stu-id="b687a-236">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)state;
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a><span data-ttu-id="b687a-237">См. также</span><span class="sxs-lookup"><span data-stu-id="b687a-237">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
