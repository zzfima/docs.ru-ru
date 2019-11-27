---
title: Пошаговое руководство. Создание COM-объектов
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 5d00aff07358a0c40159fde9c12c70e0842d848b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74338622"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="9bc94-102">Пошаговое руководство. Создание объектов COM с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9bc94-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="9bc94-103">При создании новых приложений или компонентов лучше создавать сборки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9bc94-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="9bc94-104">Однако Visual Basic также упрощает предоставление .NET Framework компонента COM.</span><span class="sxs-lookup"><span data-stu-id="9bc94-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="9bc94-105">Это позволяет предоставлять новые компоненты для более ранних версий приложений, требующих COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="9bc94-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="9bc94-106">В этом пошаговом руководстве показано, как использовать Visual Basic для предоставления объектов .NET Framework в виде COM-объектов как с шаблоном COM-класса, так и без него.</span><span class="sxs-lookup"><span data-stu-id="9bc94-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="9bc94-107">Самый простой способ предоставить COM-объекты — использовать шаблон COM-класса.</span><span class="sxs-lookup"><span data-stu-id="9bc94-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="9bc94-108">Шаблон COM-класса создает новый класс, а затем настраивает проект для создания класса и уровня взаимодействия в виде COM-объекта и его регистрации в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="9bc94-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bc94-109">Хотя можно также предоставить класс, созданный в Visual Basic, как COM-объект для использования неуправляемым кодом, он не является настоящим COM-объектом и не может использоваться Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9bc94-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="9bc94-110">Дополнительные сведения см. [в разделе COM-взаимодействие в .NET Framework приложениях](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9bc94-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="9bc94-111">Создание COM-объекта с помощью шаблона класса COM</span><span class="sxs-lookup"><span data-stu-id="9bc94-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="9bc94-112">Откройте новый проект приложения Windows из меню **файл** , щелкнув **создать проект**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="9bc94-113">Убедитесь, что в диалоговом окне **Новый проект** в поле **типы проектов** выбрано значение Windows.</span><span class="sxs-lookup"><span data-stu-id="9bc94-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9bc94-114">В списке **шаблоны** выберите пункт **Библиотека классов** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9bc94-115">Отобразится новый проект.</span><span class="sxs-lookup"><span data-stu-id="9bc94-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="9bc94-116">В меню **проект** выберите команду **Добавить новый элемент** .</span><span class="sxs-lookup"><span data-stu-id="9bc94-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="9bc94-117">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="9bc94-118">Выберите **класс COM** в списке **шаблоны** и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="9bc94-119">Visual Basic добавляет новый класс и настраивает новый проект для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9bc94-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="9bc94-120">Добавьте в класс COM код, например свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="9bc94-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="9bc94-121">Выберите **Сборка ClassLibrary1** в меню **Сборка** .</span><span class="sxs-lookup"><span data-stu-id="9bc94-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="9bc94-122">Visual Basic создает сборку и регистрирует COM-объект в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="9bc94-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="9bc94-123">Создание COM-объектов без шаблона класса COM</span><span class="sxs-lookup"><span data-stu-id="9bc94-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="9bc94-124">Можно также создать COM-класс вручную вместо использования шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="9bc94-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="9bc94-125">Эта процедура полезна при работе из командной строки или в том случае, если требуется больший контроль над определением объектов COM.</span><span class="sxs-lookup"><span data-stu-id="9bc94-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="9bc94-126">Настройка проекта для создания COM-объекта</span><span class="sxs-lookup"><span data-stu-id="9bc94-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="9bc94-127">Откройте новый проект приложения Windows из меню **файл** , щелкнув **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="9bc94-128">Убедитесь, что в диалоговом окне **Новый проект** в поле **типы проектов** выбрано значение Windows.</span><span class="sxs-lookup"><span data-stu-id="9bc94-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9bc94-129">В списке **шаблоны** выберите пункт **Библиотека классов** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9bc94-130">Отобразится новый проект.</span><span class="sxs-lookup"><span data-stu-id="9bc94-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="9bc94-131">В **обозревателе решений** щелкните правой кнопкой мыши на проект и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="9bc94-132">Откроется **Конструктор проектов** .</span><span class="sxs-lookup"><span data-stu-id="9bc94-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="9bc94-133">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="9bc94-134">Установите флажок **Регистрация для COM-взаимодействия** .</span><span class="sxs-lookup"><span data-stu-id="9bc94-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="9bc94-135">Настройка кода в классе для создания COM-объекта</span><span class="sxs-lookup"><span data-stu-id="9bc94-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="9bc94-136">В **Обозреватель решений**дважды щелкните **Class1. vb** , чтобы отобразить его код.</span><span class="sxs-lookup"><span data-stu-id="9bc94-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="9bc94-137">Переименуйте класс на `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="9bc94-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="9bc94-138">Добавьте следующие константы в `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="9bc94-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="9bc94-139">Они будут хранить константы глобального уникального идентификатора (GUID), которые должны иметь объекты COM.</span><span class="sxs-lookup"><span data-stu-id="9bc94-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="9bc94-140">В меню **Сервис** выберите пункт **Создать GUID**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="9bc94-141">В диалоговом окне **Создание GUID** нажмите кнопку **Формат реестра**, а затем **Копировать**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="9bc94-142">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="9bc94-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="9bc94-143">Замените пустую строку `ClassId` идентификатором GUID, удаляя начальные и конечные фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="9bc94-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="9bc94-144">Например, если идентификатор GUID, предоставленный Guidgen, — `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` то код должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9bc94-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="9bc94-145">Повторите предыдущие шаги для констант `InterfaceId` и `EventsId`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9bc94-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="9bc94-146">Убедитесь, что идентификаторы GUID являются новыми и уникальными. в противном случае COM-компонент может конфликтовать с другими COM-компонентами.</span><span class="sxs-lookup"><span data-stu-id="9bc94-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="9bc94-147">Добавьте атрибут `ComClass` в `ComClass1`, указав идентификаторы GUID для идентификатора класса, идентификатора интерфейса и идентификатора события, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="9bc94-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="9bc94-148">Классы COM должны иметь `Public Sub New()` конструктор без параметров, иначе класс не будет зарегистрирован правильно.</span><span class="sxs-lookup"><span data-stu-id="9bc94-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="9bc94-149">Добавьте в класс конструктор без параметров:</span><span class="sxs-lookup"><span data-stu-id="9bc94-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="9bc94-150">Добавьте свойства, методы и события в класс, завершая его оператором `End Class`.</span><span class="sxs-lookup"><span data-stu-id="9bc94-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="9bc94-151">В меню **Сборка** выберите пункт **построить решение** .</span><span class="sxs-lookup"><span data-stu-id="9bc94-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="9bc94-152">Visual Basic создает сборку и регистрирует COM-объект в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="9bc94-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9bc94-153">Объекты COM, созданные с помощью Visual Basic, не могут использоваться другими приложениями Visual Basic, поскольку они не являются настоящими COM-объектами.</span><span class="sxs-lookup"><span data-stu-id="9bc94-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="9bc94-154">Попытка добавить ссылки на такие COM-объекты вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="9bc94-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="9bc94-155">Дополнительные сведения см. [в разделе COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="9bc94-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bc94-156">См. также</span><span class="sxs-lookup"><span data-stu-id="9bc94-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="9bc94-157">COM-взаимодействие</span><span class="sxs-lookup"><span data-stu-id="9bc94-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="9bc94-158">Пошаговое руководство. Реализация наследования с использованием COM-объектов</span><span class="sxs-lookup"><span data-stu-id="9bc94-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="9bc94-159">Директива #Region</span><span class="sxs-lookup"><span data-stu-id="9bc94-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="9bc94-160">COM-взаимодействие в приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9bc94-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="9bc94-161">Устранение неполадок взаимодействия</span><span class="sxs-lookup"><span data-stu-id="9bc94-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
