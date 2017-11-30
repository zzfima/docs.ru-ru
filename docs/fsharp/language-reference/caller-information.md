---
title: "Сведения о вызывающем объекте (F #)"
description: "Описывает, как использовать информационные атрибуты аргумент вызывающего, чтобы получить сведения о вызывающем объекте из метода."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a><span data-ttu-id="9084a-104">Сведения о вызывающем объекте</span><span class="sxs-lookup"><span data-stu-id="9084a-104">Caller information</span></span>

<span data-ttu-id="9084a-105">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="9084a-105">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="9084a-106">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="9084a-106">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="9084a-107">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="9084a-107">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="9084a-108">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9084a-108">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="9084a-109">В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) пространство имен:</span><span class="sxs-lookup"><span data-stu-id="9084a-109">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="9084a-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9084a-110">Attribute</span></span>|<span data-ttu-id="9084a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9084a-111">Description</span></span>|<span data-ttu-id="9084a-112">Тип</span><span class="sxs-lookup"><span data-stu-id="9084a-112">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="9084a-113">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="9084a-113">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="9084a-114">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="9084a-114">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="9084a-115">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9084a-115">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="9084a-116">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="9084a-116">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="9084a-117">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="9084a-117">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="9084a-118">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="9084a-118">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="9084a-119">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="9084a-119">Method or property name of the caller.</span></span> <span data-ttu-id="9084a-120">В разделе имена членов далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="9084a-120">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="9084a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="9084a-121">Example</span></span>

<span data-ttu-id="9084a-122">Следующий пример показывает, как эти атрибуты можно использовать для трассировки вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="9084a-122">The following example shows how you might use these attributes to trace a caller.</span></span>

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a><span data-ttu-id="9084a-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="9084a-123">Remarks</span></span>

<span data-ttu-id="9084a-124">Информационные атрибуты вызывающего может применяться только к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="9084a-124">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="9084a-125">Необходимо указать явное значение для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="9084a-125">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="9084a-126">Информационные атрибуты вызывающего объекта привести к записи правильное значение для каждого необязательного параметра, помеченной атрибутом информация вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="9084a-126">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="9084a-127">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9084a-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="9084a-128">В отличие от результатов [StackTrace](/dotnet/api/system.diagnostics.stacktrace) свойство для исключений, результаты не затрагиваются запутыванием кода.</span><span class="sxs-lookup"><span data-stu-id="9084a-128">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="9084a-129">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="9084a-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="9084a-130">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="9084a-130">Member names</span></span>

<span data-ttu-id="9084a-131">Можно использовать [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, чтобы не указывать имя члена в виде `String` аргументов для вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="9084a-131">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="9084a-132">При использовании этого метода позволяет избежать проблемы, не меняется, рефакторинга и переименования `String` значения.</span><span class="sxs-lookup"><span data-stu-id="9084a-132">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="9084a-133">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="9084a-133">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="9084a-134">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="9084a-134">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="9084a-135">Реализация [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) интерфейс при привязке данных.</span><span class="sxs-lookup"><span data-stu-id="9084a-135">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="9084a-136">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="9084a-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="9084a-137">Без [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="9084a-137">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="9084a-138">Следующая диаграмма показывает элемент имена, которые возвращаются при использовании атрибут CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="9084a-138">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="9084a-139">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="9084a-139">Calls occurs within</span></span>|<span data-ttu-id="9084a-140">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="9084a-140">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="9084a-141">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="9084a-141">Method, property, or event</span></span>|<span data-ttu-id="9084a-142">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="9084a-142">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="9084a-143">Конструктор</span><span class="sxs-lookup"><span data-stu-id="9084a-143">Constructor</span></span>|<span data-ttu-id="9084a-144">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="9084a-144">The string ".ctor"</span></span>|
|<span data-ttu-id="9084a-145">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="9084a-145">Static constructor</span></span>|<span data-ttu-id="9084a-146">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="9084a-146">The string ".cctor"</span></span>|
|<span data-ttu-id="9084a-147">Деструктор</span><span class="sxs-lookup"><span data-stu-id="9084a-147">Destructor</span></span>|<span data-ttu-id="9084a-148">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="9084a-148">The string "Finalize"</span></span>|
|<span data-ttu-id="9084a-149">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="9084a-149">User-defined operators or conversions</span></span>|<span data-ttu-id="9084a-150">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="9084a-150">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="9084a-151">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="9084a-151">Attribute constructor</span></span>|<span data-ttu-id="9084a-152">Имя члена, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="9084a-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="9084a-153">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="9084a-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="9084a-154">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="9084a-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="9084a-155">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9084a-155">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9084a-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9084a-156">See also</span></span>
 [<span data-ttu-id="9084a-157">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9084a-157">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="9084a-158">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="9084a-158">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="9084a-159">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="9084a-159">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
