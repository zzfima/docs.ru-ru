---
title: Сведения о вызывающем объекте (C#)
ms.date: 07/20/2015
ms.assetid: ffad3d24-2fb7-4641-9124-53b5bc91d339
ms.openlocfilehash: 4b2c34945b47db01b0e655f68f92e4dae7445c2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595350"
---
# <a name="caller-information-c"></a><span data-ttu-id="90d67-102">Сведения о вызывающем объекте (C#)</span><span class="sxs-lookup"><span data-stu-id="90d67-102">Caller Information (C#)</span></span>

<span data-ttu-id="90d67-103">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="90d67-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="90d67-104">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="90d67-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="90d67-105">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="90d67-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="90d67-106">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90d67-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="90d67-107">В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в пространстве имен <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="90d67-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="90d67-108">attribute</span><span class="sxs-lookup"><span data-stu-id="90d67-108">Attribute</span></span>|<span data-ttu-id="90d67-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="90d67-109">Description</span></span>|<span data-ttu-id="90d67-110">Type</span><span class="sxs-lookup"><span data-stu-id="90d67-110">Type</span></span>|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="90d67-111">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="90d67-111">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="90d67-112">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="90d67-112">This is the file path at compile time.</span></span>|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="90d67-113">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="90d67-113">Line number in the source file at which the method is called.</span></span>|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="90d67-114">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="90d67-114">Method or property name of the caller.</span></span> <span data-ttu-id="90d67-115">См. подраздел [Имена членов](#member-names) ниже.</span><span class="sxs-lookup"><span data-stu-id="90d67-115">See [Member Names](#member-names) later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="90d67-116">Пример</span><span class="sxs-lookup"><span data-stu-id="90d67-116">Example</span></span>

<span data-ttu-id="90d67-117">В следующем примере показано, как использовать информационные атрибуты вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="90d67-117">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="90d67-118">При каждом вызове метода `TraceMessage` сведения о вызывающем объекте подставляются в качестве аргументов необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="90d67-118">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [System.Runtime.CompilerServices.CallerMemberName] string memberName = "",
        [System.Runtime.CompilerServices.CallerFilePath] string sourceFilePath = "",
        [System.Runtime.CompilerServices.CallerLineNumber] int sourceLineNumber = 0)
{
    System.Diagnostics.Trace.WriteLine("message: " + message);
    System.Diagnostics.Trace.WriteLine("member name: " + memberName);
    System.Diagnostics.Trace.WriteLine("source file path: " + sourceFilePath);
    System.Diagnostics.Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

## <a name="remarks"></a><span data-ttu-id="90d67-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="90d67-119">Remarks</span></span>

<span data-ttu-id="90d67-120">Для каждого необязательного параметра необходимо указать явное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90d67-120">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="90d67-121">Нельзя применять информационные атрибуты вызывающего объекта к параметрам, которые не были указаны как необязательные.</span><span class="sxs-lookup"><span data-stu-id="90d67-121">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>

<span data-ttu-id="90d67-122">Информационные атрибуты вызывающего объекта не делают параметр необязательным.</span><span class="sxs-lookup"><span data-stu-id="90d67-122">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="90d67-123">Вместо этого они влияют на значение по умолчанию, которое передается, если аргумент был опущен.</span><span class="sxs-lookup"><span data-stu-id="90d67-123">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>

<span data-ttu-id="90d67-124">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="90d67-124">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="90d67-125">В отличие от результатов свойства <xref:System.Exception.StackTrace%2A> для исключений, результаты не затрагиваются запутыванием кода.</span><span class="sxs-lookup"><span data-stu-id="90d67-125">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="90d67-126">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="90d67-126">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

### <a name="member-names"></a><span data-ttu-id="90d67-127">Имена членов</span><span class="sxs-lookup"><span data-stu-id="90d67-127">Member names</span></span>

<span data-ttu-id="90d67-128">Можно использовать атрибут `CallerMemberName`, чтобы не указывать имя члена в виде аргумента `String` вызываемому методу.</span><span class="sxs-lookup"><span data-stu-id="90d67-128">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="90d67-129">Этот прием позволяет избежать проблемы, заключающейся в том, что **операция рефакторинга и переименования** не изменяет значений `String`.</span><span class="sxs-lookup"><span data-stu-id="90d67-129">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="90d67-130">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="90d67-130">This benefit is especially useful for the following tasks:</span></span>

- <span data-ttu-id="90d67-131">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="90d67-131">Using tracing and diagnostic routines.</span></span>

- <span data-ttu-id="90d67-132">Реализация интерфейса <xref:System.ComponentModel.INotifyPropertyChanged> при привязке данных.</span><span class="sxs-lookup"><span data-stu-id="90d67-132">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="90d67-133">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="90d67-133">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="90d67-134">Если атрибут `CallerMemberName` не используется, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="90d67-134">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="90d67-135">В следующей таблице представлены имена членов, возвращаемых при использовании атрибута `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="90d67-135">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>

|<span data-ttu-id="90d67-136">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="90d67-136">Calls occurs within</span></span>|<span data-ttu-id="90d67-137">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="90d67-137">Member name result</span></span>|
|-|-|
|<span data-ttu-id="90d67-138">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="90d67-138">Method, property, or event</span></span>|<span data-ttu-id="90d67-139">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="90d67-139">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="90d67-140">Конструктор</span><span class="sxs-lookup"><span data-stu-id="90d67-140">Constructor</span></span>|<span data-ttu-id="90d67-141">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="90d67-141">The string ".ctor"</span></span>|
|<span data-ttu-id="90d67-142">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="90d67-142">Static constructor</span></span>|<span data-ttu-id="90d67-143">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="90d67-143">The string ".cctor"</span></span>|
|<span data-ttu-id="90d67-144">Деструктор</span><span class="sxs-lookup"><span data-stu-id="90d67-144">Destructor</span></span>|<span data-ttu-id="90d67-145">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="90d67-145">The string "Finalize"</span></span>|
|<span data-ttu-id="90d67-146">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="90d67-146">User-defined operators or conversions</span></span>|<span data-ttu-id="90d67-147">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="90d67-147">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="90d67-148">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="90d67-148">Attribute constructor</span></span>|<span data-ttu-id="90d67-149">Имя метода или свойства, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="90d67-149">The name of the method or property to which the attribute is applied.</span></span> <span data-ttu-id="90d67-150">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="90d67-150">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="90d67-151">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="90d67-151">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="90d67-152">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90d67-152">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="90d67-153">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90d67-153">See also</span></span>

- [<span data-ttu-id="90d67-154">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="90d67-154">Attributes (C#)</span></span>](./attributes/index.md)
- [<span data-ttu-id="90d67-155">Общие атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="90d67-155">Common Attributes (C#)</span></span>](./attributes/common-attributes.md)
- [<span data-ttu-id="90d67-156">Именованные и необязательные аргументы</span><span class="sxs-lookup"><span data-stu-id="90d67-156">Named and Optional Arguments</span></span>](../classes-and-structs/named-and-optional-arguments.md)
- [<span data-ttu-id="90d67-157">Основные понятия программирования (C#)</span><span class="sxs-lookup"><span data-stu-id="90d67-157">Programming Concepts (C#)</span></span>](./index.md)
