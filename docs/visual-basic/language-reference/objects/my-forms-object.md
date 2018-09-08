---
title: Объект My.Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: d15765b7673f321d4362ceea0adb73959a7e7726
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185945"
---
# <a name="myforms-object"></a><span data-ttu-id="236ef-102">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="236ef-102">My.Forms Object</span></span>
<span data-ttu-id="236ef-103">Предоставляет свойства для доступа к экземпляру каждой формы Windows, объявленные в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="236ef-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="236ef-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="236ef-104">Remarks</span></span>  
 <span data-ttu-id="236ef-105">`My.Forms` Объект предоставляет экземпляр каждой формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="236ef-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="236ef-106">Имя свойства совпадает с именем формы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="236ef-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="236ef-107">Можно воспользоваться формами, предоставляемые `My.Forms` объекта, используя имя в формате без уточнения.</span><span class="sxs-lookup"><span data-stu-id="236ef-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="236ef-108">Так как имя свойства совпадает с именем типа формы, это дает возможность доступа к форме, как если бы она имела экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="236ef-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="236ef-109">Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="236ef-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="236ef-110">`My.Forms` Объект предоставляет только формы, связанные с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="236ef-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="236ef-111">Она предоставляет доступ к формам, объявленным в указанные библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="236ef-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="236ef-112">Чтобы получить доступ к форме, библиотеки DLL, необходимо использовать полное имя формы, которое *DllName*. *FormName*.</span><span class="sxs-lookup"><span data-stu-id="236ef-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="236ef-113">Можно использовать <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> свойство, чтобы получить коллекцию всех открытых форм приложения.</span><span class="sxs-lookup"><span data-stu-id="236ef-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="236ef-114">Объект и его свойства доступны только для приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="236ef-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="236ef-115">Свойства</span><span class="sxs-lookup"><span data-stu-id="236ef-115">Properties</span></span>  
 <span data-ttu-id="236ef-116">Каждое свойство `My.Forms` объект предоставляет доступ к экземпляру формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="236ef-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="236ef-117">Имя свойства совпадает имя формы, который обращается к свойству, а тип свойства совпадает с типом формы.</span><span class="sxs-lookup"><span data-stu-id="236ef-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="236ef-118">Если имеется конфликт имен, имя свойства для доступа к форме является *RootNamespace*_*пространства имен*\_*FormName*.</span><span class="sxs-lookup"><span data-stu-id="236ef-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="236ef-119">Например, рассмотрим две формы с именем `Form1.`Если одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, доступ к этой форме через `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="236ef-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="236ef-120">`My.Forms` Объект предоставляет доступ к экземпляру главной формы приложения, который был создан во время запуска.</span><span class="sxs-lookup"><span data-stu-id="236ef-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="236ef-121">Для всех остальных форм `My.Forms` объекта создает новый экземпляр формы, когда она доступна и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="236ef-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="236ef-122">Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.</span><span class="sxs-lookup"><span data-stu-id="236ef-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="236ef-123">Можно уничтожить форму путем назначения `Nothing` свойства для этой формы.</span><span class="sxs-lookup"><span data-stu-id="236ef-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="236ef-124">Вызовы метода задания свойства <xref:System.Windows.Forms.Form.Close%2A> метод формы, а затем назначает `Nothing` к сохраненному значению.</span><span class="sxs-lookup"><span data-stu-id="236ef-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="236ef-125">Если назначить любое значение, отличное от `Nothing` свойству, метод задания значения создает исключение <xref:System.ArgumentException> исключение.</span><span class="sxs-lookup"><span data-stu-id="236ef-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="236ef-126">Вы можете протестировать свойство `My.Forms` объект сохраняет экземпляр формы с помощью `Is` или `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="236ef-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="236ef-127">Эти операторы можно использовать для проверки, является ли значение свойства `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="236ef-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="236ef-128">Как правило `Is` или `IsNot` оператор имеет считывается значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="236ef-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="236ef-129">Тем не менее если это свойство в настоящее время сохраняет `Nothing`, свойство создает новый экземпляр формы и затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="236ef-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="236ef-130">Тем не менее, компилятор Visual Basic обрабатывает свойства `My.Forms` объект по-разному и позволяет `Is` или `IsNot` оператор, чтобы проверить состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="236ef-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="236ef-131">Пример</span><span class="sxs-lookup"><span data-stu-id="236ef-131">Example</span></span>  
 <span data-ttu-id="236ef-132">В этом примере заголовок окна меняется на значение по умолчанию `SidebarMenu` формы.</span><span class="sxs-lookup"><span data-stu-id="236ef-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-forms-object_1.vb)]  
  
 <span data-ttu-id="236ef-133">Для работы этого примера проекта должен иметь форму с именем `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="236ef-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="236ef-134">Этот код будет работать только в проекте приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="236ef-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="236ef-135">Требования</span><span class="sxs-lookup"><span data-stu-id="236ef-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="236ef-136">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="236ef-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="236ef-137">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="236ef-137">Project type</span></span>|<span data-ttu-id="236ef-138">Доступно</span><span class="sxs-lookup"><span data-stu-id="236ef-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="236ef-139">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="236ef-139">Windows Application</span></span>|<span data-ttu-id="236ef-140">**Да**</span><span class="sxs-lookup"><span data-stu-id="236ef-140">**Yes**</span></span>|  
|<span data-ttu-id="236ef-141">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="236ef-141">Class Library</span></span>|<span data-ttu-id="236ef-142">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-142">No</span></span>|  
|<span data-ttu-id="236ef-143">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="236ef-143">Console Application</span></span>|<span data-ttu-id="236ef-144">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-144">No</span></span>|  
|<span data-ttu-id="236ef-145">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="236ef-145">Windows Control Library</span></span>|<span data-ttu-id="236ef-146">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-146">No</span></span>|  
|<span data-ttu-id="236ef-147">Web Control Library</span><span class="sxs-lookup"><span data-stu-id="236ef-147">Web Control Library</span></span>|<span data-ttu-id="236ef-148">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-148">No</span></span>|  
|<span data-ttu-id="236ef-149">Служба Windows</span><span class="sxs-lookup"><span data-stu-id="236ef-149">Windows Service</span></span>|<span data-ttu-id="236ef-150">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-150">No</span></span>|  
|<span data-ttu-id="236ef-151">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="236ef-151">Web Site</span></span>|<span data-ttu-id="236ef-152">Нет</span><span class="sxs-lookup"><span data-stu-id="236ef-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="236ef-153">См. также</span><span class="sxs-lookup"><span data-stu-id="236ef-153">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Form.Close%2A>  
 [<span data-ttu-id="236ef-154">Объекты</span><span class="sxs-lookup"><span data-stu-id="236ef-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)  
 [<span data-ttu-id="236ef-155">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="236ef-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="236ef-156">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="236ef-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="236ef-157">Доступ к формам приложения</span><span class="sxs-lookup"><span data-stu-id="236ef-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
