---
title: 'Сведения о вызывающем объекте (F #)'
description: Описывает, как использовать информационные атрибуты аргумент вызывающего, чтобы получить сведения о вызывающем объекте из метода.
ms.date: 04/25/2017
ms.openlocfilehash: 6fd80213cdaf2c4662fd4c2ed9eaf8949e397efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564809"
---
# <a name="caller-information"></a><span data-ttu-id="cdbcc-103">Сведения о вызывающем объекте</span><span class="sxs-lookup"><span data-stu-id="cdbcc-103">Caller information</span></span>

<span data-ttu-id="cdbcc-104">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-104">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="cdbcc-105">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-105">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="cdbcc-106">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-106">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>

<span data-ttu-id="cdbcc-107">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-107">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="cdbcc-108">В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) пространство имен:</span><span class="sxs-lookup"><span data-stu-id="cdbcc-108">The following table lists the Caller Info attributes that are defined in the [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) namespace:</span></span>

|<span data-ttu-id="cdbcc-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cdbcc-109">Attribute</span></span>|<span data-ttu-id="cdbcc-110">Описание</span><span class="sxs-lookup"><span data-stu-id="cdbcc-110">Description</span></span>|<span data-ttu-id="cdbcc-111">Тип</span><span class="sxs-lookup"><span data-stu-id="cdbcc-111">Type</span></span>|
|---------|-----------|----|
|[<span data-ttu-id="cdbcc-112">CallerFilePath</span><span class="sxs-lookup"><span data-stu-id="cdbcc-112">CallerFilePath</span></span>](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|<span data-ttu-id="cdbcc-113">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-113">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="cdbcc-114">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-114">This is the file path at compile time.</span></span>|`String`
|[<span data-ttu-id="cdbcc-115">CallerLineNumber</span><span class="sxs-lookup"><span data-stu-id="cdbcc-115">CallerLineNumber</span></span>](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|<span data-ttu-id="cdbcc-116">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-116">Line number in the source file at which the method is called.</span></span>|`Integer`|
|[<span data-ttu-id="cdbcc-117">CallerMemberName</span><span class="sxs-lookup"><span data-stu-id="cdbcc-117">CallerMemberName</span></span>](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|<span data-ttu-id="cdbcc-118">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-118">Method or property name of the caller.</span></span> <span data-ttu-id="cdbcc-119">В разделе имена членов далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-119">See the Member Names section later in this topic.</span></span>|`String`|

## <a name="example"></a><span data-ttu-id="cdbcc-120">Пример</span><span class="sxs-lookup"><span data-stu-id="cdbcc-120">Example</span></span>

<span data-ttu-id="cdbcc-121">Следующий пример показывает, как эти атрибуты можно использовать для трассировки вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-121">The following example shows how you might use these attributes to trace a caller.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="cdbcc-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="cdbcc-122">Remarks</span></span>

<span data-ttu-id="cdbcc-123">Информационные атрибуты вызывающего может применяться только к необязательным параметрам.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-123">Caller Info attributes can only be applied to optional parameters.</span></span> <span data-ttu-id="cdbcc-124">Необходимо указать явное значение для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-124">You must supply an explicit value for each optional parameter.</span></span> <span data-ttu-id="cdbcc-125">Информационные атрибуты вызывающего объекта привести к записи правильное значение для каждого необязательного параметра, помеченной атрибутом информация вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-125">The Caller Info attributes cause the compiler to write the proper value for each optional parameter decorated with a Caller Info attribute.</span></span>

<span data-ttu-id="cdbcc-126">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-126">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="cdbcc-127">В отличие от результатов [StackTrace](/dotnet/api/system.diagnostics.stacktrace) свойство для исключений, результаты не затрагиваются запутыванием кода.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-127">Unlike the results of the [StackTrace](/dotnet/api/system.diagnostics.stacktrace) property for exceptions, the results aren't affected by obfuscation.</span></span>

<span data-ttu-id="cdbcc-128">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-128">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>

## <a name="member-names"></a><span data-ttu-id="cdbcc-129">Имена элементов</span><span class="sxs-lookup"><span data-stu-id="cdbcc-129">Member names</span></span>

<span data-ttu-id="cdbcc-130">Можно использовать [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, чтобы не указывать имя члена в виде `String` аргументов для вызываемого метода.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-130">You can use the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="cdbcc-131">При использовании этого метода позволяет избежать проблемы, не меняется, рефакторинга и переименования `String` значения.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-131">By using this technique, you avoid the problem that Rename Refactoring doesn't change the `String` values.</span></span> <span data-ttu-id="cdbcc-132">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="cdbcc-132">This benefit is especially useful for the following tasks:</span></span>

* <span data-ttu-id="cdbcc-133">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-133">Using tracing and diagnostic routines.</span></span>
* <span data-ttu-id="cdbcc-134">Реализация [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) интерфейс при привязке данных.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-134">Implementing the [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) interface when binding data.</span></span> <span data-ttu-id="cdbcc-135">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-135">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="cdbcc-136">Без [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-136">Without the [`CallerMemberName`](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) attribute, you must specify the property name as a literal.</span></span>

<span data-ttu-id="cdbcc-137">Следующая диаграмма показывает элемент имена, которые возвращаются при использовании атрибут CallerMemberName.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-137">The following chart shows the member names that are returned when you use the CallerMemberName attribute.</span></span>

|<span data-ttu-id="cdbcc-138">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="cdbcc-138">Calls occurs within</span></span>|<span data-ttu-id="cdbcc-139">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="cdbcc-139">Member name result</span></span>|
|-------------------|------------------|
|<span data-ttu-id="cdbcc-140">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="cdbcc-140">Method, property, or event</span></span>|<span data-ttu-id="cdbcc-141">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-141">The name of the method, property, or event from which the call originated.</span></span>|
|<span data-ttu-id="cdbcc-142">Конструктор</span><span class="sxs-lookup"><span data-stu-id="cdbcc-142">Constructor</span></span>|<span data-ttu-id="cdbcc-143">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="cdbcc-143">The string ".ctor"</span></span>|
|<span data-ttu-id="cdbcc-144">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="cdbcc-144">Static constructor</span></span>|<span data-ttu-id="cdbcc-145">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="cdbcc-145">The string ".cctor"</span></span>|
|<span data-ttu-id="cdbcc-146">Деструктор</span><span class="sxs-lookup"><span data-stu-id="cdbcc-146">Destructor</span></span>|<span data-ttu-id="cdbcc-147">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="cdbcc-147">The string "Finalize"</span></span>|
|<span data-ttu-id="cdbcc-148">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="cdbcc-148">User-defined operators or conversions</span></span>|<span data-ttu-id="cdbcc-149">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="cdbcc-149">The generated name for the member, for example, "op_Addition".</span></span>|
|<span data-ttu-id="cdbcc-150">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="cdbcc-150">Attribute constructor</span></span>|<span data-ttu-id="cdbcc-151">Имя члена, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-151">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="cdbcc-152">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-152">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|
|<span data-ttu-id="cdbcc-153">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="cdbcc-153">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="cdbcc-154">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdbcc-154">The default value of the optional parameter.</span></span>|

## <a name="see-also"></a><span data-ttu-id="cdbcc-155">См. также</span><span class="sxs-lookup"><span data-stu-id="cdbcc-155">See also</span></span>
 [<span data-ttu-id="cdbcc-156">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cdbcc-156">Attributes</span></span>](attributes.md)  
 [<span data-ttu-id="cdbcc-157">Именованные аргументы</span><span class="sxs-lookup"><span data-stu-id="cdbcc-157">Named arguments</span></span>](parameters-and-arguments.md#named-arguments)  
 [<span data-ttu-id="cdbcc-158">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="cdbcc-158">Optional parameters</span></span>](parameters-and-arguments.md#optional-parameters)  
