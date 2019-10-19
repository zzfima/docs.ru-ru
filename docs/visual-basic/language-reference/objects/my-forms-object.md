---
title: Объект My. Forms (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 9a0b3b9202972122aea4a7147d8d872486418264
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581868"
---
# <a name="myforms-object"></a><span data-ttu-id="bed8f-102">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="bed8f-102">My.Forms Object</span></span>

<span data-ttu-id="bed8f-103">Предоставляет свойства для доступа к экземпляру каждой формы Windows Form, объявленной в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="bed8f-103">Provides properties for accessing an instance of each Windows form declared in the current project.</span></span>

## <a name="remarks"></a><span data-ttu-id="bed8f-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="bed8f-104">Remarks</span></span>

<span data-ttu-id="bed8f-105">Объект `My.Forms` предоставляет экземпляр каждой формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="bed8f-105">The `My.Forms` object provides an instance of each form in the current project.</span></span> <span data-ttu-id="bed8f-106">Имя свойства совпадает с именем формы, к которой обращается свойство.</span><span class="sxs-lookup"><span data-stu-id="bed8f-106">The name of the property is the same as the name of the form that the property accesses.</span></span>

<span data-ttu-id="bed8f-107">Доступ к формам, предоставляемым объектом `My.Forms`, можно получить с помощью имени формы без уточнения.</span><span class="sxs-lookup"><span data-stu-id="bed8f-107">You can access the forms provided by the `My.Forms` object by using the name of the form, without qualification.</span></span> <span data-ttu-id="bed8f-108">Так как имя свойства совпадает с именем типа формы, это позволяет получить доступ к форме, как если бы она имела экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed8f-108">Because the property name is the same as the form's type name, this allows you to access a form as if it had a default instance.</span></span> <span data-ttu-id="bed8f-109">Например, предложение `My.Forms.Form1.Show` эквивалентно предложению `Form1.Show`.</span><span class="sxs-lookup"><span data-stu-id="bed8f-109">For example, `My.Forms.Form1.Show` is equivalent to `Form1.Show`.</span></span>

<span data-ttu-id="bed8f-110">Объект `My.Forms` предоставляет только формы, связанные с текущим проектом.</span><span class="sxs-lookup"><span data-stu-id="bed8f-110">The `My.Forms` object exposes only the forms associated with the current project.</span></span> <span data-ttu-id="bed8f-111">Он не предоставляет доступ к формам, объявленным в упоминаемых библиотеках DLL.</span><span class="sxs-lookup"><span data-stu-id="bed8f-111">It does not provide access to forms declared in referenced DLLs.</span></span> <span data-ttu-id="bed8f-112">Для доступа к форме, предоставляемой библиотекой DLL, необходимо использовать полное имя формы, записанное как *dllname*. *Формнаме*.</span><span class="sxs-lookup"><span data-stu-id="bed8f-112">To access a form that a DLL provides, you must use the qualified name of the form, written as *DllName*.*FormName*.</span></span>

<span data-ttu-id="bed8f-113">Чтобы получить коллекцию всех открытых форм приложения, можно использовать свойство <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>.</span><span class="sxs-lookup"><span data-stu-id="bed8f-113">You can use the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> property to get a collection of all the application's open forms.</span></span>

<span data-ttu-id="bed8f-114">Объект и его свойства доступны только для приложений Windows.</span><span class="sxs-lookup"><span data-stu-id="bed8f-114">The object and its properties are available only for Windows applications.</span></span>

## <a name="properties"></a><span data-ttu-id="bed8f-115">Свойства</span><span class="sxs-lookup"><span data-stu-id="bed8f-115">Properties</span></span>

<span data-ttu-id="bed8f-116">Каждое свойство объекта `My.Forms` предоставляет доступ к экземпляру формы в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="bed8f-116">Each property of the `My.Forms` object provides access to an instance of a form in the current project.</span></span> <span data-ttu-id="bed8f-117">Имя свойства совпадает с именем формы, к которой обращается свойство, а тип свойства совпадает с типом формы.</span><span class="sxs-lookup"><span data-stu-id="bed8f-117">The name of the property is the same as the name of the form that the property accesses, and the property type is the same as the form's type.</span></span>

> [!NOTE]
> <span data-ttu-id="bed8f-118">При конфликте имен имя свойства для доступа к форме — *RootNamespace*_*Namespace* \_*формнаме*.</span><span class="sxs-lookup"><span data-stu-id="bed8f-118">If there is a name collision, the property name to access a form is *RootNamespace*_*Namespace*\_*FormName*.</span></span> <span data-ttu-id="bed8f-119">Например, рассмотрим две формы с именем `Form1.`If одна из этих форм находится в корневом пространстве имен `WindowsApplication1` и в пространстве имен `Namespace1`, вы получите доступ к этой форме через `My.Forms.WindowsApplication1_Namespace1_Form1`.</span><span class="sxs-lookup"><span data-stu-id="bed8f-119">For example, consider two forms named `Form1.`If one of these forms is in the root namespace `WindowsApplication1` and in the namespace `Namespace1`, you would access that form through `My.Forms.WindowsApplication1_Namespace1_Form1`.</span></span>

<span data-ttu-id="bed8f-120">Объект `My.Forms` предоставляет доступ к экземпляру главной формы приложения, созданному при запуске.</span><span class="sxs-lookup"><span data-stu-id="bed8f-120">The `My.Forms` object provides access to the instance of the application's main form that was created on startup.</span></span> <span data-ttu-id="bed8f-121">Для всех других форм объект `My.Forms` создает новый экземпляр формы при доступе к нему и сохраняет его.</span><span class="sxs-lookup"><span data-stu-id="bed8f-121">For all other forms, the `My.Forms` object creates a new instance of the form when it is accessed and stores it.</span></span> <span data-ttu-id="bed8f-122">Последующие попытки доступа к этому свойству возвращают этот экземпляр формы.</span><span class="sxs-lookup"><span data-stu-id="bed8f-122">Subsequent attempts to access that property return that instance of the form.</span></span>

<span data-ttu-id="bed8f-123">Вы можете удалить форму, назначив `Nothing` свойству этой формы.</span><span class="sxs-lookup"><span data-stu-id="bed8f-123">You can dispose of a form by assigning `Nothing` to the property for that form.</span></span> <span data-ttu-id="bed8f-124">Средство задания свойств вызывает метод <xref:System.Windows.Forms.Form.Close%2A> формы, а затем присваивает `Nothing` сохраненному значению.</span><span class="sxs-lookup"><span data-stu-id="bed8f-124">The property setter calls the <xref:System.Windows.Forms.Form.Close%2A> method of the form, and then assigns `Nothing` to the stored value.</span></span> <span data-ttu-id="bed8f-125">Если присвоить свойству любое значение, отличное от `Nothing`, то метод задания выдаст исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="bed8f-125">If you assign any value other than `Nothing` to the property, the setter throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="bed8f-126">Можно проверить, сохраняет ли свойство объекта `My.Forms` экземпляр формы с помощью оператора `Is` или `IsNot`.</span><span class="sxs-lookup"><span data-stu-id="bed8f-126">You can test whether a property of the `My.Forms` object stores an instance of the form by using the `Is` or `IsNot` operator.</span></span> <span data-ttu-id="bed8f-127">С помощью этих операторов можно проверить, является ли значение свойства `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="bed8f-127">You can use those operators to check if the value of the property is `Nothing`.</span></span>

> [!NOTE]
> <span data-ttu-id="bed8f-128">Как правило, оператор `Is` или `IsNot` должен считывать значение свойства для выполнения сравнения.</span><span class="sxs-lookup"><span data-stu-id="bed8f-128">Typically, the `Is` or `IsNot` operator has to read the value of the property to perform the comparison.</span></span> <span data-ttu-id="bed8f-129">Однако если свойство в настоящее время хранит `Nothing`, свойство создает новый экземпляр формы, а затем возвращает этот экземпляр.</span><span class="sxs-lookup"><span data-stu-id="bed8f-129">However, if the property currently stores `Nothing`, the property creates a new instance of the form and then returns that instance.</span></span> <span data-ttu-id="bed8f-130">Однако компилятор Visual Basic обрабатывает свойства объекта `My.Forms` по-разному и позволяет оператору `Is` или `IsNot` проверять состояние свойства без изменения его значения.</span><span class="sxs-lookup"><span data-stu-id="bed8f-130">However, the Visual Basic compiler treats the properties of the `My.Forms` object differently and allows the `Is` or `IsNot` operator to check the status of the property without altering its value.</span></span>

## <a name="example"></a><span data-ttu-id="bed8f-131">Пример</span><span class="sxs-lookup"><span data-stu-id="bed8f-131">Example</span></span>

<span data-ttu-id="bed8f-132">В этом примере изменяется заголовок формы `SidebarMenu` по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bed8f-132">This example changes the title of the default `SidebarMenu` form.</span></span>

[!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]

<span data-ttu-id="bed8f-133">Чтобы этот пример работал, проект должен иметь форму с именем `SidebarMenu`.</span><span class="sxs-lookup"><span data-stu-id="bed8f-133">For this example to work, your project must have a form named `SidebarMenu`.</span></span>

<span data-ttu-id="bed8f-134">Этот код будет работать только в проекте приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="bed8f-134">This code will work only in a Windows Application project.</span></span>

## <a name="requirements"></a><span data-ttu-id="bed8f-135">Требования</span><span class="sxs-lookup"><span data-stu-id="bed8f-135">Requirements</span></span>

### <a name="availability-by-project-type"></a><span data-ttu-id="bed8f-136">Доступность по типу проекта</span><span class="sxs-lookup"><span data-stu-id="bed8f-136">Availability by Project Type</span></span>

|<span data-ttu-id="bed8f-137">Тип проекта</span><span class="sxs-lookup"><span data-stu-id="bed8f-137">Project type</span></span>|<span data-ttu-id="bed8f-138">Доступно</span><span class="sxs-lookup"><span data-stu-id="bed8f-138">Available</span></span>|
|---|---|
|<span data-ttu-id="bed8f-139">Приложение Windows</span><span class="sxs-lookup"><span data-stu-id="bed8f-139">Windows Application</span></span>|<span data-ttu-id="bed8f-140">**Да**</span><span class="sxs-lookup"><span data-stu-id="bed8f-140">**Yes**</span></span>|
|<span data-ttu-id="bed8f-141">Библиотека классов</span><span class="sxs-lookup"><span data-stu-id="bed8f-141">Class Library</span></span>|<span data-ttu-id="bed8f-142">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-142">No</span></span>|
|<span data-ttu-id="bed8f-143">Консольное приложение</span><span class="sxs-lookup"><span data-stu-id="bed8f-143">Console Application</span></span>|<span data-ttu-id="bed8f-144">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-144">No</span></span>|
|<span data-ttu-id="bed8f-145">Библиотека элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="bed8f-145">Windows Control Library</span></span>|<span data-ttu-id="bed8f-146">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-146">No</span></span>|
|<span data-ttu-id="bed8f-147">Библиотека веб-элементов управления</span><span class="sxs-lookup"><span data-stu-id="bed8f-147">Web Control Library</span></span>|<span data-ttu-id="bed8f-148">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-148">No</span></span>|
|<span data-ttu-id="bed8f-149">Служба Windows</span><span class="sxs-lookup"><span data-stu-id="bed8f-149">Windows Service</span></span>|<span data-ttu-id="bed8f-150">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-150">No</span></span>|
|<span data-ttu-id="bed8f-151">Веб-сайт</span><span class="sxs-lookup"><span data-stu-id="bed8f-151">Web Site</span></span>|<span data-ttu-id="bed8f-152">Нет</span><span class="sxs-lookup"><span data-stu-id="bed8f-152">No</span></span>|

## <a name="see-also"></a><span data-ttu-id="bed8f-153">См. также</span><span class="sxs-lookup"><span data-stu-id="bed8f-153">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [<span data-ttu-id="bed8f-154">Объекты</span><span class="sxs-lookup"><span data-stu-id="bed8f-154">Objects</span></span>](../../../visual-basic/language-reference/objects/index.md)
- [<span data-ttu-id="bed8f-155">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="bed8f-155">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="bed8f-156">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="bed8f-156">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="bed8f-157">Доступ к формам приложения</span><span class="sxs-lookup"><span data-stu-id="bed8f-157">Accessing Application Forms</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
