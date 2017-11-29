---
title: "Объект My.Forms"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords: My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a5aa7af1f07a29660335d968c1ecc17be5f8beec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="myforms-object"></a><span data-ttu-id="1cad2-102">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="1cad2-102">My.Forms Object</span></span>
<span data-ttu-id="1cad2-103">Предоставляет свойства для доступа к экземпляру каждой формы Windows Forms, объявленные в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1cad2-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cad2-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1cad2-104">Remarks</span></span>  
 <span data-ttu-id="1cad2-105">`My.Forms` Объект предоставляет экземпляр каждой формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1cad2-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="1cad2-106">Имя свойства совпадает с именем формы, которая обращается к свойству.</span><span class="sxs-lookup"><span data-stu-id="1cad2-106">The name of the property is the same as the name of the form that the property accesses.</span></span> <span data-ttu-id="1cad2-107">Сведения о добавлении формы в проект см. в разделе [как: добавить Windows Forms в проект](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="1cad2-107">For information about adding forms to a project, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="1cad2-108">Можно воспользоваться формами, предоставляемые `My.Forms` с использованием имени формы без уточнения.</span><span class="sxs-lookup"><span data-stu-id="1cad2-108">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="1cad2-109">Поскольку имя свойства совпадает с именем типа формы, это дает возможность доступа к форме, как если бы она имела экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1cad2-109">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="1cad2-110">Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="1cad2-110">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="1cad2-111">`My.Forms` Объект предоставляет только формы, связанные с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="1cad2-111">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="1cad2-112">Он не предоставляет доступ к формам, объявленным в DLL, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="1cad2-112">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="1cad2-113">Чтобы получить доступ к форме, библиотеки DLL, необходимо использовать полное имя формы, которое *DllName*. *Имя_формы*.</span><span class="sxs-lookup"><span data-stu-id="1cad2-113">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="1cad2-114">Можно использовать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> свойство для получения коллекции всех открытых форм приложения.</span><span class="sxs-lookup"><span data-stu-id="1cad2-114">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="1cad2-115">Объект и его свойства доступны только для приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="1cad2-115">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1cad2-116">Свойства</span><span class="sxs-lookup"><span data-stu-id="1cad2-116">Properties</span></span>  
 <span data-ttu-id="1cad2-117">Каждое свойство `My.Forms` объект предоставляет доступ к экземпляру формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="1cad2-117">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="1cad2-118">Имя свойства совпадает имя формы, который обращается к свойству, а тип свойства совпадает с типом формы.</span><span class="sxs-lookup"><span data-stu-id="1cad2-118">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cad2-119">Если имеется конфликт имен, имя свойства для доступа к форме является *RootNamespace*_*имен*\_*Имя_формы*.</span><span class="sxs-lookup"><span data-stu-id="1cad2-119">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="1cad2-120">Например, рассмотрим две формы с именем `Form1.`Если одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к форме с использованием `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="1cad2-120">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="1cad2-121">`My.Forms` Объект предоставляет доступ к экземпляру приложения главной формы, созданной при запуске.</span><span class="sxs-lookup"><span data-stu-id="1cad2-121">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="1cad2-122">Для всех других форм `My.Forms` объект создает новый экземпляр формы, если она доступна и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="1cad2-122">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="1cad2-123">Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.</span><span class="sxs-lookup"><span data-stu-id="1cad2-123">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="1cad2-124">Формы можно освободить путем назначения `Nothing` свойства для этой формы.</span><span class="sxs-lookup"><span data-stu-id="1cad2-124">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="1cad2-125">Вызовы метода задания свойства <xref:System.Windows.Forms.Form.Close%2A> метод формы, а затем назначает `Nothing` с сохраненным значением.</span><span class="sxs-lookup"><span data-stu-id="1cad2-125">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="1cad2-126">Если присвоить любое значение, отличное от `Nothing` к свойству, методу задания создает исключение <xref:System.ArgumentException> исключение.</span><span class="sxs-lookup"><span data-stu-id="1cad2-126">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="1cad2-127">Можно проверить, является ли свойство `My.Forms` объект сохраняет экземпляр формы с помощью `Is` или `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="1cad2-127">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="1cad2-128">Эти операторы можно использовать для проверки, если значение свойства `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1cad2-128">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cad2-129">Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="1cad2-129">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="1cad2-130">Тем не менее если в настоящее время хранит свойство `Nothing`, свойство создает новый экземпляр формы и затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1cad2-130">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="1cad2-131">Однако компилятор Visual Basic обрабатывает свойства `My.Forms` объект по-разному и позволяет `Is` или `IsNot` проверить состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="1cad2-131">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cad2-132">Пример</span><span class="sxs-lookup"><span data-stu-id="1cad2-132">Example</span></span>  
 <span data-ttu-id="1cad2-133">В этом примере изменяется заголовок по умолчанию `SidebarMenu` формы.</span><span class="sxs-lookup"><span data-stu-id="1cad2-133">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="1cad2-134">Для работы этого примера проект должен иметь форму с именем `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="1cad2-134">For this example to work, your project must have a form named `SidebarMenu`.</span></span> <span data-ttu-id="1cad2-135">Дополнительные сведения см. в разделе [как: добавить Windows Forms в проект](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span><span class="sxs-lookup"><span data-stu-id="1cad2-135">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
 <span data-ttu-id="1cad2-136">Этот код будет работать только в проекте приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="1cad2-136">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cad2-137">Требования</span><span class="sxs-lookup"><span data-stu-id="1cad2-137">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="1cad2-138">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="1cad2-138">Availability by Project Type</span></span>  
  
|<span data-ttu-id="1cad2-139">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="1cad2-139">Project type</span></span>|<span data-ttu-id="1cad2-140">Доступно</span><span class="sxs-lookup"><span data-stu-id="1cad2-140">Available</span></span>|  
|---|---|  
|<span data-ttu-id="1cad2-141">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="1cad2-141">Windows Application</span></span>|<span data-ttu-id="1cad2-142">**Да**</span><span class="sxs-lookup"><span data-stu-id="1cad2-142">**Yes**</span></span>|  
|<span data-ttu-id="1cad2-143">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="1cad2-143">Class Library</span></span>|<span data-ttu-id="1cad2-144">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-144">No</span></span>|  
|<span data-ttu-id="1cad2-145">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="1cad2-145">Console Application</span></span>|<span data-ttu-id="1cad2-146">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-146">No</span></span>|  
|<span data-ttu-id="1cad2-147">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="1cad2-147">Windows Control Library</span></span>|<span data-ttu-id="1cad2-148">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-148">No</span></span>|  
|<span data-ttu-id="1cad2-149">Библиотека веб-элементов управления</span><span class="sxs-lookup"><span data-stu-id="1cad2-149">Web Control Library</span></span>|<span data-ttu-id="1cad2-150">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-150">No</span></span>|  
|<span data-ttu-id="1cad2-151">Служба Windows</span><span class="sxs-lookup"><span data-stu-id="1cad2-151">Windows Service</span></span>|<span data-ttu-id="1cad2-152">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-152">No</span></span>|  
|<span data-ttu-id="1cad2-153">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="1cad2-153">Web Site</span></span>|<span data-ttu-id="1cad2-154">Нет</span><span class="sxs-lookup"><span data-stu-id="1cad2-154">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1cad2-155">См. также</span><span class="sxs-lookup"><span data-stu-id="1cad2-155">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="1cad2-156">Объекты</span><span class="sxs-lookup"><span data-stu-id="1cad2-156">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="1cad2-157">Способ: добавить в проект Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1cad2-157">How to: Add Windows Forms to a Project</span></span>](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1)  
 [<span data-ttu-id="1cad2-158">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="1cad2-158">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="1cad2-159">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="1cad2-159">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="1cad2-160">Доступ к формам приложения</span><span class="sxs-lookup"><span data-stu-id="1cad2-160">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
