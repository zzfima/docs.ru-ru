---
title: 'Сведения о вызывающем объекте (F #)'
description: Описывает, как использовать информационные атрибуты аргумента вызывающего объекта, чтобы получить сведения о вызывающем объекте из метода.
ms.date: 04/25/2017
ms.openlocfilehash: 0f2f4b16804d9156d234cc29d1f72ebe80a5b556
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44353451"
---
# <a name="caller-information"></a><span data-ttu-id="362c0-103">Сведения о вызывающем объекте</span><span class="sxs-lookup"><span data-stu-id="362c0-103">Caller information</span></span>

<span data-ttu-id="362c0-104">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="362c0-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="362c0-105">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="362c0-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="362c0-106">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="362c0-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="362c0-107">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="362c0-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="362c0-108">В следующей таблице перечислены информационные атрибуты вызывающего объекта, которые определены в [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) пространство имен:</span><span class="sxs-lookup"><span data-stu-id="362c0-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="362c0-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="362c0-109">Attribute</span></span>|<span data-ttu-id="362c0-110">Описание</span><span class="sxs-lookup"><span data-stu-id="362c0-110">Description</span></span>|<span data-ttu-id="362c0-111">Тип</span><span class="sxs-lookup"><span data-stu-id="362c0-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="362c0-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="362c0-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="362c0-113">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="362c0-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="362c0-114">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="362c0-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="362c0-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="362c0-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="362c0-116">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="362c0-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="362c0-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="362c0-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="362c0-118">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="362c0-118">Method or property name of the caller.</span></span> <span data-ttu-id="362c0-119">См. в разделе "имена элементов" Далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="362c0-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="362c0-120">Пример</span><span class="sxs-lookup"><span data-stu-id="362c0-120">Example</span></span>

<span data-ttu-id="362c0-121">Следующий пример показывает, как эти атрибуты можно использовать для трассировки вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="362c0-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="362c0-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="362c0-122">Remarks</span></span>

<span data-ttu-id="362c0-123">Информационные атрибуты вызывающего объекта может применяться только к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="362c0-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="362c0-124">Необходимо указать явное значение для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="362c0-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="362c0-125">Информационные атрибуты вызывающего объекта при компиляции для записи правильное значение для каждого необязательного параметра, атрибут информация вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="362c0-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="362c0-126">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="362c0-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="362c0-127">В отличие от результатов [StackTrace](/dotnet/api/system.diagnostics.stacktrace) свойство для исключений, результаты не затрагиваются обфускацией.</span><span class="sxs-lookup"><span data-stu-id="362c0-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="362c0-128">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="362c0-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="362c0-129">Имена членов</span><span class="sxs-lookup"><span data-stu-id="362c0-129">Member names</span></span>

<span data-ttu-id="362c0-130">Можно использовать [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, чтобы не указывать имя члена в виде `String` аргумента в вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="362c0-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="362c0-131">При использовании этого метода, позволяет избежать проблемы рефакторинга и переименования неизменная `String` значения.</span><span class="sxs-lookup"><span data-stu-id="362c0-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="362c0-132">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="362c0-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="362c0-133">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="362c0-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="362c0-134">Реализация [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) интерфейс во время привязки данных.</span><span class="sxs-lookup"><span data-stu-id="362c0-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="362c0-135">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="362c0-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="362c0-136">Без [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="362c0-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="362c0-137">На следующем рисунке показана член имена, которые возвращаются при использовании атрибут CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="362c0-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="362c0-138">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="362c0-138">Calls occurs within</span></span>|<span data-ttu-id="362c0-139">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="362c0-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="362c0-140">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="362c0-140">Method, property, or event</span></span>|<span data-ttu-id="362c0-141">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="362c0-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="362c0-142">Конструктор</span><span class="sxs-lookup"><span data-stu-id="362c0-142">Constructor</span></span>|<span data-ttu-id="362c0-143">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="362c0-143">The string ".ctor"</span></span>|
|<span data-ttu-id="362c0-144">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="362c0-144">Static constructor</span></span>|<span data-ttu-id="362c0-145">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="362c0-145">The string ".cctor"</span></span>|
|<span data-ttu-id="362c0-146">Деструктор</span><span class="sxs-lookup"><span data-stu-id="362c0-146">Destructor</span></span>|<span data-ttu-id="362c0-147">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="362c0-147">The string "Finalize"</span></span>|
|<span data-ttu-id="362c0-148">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="362c0-148">User-defined operators or conversions</span></span>|<span data-ttu-id="362c0-149">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="362c0-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="362c0-150">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="362c0-150">Attribute constructor</span></span>|<span data-ttu-id="362c0-151">Имя члена, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="362c0-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="362c0-152">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="362c0-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="362c0-153">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="362c0-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="362c0-154">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="362c0-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="362c0-155">См. также</span><span class="sxs-lookup"><span data-stu-id="362c0-155">See also</span></span>

- [<span data-ttu-id="362c0-156">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="362c0-156">Attributes</span></span>](attributes.md)  
- [<span data-ttu-id="362c0-157">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="362c0-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
- [<span data-ttu-id="362c0-158">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="362c0-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
