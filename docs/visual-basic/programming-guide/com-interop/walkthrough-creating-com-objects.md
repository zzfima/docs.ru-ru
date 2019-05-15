---
title: Пошаговое руководство. Создание объектов COM с помощью Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 465f1d8141f51de179dbb4e963a8fcac8c09fa33
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592694"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="75941-102">Пошаговое руководство. Создание объектов COM с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75941-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="75941-103">При создании новых приложений или компонентов, лучше всего создать сборок платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75941-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="75941-104">Тем не менее Visual Basic также позволяет легко предоставить доступ к компоненту .NET Framework для модели COM.</span><span class="sxs-lookup"><span data-stu-id="75941-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="75941-105">Это позволяет создавать новые компоненты для более ранних пакетов приложений, требующих COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="75941-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="75941-106">В этом пошаговом руководстве демонстрируется использование Visual Basic для предоставления объектов .NET Framework в виде COM-объектов, как с и без шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="75941-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="75941-107">Самый простой способ предоставлять COM-объекты — с помощью шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="75941-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="75941-108">Шаблон класса COM создает новый класс и затем настраивает проект для создания на уровне класса и взаимодействие как объект COM и зарегистрируйте его с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="75941-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="75941-109">Несмотря на то, что можно также предоставлять класс, созданный в Visual Basic как объект COM для неуправляемого кода для использования, он не является истинным COM-объектом и не может использоваться с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="75941-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="75941-110">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="75941-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="75941-111">Чтобы создать объект COM с помощью шаблона класса COM</span><span class="sxs-lookup"><span data-stu-id="75941-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="75941-112">Откройте новый проект приложения Windows из **файл** меню, щелкнув **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="75941-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="75941-113">В **новый проект** диалогового окна **типы проектов** , убедитесь, что выбран Windows.</span><span class="sxs-lookup"><span data-stu-id="75941-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="75941-114">Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="75941-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="75941-115">Откроется новый проект.</span><span class="sxs-lookup"><span data-stu-id="75941-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="75941-116">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="75941-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="75941-117">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="75941-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="75941-118">Выберите **COM-класса** из **шаблоны** , а затем нажмите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="75941-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="75941-119">Добавляет новый класс Visual Basic и настраивает новый проект для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="75941-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="75941-120">Добавьте код, такие как свойства, методы и события в COM-класс.</span><span class="sxs-lookup"><span data-stu-id="75941-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="75941-121">Выберите **построения ClassLibrary1** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="75941-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="75941-122">Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="75941-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="75941-123">Создание объектов COM без шаблона COM-класса</span><span class="sxs-lookup"><span data-stu-id="75941-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="75941-124">Также можно создать класс COM вручную, вместо использования шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="75941-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="75941-125">Данная процедура будет полезна при работе из командной строки, или если требуется больший контроль над определение COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="75941-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="75941-126">Чтобы настроить проект для создания COM-объекта</span><span class="sxs-lookup"><span data-stu-id="75941-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="75941-127">Откройте новый проект приложения Windows из **файл** меню, щелкнув **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="75941-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="75941-128">В **новый проект** диалогового окна **типы проектов** , убедитесь, что выбран Windows.</span><span class="sxs-lookup"><span data-stu-id="75941-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="75941-129">Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="75941-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="75941-130">Откроется новый проект.</span><span class="sxs-lookup"><span data-stu-id="75941-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="75941-131">В **обозревателе решений** щелкните правой кнопкой мыши на проект и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="75941-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="75941-132">**Конструктор проектов** отображается.</span><span class="sxs-lookup"><span data-stu-id="75941-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="75941-133">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="75941-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="75941-134">Выберите **регистрация для COM-взаимодействия** "флажок".</span><span class="sxs-lookup"><span data-stu-id="75941-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="75941-135">Чтобы настроить код в классе для создания COM-объекта</span><span class="sxs-lookup"><span data-stu-id="75941-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="75941-136">В **обозревателе решений**, дважды щелкните **Class1.vb** для отображения ее кода.</span><span class="sxs-lookup"><span data-stu-id="75941-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="75941-137">Переименуйте класс на `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="75941-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="75941-138">Добавьте следующие константы для `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="75941-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="75941-139">Они будут храниться константы глобальный уникальный идентификатор (GUID), которые должны иметь COM-объекты.</span><span class="sxs-lookup"><span data-stu-id="75941-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="75941-140">В меню **Сервис** выберите пункт **Создать GUID**.</span><span class="sxs-lookup"><span data-stu-id="75941-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="75941-141">В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="75941-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="75941-142">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="75941-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="75941-143">Замените пустую строку для `ClassId` с идентификатором GUID, удалите начальные и конечные фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="75941-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="75941-144">Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` то ваш код должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="75941-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="75941-145">Повторите предыдущие шаги для `InterfaceId` и `EventsId` константы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="75941-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  <span data-ttu-id="75941-146">Убедитесь, что значения GUID имеют новыми и уникальными; в противном случае компонент COM могут конфликтовать с другими компонентами COM.</span><span class="sxs-lookup"><span data-stu-id="75941-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="75941-147">Добавить `ComClass` атрибут `ComClass1`, указав идентификаторы GUID для идентификатора класса, идентификатор интерфейса и идентификатор события, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="75941-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="75941-148">Классы COM должны иметь конструктор без параметров `Public Sub New()` конструктор или класс не будет зарегистрирован правильно.</span><span class="sxs-lookup"><span data-stu-id="75941-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="75941-149">Добавьте конструктор в класс:</span><span class="sxs-lookup"><span data-stu-id="75941-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="75941-150">Добавьте свойства, методы и события к классу, в конце `End Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="75941-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="75941-151">Выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="75941-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="75941-152">Visual Basic создает сборку и регистрирует COM-объекта с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="75941-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="75941-153">COM-объекты, созданные с помощью Visual Basic не может использоваться другими приложениями Visual Basic, поскольку они не являются настоящими COM-объектами.</span><span class="sxs-lookup"><span data-stu-id="75941-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="75941-154">Попытка добавить ссылку на такие объекты COM, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="75941-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="75941-155">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="75941-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75941-156">См. также</span><span class="sxs-lookup"><span data-stu-id="75941-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="75941-157">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="75941-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="75941-158">Пошаговое руководство: Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="75941-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="75941-159">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="75941-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="75941-160">COM-взаимодействие в приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="75941-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="75941-161">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="75941-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
