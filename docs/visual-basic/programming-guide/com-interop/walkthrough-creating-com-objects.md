---
title: "Пошаговое руководство: Создание объектов COM с помощью Visual Basic | Документы Microsoft"
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
helpviewer_keywords:
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 859a8fc7440eecc0cadbfa8ea236dad7cae99247
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="17f80-102">Пошаговое руководство. Создание объектов COM с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17f80-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="17f80-103">При создании новых приложений или компонентов, лучше всего создать сборок платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17f80-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="17f80-104">Однако [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] также позволяет предоставить доступ к компоненту .NET Framework для COM.</span><span class="sxs-lookup"><span data-stu-id="17f80-104">However, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="17f80-105">Это позволяет создавать новые компоненты для более ранних наборы приложений, требующих COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="17f80-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="17f80-106">В этом пошаговом руководстве демонстрируется использование [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для предоставления [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] объектов в виде COM-объектов, как с и без шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="17f80-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to expose [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="17f80-107">Самый простой способ предоставлять COM-объекты — с помощью шаблона COM-класса.</span><span class="sxs-lookup"><span data-stu-id="17f80-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="17f80-108">Шаблон COM-класса создает новый класс и затем настраивает проект для создания класса и уровня управляемого взаимодействия как COM-объект и зарегистрировать его с операционной системой.</span><span class="sxs-lookup"><span data-stu-id="17f80-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17f80-109">Несмотря на то, что пользователь может предоставить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] как объект COM для использования в неуправляемом коде, не является объектом COM и не может использоваться с [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="17f80-109">Although you can also expose a class created in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="17f80-110">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="17f80-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="17f80-111">Чтобы создать объект COM при помощи шаблона класса COM</span><span class="sxs-lookup"><span data-stu-id="17f80-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="17f80-112">Откройте новый проект приложения Windows из **файл** меню **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="17f80-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="17f80-113">В **новый проект** диалогового окна **типы проектов** поля, проверьте, что выбран Windows.</span><span class="sxs-lookup"><span data-stu-id="17f80-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="17f80-114">Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="17f80-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="17f80-115">Откроется новый проект.</span><span class="sxs-lookup"><span data-stu-id="17f80-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="17f80-116">Выберите **Добавление нового элемента** из **проекта** меню.</span><span class="sxs-lookup"><span data-stu-id="17f80-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="17f80-117">**Add New Item** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="17f80-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="17f80-118">Выберите **COM-класса** из **шаблоны** , а затем нажмите **добавить**.</span><span class="sxs-lookup"><span data-stu-id="17f80-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="17f80-119">Добавляет новый класс и настроит новый проект для COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="17f80-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="17f80-120">Добавьте код, такие как свойства, методы и события в COM-класс.</span><span class="sxs-lookup"><span data-stu-id="17f80-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="17f80-121">Выберите **построить ClassLibrary1** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="17f80-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="17f80-122">Строит сборку и зарегистрирует объект COM в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="17f80-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="17f80-123">Создание объектов COM без шаблона COM-класса</span><span class="sxs-lookup"><span data-stu-id="17f80-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="17f80-124">Можно также создать класс COM вручную, не используя шаблон COM-класса.</span><span class="sxs-lookup"><span data-stu-id="17f80-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="17f80-125">Данная процедура будет полезна при работе в командной строке или если требуется больший контроль над определяются как COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="17f80-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="17f80-126">Чтобы настроить проект для создания объекта COM</span><span class="sxs-lookup"><span data-stu-id="17f80-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="17f80-127">Откройте новый проект приложения Windows из **файл** меню **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="17f80-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="17f80-128">В **новый проект** диалогового окна **типы проектов** поля, проверьте, что выбран Windows.</span><span class="sxs-lookup"><span data-stu-id="17f80-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="17f80-129">Выберите **библиотеки классов** из **шаблоны** , а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="17f80-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="17f80-130">Откроется новый проект.</span><span class="sxs-lookup"><span data-stu-id="17f80-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="17f80-131">В **обозревателе решений**щелкните правой кнопкой мыши проект затем **свойства**.</span><span class="sxs-lookup"><span data-stu-id="17f80-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="17f80-132">**Конструктора проектов** отображается.</span><span class="sxs-lookup"><span data-stu-id="17f80-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="17f80-133">Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="17f80-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="17f80-134">Выберите **Register for COM Interop** флажок.</span><span class="sxs-lookup"><span data-stu-id="17f80-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="17f80-135">Настройка кода в классе для создания объекта COM</span><span class="sxs-lookup"><span data-stu-id="17f80-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="17f80-136">В **обозревателе решений**, дважды щелкните **Class1.vb** для просмотра его кода.</span><span class="sxs-lookup"><span data-stu-id="17f80-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="17f80-137">Переименуйте класс на `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="17f80-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="17f80-138">Добавьте следующие константы в `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="17f80-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="17f80-139">Они будут хранить константы глобальный уникальный идентификатор (GUID), COM-объекты должны иметь.</span><span class="sxs-lookup"><span data-stu-id="17f80-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     <span data-ttu-id="17f80-140">[!code-vb[VbVbalrInterop&#2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="17f80-140">[!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span></span>  
  
4.  <span data-ttu-id="17f80-141">На **средства** меню, щелкните **создать Guid**.</span><span class="sxs-lookup"><span data-stu-id="17f80-141">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="17f80-142">В **создать GUID** диалоговом нажмите кнопку **формат реестра** и нажмите кнопку **копирования**.</span><span class="sxs-lookup"><span data-stu-id="17f80-142">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="17f80-143">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="17f80-143">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="17f80-144">Замените пустую строку для `ClassId` на GUID, удалите начальные и конечные фигурные скобки.</span><span class="sxs-lookup"><span data-stu-id="17f80-144">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="17f80-145">Например, если идентификатор GUID, предоставляемый Guidgen является `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , а затем код должен выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="17f80-145">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     <span data-ttu-id="17f80-146">[!code-vb[VbVbalrInterop&#3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="17f80-146">[!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span></span>  
  
6.  <span data-ttu-id="17f80-147">Повторите предыдущие шаги для `InterfaceId` и `EventsId` константы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="17f80-147">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     <span data-ttu-id="17f80-148">[!code-vb[VbVbalrInterop&#4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="17f80-148">[!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17f80-149">Убедитесь, что GUID являются новыми и уникальными; в противном случае — COM-компонент может конфликтовать с другими COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="17f80-149">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="17f80-150">Добавить `ComClass` атрибут `ComClass1`, указание идентификаторы GUID для идентификатора класса, идентификатор интерфейса и идентификатор события, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="17f80-150">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     <span data-ttu-id="17f80-151">[!code-vb[VbVbalrInterop&#5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="17f80-151">[!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span></span>  
  
8.  <span data-ttu-id="17f80-152">Классы COM должны иметь конструктор без параметров `Public Sub New()` конструктору, или класс не будет регистрироваться правильно.</span><span class="sxs-lookup"><span data-stu-id="17f80-152">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="17f80-153">Добавьте конструктор для класса:</span><span class="sxs-lookup"><span data-stu-id="17f80-153">Add a parameterless constructor to the class:</span></span>  
  
     <span data-ttu-id="17f80-154">[!code-vb[VbVbalrInterop №&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="17f80-154">[!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span></span>  
  
9. <span data-ttu-id="17f80-155">Добавьте в класс, в конце свойства, методы и события `End Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="17f80-155">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="17f80-156">Выберите **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="17f80-156">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="17f80-157">Строит сборку и зарегистрирует объект COM в операционной системе.</span><span class="sxs-lookup"><span data-stu-id="17f80-157"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17f80-158">COM-объекты, которые создают с [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не может использоваться другими [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приложений, так как они не являются настоящими COM-объектами.</span><span class="sxs-lookup"><span data-stu-id="17f80-158">The COM objects you generate with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot be used by other [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="17f80-159">Попытка добавить ссылку на такие объекты COM вызовет ошибку.</span><span class="sxs-lookup"><span data-stu-id="17f80-159">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="17f80-160">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="17f80-160">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f80-161">См. также</span><span class="sxs-lookup"><span data-stu-id="17f80-161">See Also</span></span>  
 <span data-ttu-id="17f80-162"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="17f80-162"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>   
<span data-ttu-id="17f80-163"> [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="17f80-163"> [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="17f80-164"> [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="17f80-164"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="17f80-165"> [Директива #Region](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="17f80-165"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="17f80-166"> [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="17f80-166"> [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="17f80-167"> [Устранение неполадок взаимодействия](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="17f80-167"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span></span>
