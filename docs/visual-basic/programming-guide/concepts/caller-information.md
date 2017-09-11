---
title: "Сведения о вызывающем (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d9a028474a3bb7ae020f466d4dfe51608c43ab07
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="caller-information-visual-basic"></a><span data-ttu-id="37761-102">Сведения о вызывающем (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37761-102">Caller Information (Visual Basic)</span></span>
<span data-ttu-id="37761-103">С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода.</span><span class="sxs-lookup"><span data-stu-id="37761-103">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="37761-104">Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="37761-104">You can obtain file path of the source code, the line number in the source code, and the member name of the caller.</span></span> <span data-ttu-id="37761-105">Эти сведения полезны для трассировки, отладки и создания средств диагностики.</span><span class="sxs-lookup"><span data-stu-id="37761-105">This information is helpful for tracing, debugging, and creating diagnostic tools.</span></span>  
  
 <span data-ttu-id="37761-106">Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37761-106">To obtain this information, you use attributes that are applied to optional parameters, each of which has a default value.</span></span> <span data-ttu-id="37761-107">В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в <xref:System.Runtime.CompilerServices?displayProperty=fullName>пространство имен:</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="37761-107">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="37761-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="37761-108">Attribute</span></span>|<span data-ttu-id="37761-109">Описание</span><span class="sxs-lookup"><span data-stu-id="37761-109">Description</span></span>|<span data-ttu-id="37761-110">Тип</span><span class="sxs-lookup"><span data-stu-id="37761-110">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="37761-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="37761-111"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="37761-112">Полный путь исходного файла, содержащего вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="37761-112">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="37761-113">Это путь к файлу во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="37761-113">This is the file path at compile time.</span></span>|`String`|  
|<span data-ttu-id="37761-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="37761-114"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="37761-115">Номер строки в исходном файле, в которой вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="37761-115">Line number in the source file at which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="37761-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="37761-116"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="37761-117">Имя свойства или метода вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="37761-117">Method or property name of the caller.</span></span> <span data-ttu-id="37761-118">В разделе [имена членов](#MEMBERNAMES) далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="37761-118">See [Member Names](#MEMBERNAMES) later in this topic.</span></span>|`String`|  
  
## <a name="example"></a><span data-ttu-id="37761-119">Пример</span><span class="sxs-lookup"><span data-stu-id="37761-119">Example</span></span>  
 <span data-ttu-id="37761-120">В следующем примере показано, как использовать информационные атрибуты вызывающего объекта.</span><span class="sxs-lookup"><span data-stu-id="37761-120">The following example shows how to use Caller Info attributes.</span></span> <span data-ttu-id="37761-121">При каждом вызове метода `TraceMessage` сведения о вызывающем объекте подставляются в качестве аргументов необязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="37761-121">On each call to the `TraceMessage` method, the caller information is substituted as arguments to the optional parameters.</span></span>  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a><span data-ttu-id="37761-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="37761-122">Remarks</span></span>  
 <span data-ttu-id="37761-123">Для каждого необязательного параметра необходимо указать явное значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37761-123">You must specify an explicit default value for each optional parameter.</span></span> <span data-ttu-id="37761-124">Нельзя применять информационные атрибуты вызывающего объекта к параметрам, которые не были указаны как необязательные.</span><span class="sxs-lookup"><span data-stu-id="37761-124">You can't apply Caller Info attributes to parameters that aren't specified as optional.</span></span>  
  
 <span data-ttu-id="37761-125">Информационные атрибуты вызывающего объекта не делают параметр необязательным.</span><span class="sxs-lookup"><span data-stu-id="37761-125">The Caller Info attributes don't make a parameter optional.</span></span> <span data-ttu-id="37761-126">Вместо этого они влияют на значение по умолчанию, которое передается, если аргумент был опущен.</span><span class="sxs-lookup"><span data-stu-id="37761-126">Instead, they affect the default value that's passed in when the argument is omitted.</span></span>  
  
 <span data-ttu-id="37761-127">Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="37761-127">Caller Info values are emitted as literals into the Intermediate Language (IL) at compile time.</span></span> <span data-ttu-id="37761-128">В отличие от результатов <xref:System.Exception.StackTrace%2A>свойство для исключений, результаты не затрагиваются запутывания.</xref:System.Exception.StackTrace%2A></span><span class="sxs-lookup"><span data-stu-id="37761-128">Unlike the results of the <xref:System.Exception.StackTrace%2A> property for exceptions, the results aren't affected by obfuscation.</span></span>  
  
 <span data-ttu-id="37761-129">Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="37761-129">You can explicitly supply the optional arguments to control the caller information or to hide caller information.</span></span>  
  
###  <span data-ttu-id="37761-130"><a name="MEMBERNAMES"></a>Имена членов</span><span class="sxs-lookup"><span data-stu-id="37761-130"><a name="MEMBERNAMES"></a> Member Names</span></span>  
 <span data-ttu-id="37761-131">Можно использовать атрибут `CallerMemberName`, чтобы не указывать имя члена в виде аргумента `String` вызываемому методу.</span><span class="sxs-lookup"><span data-stu-id="37761-131">You can use the `CallerMemberName` attribute to avoid specifying the member name as a `String` argument to the called method.</span></span> <span data-ttu-id="37761-132">С помощью этого метода позволяет избежать проблемы, **рефакторинга и переименования** не изменяет `String` значения.</span><span class="sxs-lookup"><span data-stu-id="37761-132">By using this technique, you avoid the problem that **Rename Refactoring** doesn't change the `String` values.</span></span> <span data-ttu-id="37761-133">Это особенно полезно при выполнении следующих задач:</span><span class="sxs-lookup"><span data-stu-id="37761-133">This benefit is especially useful for the following tasks:</span></span>  
  
-   <span data-ttu-id="37761-134">Использование процедур трассировки и диагностики.</span><span class="sxs-lookup"><span data-stu-id="37761-134">Using tracing and diagnostic routines.</span></span>  
  
-   <span data-ttu-id="37761-135">Реализация <xref:System.ComponentModel.INotifyPropertyChanged>интерфейса при привязке данных.</xref:System.ComponentModel.INotifyPropertyChanged></span><span class="sxs-lookup"><span data-stu-id="37761-135">Implementing the <xref:System.ComponentModel.INotifyPropertyChanged> interface when binding data.</span></span> <span data-ttu-id="37761-136">Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения.</span><span class="sxs-lookup"><span data-stu-id="37761-136">This interface allows the property of an object to notify a bound control that the property has changed, so that the control can display the updated information.</span></span> <span data-ttu-id="37761-137">Если атрибут `CallerMemberName` не используется, необходимо указать имя свойства как литерал.</span><span class="sxs-lookup"><span data-stu-id="37761-137">Without the `CallerMemberName` attribute, you must specify the property name as a literal.</span></span>  
  
 <span data-ttu-id="37761-138">В следующей таблице представлены имена членов, возвращаемых при использовании атрибута `CallerMemberName`.</span><span class="sxs-lookup"><span data-stu-id="37761-138">The following chart shows the member names that are returned when you use the `CallerMemberName` attribute.</span></span>  
  
|<span data-ttu-id="37761-139">Фрагмент кода, в пределах которого происходит вызов</span><span class="sxs-lookup"><span data-stu-id="37761-139">Calls occurs within</span></span>|<span data-ttu-id="37761-140">Результат имени члена</span><span class="sxs-lookup"><span data-stu-id="37761-140">Member name result</span></span>|  
|-------------------------|------------------------|  
|<span data-ttu-id="37761-141">Метод, свойство или событие</span><span class="sxs-lookup"><span data-stu-id="37761-141">Method, property, or event</span></span>|<span data-ttu-id="37761-142">Имя метода, свойства или события, из которого происходил вызов.</span><span class="sxs-lookup"><span data-stu-id="37761-142">The name of the method, property, or event from which the call originated.</span></span>|  
|<span data-ttu-id="37761-143">Конструктор</span><span class="sxs-lookup"><span data-stu-id="37761-143">Constructor</span></span>|<span data-ttu-id="37761-144">Строка ".ctor"</span><span class="sxs-lookup"><span data-stu-id="37761-144">The string ".ctor"</span></span>|  
|<span data-ttu-id="37761-145">Статический конструктор</span><span class="sxs-lookup"><span data-stu-id="37761-145">Static constructor</span></span>|<span data-ttu-id="37761-146">Строка ".cctor"</span><span class="sxs-lookup"><span data-stu-id="37761-146">The string ".cctor"</span></span>|  
|<span data-ttu-id="37761-147">Деструктор</span><span class="sxs-lookup"><span data-stu-id="37761-147">Destructor</span></span>|<span data-ttu-id="37761-148">Строка "Finalize"</span><span class="sxs-lookup"><span data-stu-id="37761-148">The string "Finalize"</span></span>|  
|<span data-ttu-id="37761-149">Определяемые пользователем операторы и преобразования</span><span class="sxs-lookup"><span data-stu-id="37761-149">User-defined operators or conversions</span></span>|<span data-ttu-id="37761-150">Созданное имя члена, например, "op_Addition".</span><span class="sxs-lookup"><span data-stu-id="37761-150">The generated name for the member, for example, "op_Addition".</span></span>|  
|<span data-ttu-id="37761-151">Конструктора атрибута</span><span class="sxs-lookup"><span data-stu-id="37761-151">Attribute constructor</span></span>|<span data-ttu-id="37761-152">Имя члена, к которому применяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="37761-152">The name of the member to which the attribute is applied.</span></span> <span data-ttu-id="37761-153">Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.</span><span class="sxs-lookup"><span data-stu-id="37761-153">If the attribute is any element within a member (such as a parameter, a return value, or a generic type parameter), this result is the name of the member that's associated with that element.</span></span>|  
|<span data-ttu-id="37761-154">Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)</span><span class="sxs-lookup"><span data-stu-id="37761-154">No containing member (for example, assembly-level or attributes that are applied to types)</span></span>|<span data-ttu-id="37761-155">Значение необязательного параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37761-155">The default value of the optional parameter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37761-156">См. также</span><span class="sxs-lookup"><span data-stu-id="37761-156">See Also</span></span>  
 <span data-ttu-id="37761-157">[Атрибуты (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="37761-157">[Attributes (Visual Basic)](../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="37761-158"> [Общие атрибуты (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="37761-158"> [Common Attributes (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md) </span></span>  
<span data-ttu-id="37761-159"> [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="37761-159"> [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md) </span></span>  
<span data-ttu-id="37761-160"> [Основные понятия программирования (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="37761-160"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)</span></span>
