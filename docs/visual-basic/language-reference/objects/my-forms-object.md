---
title: Объект My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9fa5c77dd12c98100e3d17fc473a6802180d1e32
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965980"
---
# <a name="myforms-object"></a><span data-ttu-id="c7a8a-102">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="c7a8a-102">My.Forms Object</span></span>
<span data-ttu-id="c7a8a-103">Предоставляет свойства для доступа к экземпляру каждой формы Windows Form, объявленной в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7a8a-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7a8a-104">Remarks</span></span>  
 <span data-ttu-id="c7a8a-105">`My.Forms` Объект предоставляет экземпляр каждой формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="c7a8a-106">Имя свойства совпадает с именем формы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-106">The name of the property is the same as the name of the form that the property accesses.</span></span>   
  
 <span data-ttu-id="c7a8a-107">Доступ к формам, предоставляемым `My.Forms` объектом, можно получить с помощью имени формы без уточнения.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="c7a8a-108">Так как имя свойства совпадает с именем типа формы, это позволяет получить доступ к форме, как если бы она имела экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="c7a8a-109">Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>  
  
 <span data-ttu-id="c7a8a-110">`My.Forms` Объект предоставляет только формы, связанные с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="c7a8a-111">Он не предоставляет доступ к формам, объявленным в упоминаемых библиотеках DLL.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="c7a8a-112">Для доступа к форме, предоставляемой библиотекой DLL, необходимо использовать полное имя формы, записанное как *dllname*. *Формнаме*.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>  
  
 <span data-ttu-id="c7a8a-113"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> Свойство можно использовать для получения коллекции всех открытых форм приложения.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>  
  
 <span data-ttu-id="c7a8a-114">Объект и его свойства доступны только для приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-114">The object and its properties are available only for Windows applications.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c7a8a-115">Свойства</span><span class="sxs-lookup"><span data-stu-id="c7a8a-115">Properties</span></span>  
 <span data-ttu-id="c7a8a-116">Каждое свойство `My.Forms` объекта предоставляет доступ к экземпляру формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="c7a8a-117">Имя свойства совпадает с именем формы, к которой обращается свойство, а тип свойства совпадает с типом формы.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7a8a-118">При конфликте имен имя свойства для доступа к форме — *RootNamespace*_*Namespace*\_*формнаме*.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="c7a8a-119">Например, рассмотрим две формы с именем `Form1.`, если одна из этих форм находится в корневом `WindowsApplication1` пространстве имен и в `Namespace1`пространстве имен, поэтому доступ к этой `My.Forms.WindowsApplication1_Namespace1_Form1`форме осуществляется через.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>  
  
 <span data-ttu-id="c7a8a-120">`My.Forms` Объект предоставляет доступ к экземпляру главной формы приложения, созданному при запуске.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="c7a8a-121">Для всех других форм `My.Forms` объект создает новый экземпляр формы при обращении к нему и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="c7a8a-122">Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-122">Subsequent attempts to access that property return that instance of the form.</span></span>  
  
 <span data-ttu-id="c7a8a-123">Форму можно удалить, назначив `Nothing` свойству для этой формы.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="c7a8a-124">Средство задания свойств вызывает <xref:System.Windows.Forms.Form.Close%2A> метод формы, а затем `Nothing` присваивает хранимому значению.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="c7a8a-125">Если присвоить значение, отличное `Nothing` от свойства, метод задания <xref:System.ArgumentException> выдаст исключение.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="c7a8a-126">Можно проверить, сохраняет ли свойство `My.Forms` объекта экземпляр формы с `Is` помощью оператора или `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="c7a8a-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="c7a8a-127">С помощью этих операторов можно проверить, имеет `Nothing`ли свойство значение.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7a8a-128">Как правило, `Is` оператор `IsNot` или должен считывать значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="c7a8a-129">Однако если текущее свойство хранится `Nothing`, свойство создает новый экземпляр формы, а затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="c7a8a-130">Однако компилятор Visual Basic обрабатывает свойства `My.Forms` объекта по-разному и `Is` позволяет оператору или `IsNot` проверить состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a8a-131">Пример</span><span class="sxs-lookup"><span data-stu-id="c7a8a-131">Example</span></span>  
 <span data-ttu-id="c7a8a-132">В этом примере изменяется заголовок формы по умолчанию `SidebarMenu` .</span><span class="sxs-lookup"><span data-stu-id="c7a8a-132">This example changes the title of the default `SidebarMenu` form.</span></span>  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 <span data-ttu-id="c7a8a-133">Чтобы этот пример работал, проект должен иметь форму с именем `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>  
  
 <span data-ttu-id="c7a8a-134">Этот код будет работать только в проекте приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="c7a8a-134">This code will work only in a Windows Application project.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7a8a-135">Требования</span><span class="sxs-lookup"><span data-stu-id="c7a8a-135">Requirements</span></span>  
  
### <a name="availability-by-project-type"></a><span data-ttu-id="c7a8a-136">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="c7a8a-136">Availability by Project Type</span></span>  
  
|<span data-ttu-id="c7a8a-137">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="c7a8a-137">Project type</span></span>|<span data-ttu-id="c7a8a-138">Доступно</span><span class="sxs-lookup"><span data-stu-id="c7a8a-138">Available</span></span>|  
|---|---|  
|<span data-ttu-id="c7a8a-139">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="c7a8a-139">Windows Application</span></span>|<span data-ttu-id="c7a8a-140">**Да**</span><span class="sxs-lookup"><span data-stu-id="c7a8a-140">**Yes**</span></span>|  
|<span data-ttu-id="c7a8a-141">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="c7a8a-141">Class Library</span></span>|<span data-ttu-id="c7a8a-142">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-142">No</span></span>|  
|<span data-ttu-id="c7a8a-143">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="c7a8a-143">Console Application</span></span>|<span data-ttu-id="c7a8a-144">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-144">No</span></span>|  
|<span data-ttu-id="c7a8a-145">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="c7a8a-145">Windows Control Library</span></span>|<span data-ttu-id="c7a8a-146">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-146">No</span></span>|  
|<span data-ttu-id="c7a8a-147">Библиотека веб-элементов управления</span><span class="sxs-lookup"><span data-stu-id="c7a8a-147">Web Control Library</span></span>|<span data-ttu-id="c7a8a-148">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-148">No</span></span>|  
|<span data-ttu-id="c7a8a-149">Служба Windows</span><span class="sxs-lookup"><span data-stu-id="c7a8a-149">Windows Service</span></span>|<span data-ttu-id="c7a8a-150">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-150">No</span></span>|  
|<span data-ttu-id="c7a8a-151">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="c7a8a-151">Web Site</span></span>|<span data-ttu-id="c7a8a-152">Нет</span><span class="sxs-lookup"><span data-stu-id="c7a8a-152">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c7a8a-153">См. также</span><span class="sxs-lookup"><span data-stu-id="c7a8a-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="c7a8a-154">Объекты</span><span class="sxs-lookup"><span data-stu-id="c7a8a-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="c7a8a-155">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="c7a8a-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="c7a8a-156">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="c7a8a-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="c7a8a-157">Доступ к формам приложения</span><span class="sxs-lookup"><span data-stu-id="c7a8a-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
