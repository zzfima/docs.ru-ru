---
title: "Создание элементов управления Windows Forms во время разработки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9910aa1849ed9288eca7003408c0afc39c641dbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="developing-windows-forms-controls-at-design-time"></a><span data-ttu-id="4ed7b-102">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="4ed7b-102">Developing Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="4ed7b-103">Среда .NET Framework предоставляет широкий набор технологий создания элементов управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="4ed7b-104">Авторы больше не ограничены созданием составных элементов управления, которые действуют как коллекция стандартных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="4ed7b-105">Через наследование можно создать свои собственные элементы управления на основе существующих составных элементов управления или существующих элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="4ed7b-106">Можно также создать собственные элементы управления, реализующие настраиваемое рисование.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="4ed7b-107">Эти возможности обеспечивают высокую степень гибкости разработки и функциональности визуального интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="4ed7b-108">Чтобы воспользоваться преимуществами этих функций, вы должны быть знакомы с понятиями объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ed7b-109">Это не обязательно иметь глубокие знания о наследовании, но могут оказаться полезными для обращения к [Основы наследования (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="4ed7b-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>  
  
 <span data-ttu-id="4ed7b-110">Если вам необходимо создать пользовательский элемент управления для использования в веб-формах, см. раздел [Разработка пользовательских серверных элементов управления ASP.NET](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span><span class="sxs-lookup"><span data-stu-id="4ed7b-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ed7b-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4ed7b-111">In This Section</span></span>  
 [<span data-ttu-id="4ed7b-112">Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ed7b-112">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 <span data-ttu-id="4ed7b-113">Демонстрируется создание простого составного элемента управления в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-113">Shows how to create a simple composite control in Visual Basic.</span></span>  
  
 [<span data-ttu-id="4ed7b-114">Пример. Создание составного элемента управления с помощью C#</span><span class="sxs-lookup"><span data-stu-id="4ed7b-114">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 <span data-ttu-id="4ed7b-115">Демонстрируется создание простого составного элемента управления в C#.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-115">Shows how to create a simple composite control in C#.</span></span>  
  
 [<span data-ttu-id="4ed7b-116">Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4ed7b-116">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 <span data-ttu-id="4ed7b-117">Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-117">Shows how to create a simple Windows Forms control using inheritance in Visual Basic.</span></span>  
  
 [<span data-ttu-id="4ed7b-118">Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#</span><span class="sxs-lookup"><span data-stu-id="4ed7b-118">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 <span data-ttu-id="4ed7b-119">Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в C#.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-119">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>  
  
 [<span data-ttu-id="4ed7b-120">Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ed7b-120">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 <span data-ttu-id="4ed7b-121">Демонстрируется использование функции смарт-тегов в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-121">Shows how to use the smart tag feature on Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="4ed7b-122">Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="4ed7b-122">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 <span data-ttu-id="4ed7b-123">Показано, как использовать <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> атрибут для сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-123">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>  
  
 [<span data-ttu-id="4ed7b-124">Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="4ed7b-124">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 <span data-ttu-id="4ed7b-125">Демонстрируется процедура отладки поведения элемента управления Windows Forms во время разработки.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-125">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="4ed7b-126">Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки</span><span class="sxs-lookup"><span data-stu-id="4ed7b-126">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 <span data-ttu-id="4ed7b-127">Демонстрируется интеграция составного элемента управления в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-127">Shows how to tightly integrate a composite control into the design environment.</span></span>  
  
 [<span data-ttu-id="4ed7b-128">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ed7b-128">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 <span data-ttu-id="4ed7b-129">Общие рекомендации по реализации элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-129">Provides an overview of considerations for implementing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="4ed7b-130">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="4ed7b-130">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 <span data-ttu-id="4ed7b-131">Демонстрируется создание элемента управления путем наследования из составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-131">Shows how to create a control by inheriting from a composite control.</span></span>  
  
 [<span data-ttu-id="4ed7b-132">Практическое руководство. Наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="4ed7b-132">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 <span data-ttu-id="4ed7b-133">Обзор процедуры создания составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-133">Provides an overview of the procedure for creating a composite control.</span></span>  
  
 [<span data-ttu-id="4ed7b-134">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ed7b-134">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 <span data-ttu-id="4ed7b-135">Описание способов создания расширенного элемента управления путем наследования от <xref:System.Windows.Forms.Button> класса элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-135">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>  
  
 [<span data-ttu-id="4ed7b-136">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="4ed7b-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 <span data-ttu-id="4ed7b-137">Обзор создания расширенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-137">Provides an overview of creating an extended control.</span></span>  
  
 [<span data-ttu-id="4ed7b-138">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="4ed7b-138">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 <span data-ttu-id="4ed7b-139">Показано, как использовать <xref:System.Windows.Forms.Control.Dock%2A> свойства для выравнивания пользовательского элемента управления по краю занимаемой им формы.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-139">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="4ed7b-140">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="4ed7b-140">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 <span data-ttu-id="4ed7b-141">Описание процедуры установки элемента управления таким образом, чтобы он отображался в диалоговом окне **Настройка области элементов**.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-141">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>  
  
 [<span data-ttu-id="4ed7b-142">Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления</span><span class="sxs-lookup"><span data-stu-id="4ed7b-142">How to: Provide a Toolbox Bitmap for a Control</span></span>](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 <span data-ttu-id="4ed7b-143">Показано, как использовать <xref:System.Drawing.ToolboxBitmapAttribute> для отображения значка рядом с пользовательского элемента управления в **элементов**.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-143">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>  
  
 [<span data-ttu-id="4ed7b-144">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="4ed7b-144">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 <span data-ttu-id="4ed7b-145">Демонстрируется использование **тестового контейнера UserControl** для тестирования поведения составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-145">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>  
  
 [<span data-ttu-id="4ed7b-146">Ошибки во время разработки в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ed7b-146">Design-Time Errors in the Windows Forms Designer</span></span>](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 <span data-ttu-id="4ed7b-147">Объяснение значения и использования списка ошибок во время разработки, отображаемого в Microsoft Visual Studio при невозможности загрузить конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-147">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>  
  
 [<span data-ttu-id="4ed7b-148">Разрешение вопросов, связанных с созданием элементов управления и компонентов</span><span class="sxs-lookup"><span data-stu-id="4ed7b-148">Troubleshooting Control and Component Authoring</span></span>](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 <span data-ttu-id="4ed7b-149">Демонстрируются диагностика и исправление распространенных проблем, возникающих при разработке пользовательского компонента или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-149">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4ed7b-150">Ссылка</span><span class="sxs-lookup"><span data-stu-id="4ed7b-150">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="4ed7b-151">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-151">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="4ed7b-152">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-152">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4ed7b-153">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4ed7b-153">Related Sections</span></span>  
 [<span data-ttu-id="4ed7b-154">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ed7b-154">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 <span data-ttu-id="4ed7b-155">Описывается создание пользовательских элементов управления с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-155">Discusses how to create your own custom controls with the .NET Framework.</span></span>  
  
 [<span data-ttu-id="4ed7b-156">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="4ed7b-156">Language Independence and Language-Independent Components</span></span>](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="4ed7b-157">Основные сведения об общеязыковой среде выполнения (CLR), которая предназначена для упрощения создания и использования компонентов.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-157">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="4ed7b-158">Важным аспектом этого упрощения является расширение возможностей взаимодействия между компонентами, написанными на разных языках программирования.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-158">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="4ed7b-159">Спецификация CLS делает возможным создание инструментов и компонентов, которые работают с несколькими языками программирования.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-159">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>  
  
 [<span data-ttu-id="4ed7b-160">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="4ed7b-160">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 <span data-ttu-id="4ed7b-161">Описание включения компонентов или элементов управления для отображения в диалоговом окне **Настройка области элементов**.</span><span class="sxs-lookup"><span data-stu-id="4ed7b-161">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
