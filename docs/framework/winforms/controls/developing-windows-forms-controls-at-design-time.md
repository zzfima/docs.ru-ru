---
title: Проектирование элементов управления во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dac049ea6a51037daa0e23dc93476e4410b2df06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745986"
---
# <a name="develop-windows-forms-controls-at-design-time"></a><span data-ttu-id="9fca4-102">Разработка элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="9fca4-102">Develop Windows Forms controls at design time</span></span>

<span data-ttu-id="9fca4-103">Среда .NET Framework предоставляет широкий набор технологий создания элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-103">For control authors, the .NET Framework provides a wealth of control authoring technology.</span></span> <span data-ttu-id="9fca4-104">Авторы больше не ограничены созданием составных элементов управления, которые действуют как коллекция стандартных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-104">Authors are no longer limited to designing composite controls that act as a collection of preexisting controls.</span></span> <span data-ttu-id="9fca4-105">Через наследование можно создать свои собственные элементы управления на основе существующих составных элементов управления или существующих элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9fca4-105">Through inheritance, you can create your own controls from preexisting composite controls or preexisting Windows Forms controls.</span></span> <span data-ttu-id="9fca4-106">Можно также создать собственные элементы управления, реализующие настраиваемое рисование.</span><span class="sxs-lookup"><span data-stu-id="9fca4-106">You can also design your own controls that implement custom painting.</span></span> <span data-ttu-id="9fca4-107">Эти возможности обеспечивают высокую степень гибкости разработки и функциональности визуального интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9fca4-107">These options enable a great deal of flexibility to the design and functionality of the visual interface.</span></span> <span data-ttu-id="9fca4-108">Чтобы воспользоваться преимуществами этих функций, вы должны быть знакомы с понятиями объектно-ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="9fca4-108">To take advantage of these features, you should be familiar with object-based programming concepts.</span></span>

> [!NOTE]
> <span data-ttu-id="9fca4-109">Нет необходимости глубокого понимания наследования, но может оказаться полезным ознакомиться с [основами наследования (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span><span class="sxs-lookup"><span data-stu-id="9fca4-109">It is not necessary to have a thorough understanding of inheritance, but you may find it useful to refer to [Inheritance basics (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).</span></span>

<span data-ttu-id="9fca4-110">Если вам необходимо создать пользовательский элемент управления для использования в веб-формах, см. раздел [Разработка пользовательских серверных элементов управления ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9fca4-110">If you want to create custom controls to use on Web Forms, see [Developing Custom ASP.NET Server Controls](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9fca4-111">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9fca4-111">In this section</span></span>

<span data-ttu-id="9fca4-112">[Пошаговое руководство. Создание составного элемента управления](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-112">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="9fca4-113">Демонстрируется создание простого составного элемента управления в C#.</span><span class="sxs-lookup"><span data-stu-id="9fca4-113">Shows how to create a simple composite control in C#.</span></span>

<span data-ttu-id="9fca4-114">[Пошаговое руководство. наследование от Windows Formsного элемента управления](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-114">[Walkthrough: Inheriting from a Windows Forms Control](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)</span></span>\
<span data-ttu-id="9fca4-115">Демонстрируется создание простого элемента управления Windows Forms с помощью наследования в C#.</span><span class="sxs-lookup"><span data-stu-id="9fca4-115">Shows how to create a simple Windows Forms control using inheritance in C#.</span></span>

<span data-ttu-id="9fca4-116">[Пошаговое руководство. выполнение стандартных задач с использованием смарт-тегов для элементов управления Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-116">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](performing-common-tasks-using-smart-tags-on-wf-controls.md)</span></span>\
<span data-ttu-id="9fca4-117">Демонстрируется использование функции смарт-тегов в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9fca4-117">Shows how to use the smart tag feature on Windows Forms controls.</span></span>

<span data-ttu-id="9fca4-118">[Пошаговое руководство. Сериализация коллекций стандартных типов с помощью десигнерсериализатионвисибилитяттрибуте](serializing-collections-designerserializationvisibilityattribute.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-118">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)</span></span>\
<span data-ttu-id="9fca4-119">Показывает, как использовать атрибут <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> для сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="9fca4-119">Shows how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attribute to serialize a collection.</span></span>

<span data-ttu-id="9fca4-120">[Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-120">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)</span></span>\
<span data-ttu-id="9fca4-121">Демонстрируется процедура отладки поведения элемента управления Windows Forms во время разработки.</span><span class="sxs-lookup"><span data-stu-id="9fca4-121">Shows how to debug the design-time behavior of a Windows Forms control.</span></span>

<span data-ttu-id="9fca4-122">[Пошаговое руководство. Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio](creating-a-wf-control-design-time-features.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-122">[Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md)</span></span>\
<span data-ttu-id="9fca4-123">Демонстрируется интеграция составного элемента управления в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="9fca4-123">Shows how to tightly integrate a composite control into the design environment.</span></span>

<span data-ttu-id="9fca4-124">[Практическое руководство. Создание элементов управления для форм Windows Forms](how-to-author-controls-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-124">[How to: Author Controls for Windows Forms](how-to-author-controls-for-windows-forms.md)</span></span>\
<span data-ttu-id="9fca4-125">Общие рекомендации по реализации элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9fca4-125">Provides an overview of considerations for implementing a Windows Forms control.</span></span>

<span data-ttu-id="9fca4-126">[Практическое руководство. Создание составных элементов управления](how-to-author-composite-controls.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-126">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>\
<span data-ttu-id="9fca4-127">Демонстрируется создание элемента управления путем наследования из составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-127">Shows how to create a control by inheriting from a composite control.</span></span>

<span data-ttu-id="9fca4-128">[Практическое руководство. Наследование класса UserControl](how-to-inherit-from-the-usercontrol-class.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-128">[How to: Inherit from the UserControl Class](how-to-inherit-from-the-usercontrol-class.md)</span></span>\
<span data-ttu-id="9fca4-129">Обзор процедуры создания составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-129">Provides an overview of the procedure for creating a composite control.</span></span>

<span data-ttu-id="9fca4-130">[Практическое руководство. Наследование существующих элементов управления Windows Forms](how-to-inherit-from-existing-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-130">[How to: Inherit from Existing Windows Forms Controls](how-to-inherit-from-existing-windows-forms-controls.md)</span></span>\
<span data-ttu-id="9fca4-131">Демонстрирует создание расширенного элемента управления путем наследования от класса элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="9fca4-131">Shows how to create an extended control by inheriting from the <xref:System.Windows.Forms.Button> control class.</span></span>

<span data-ttu-id="9fca4-132">[Практическое руководство. Наследование класса Control](how-to-inherit-from-the-control-class.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-132">[How to: Inherit from the Control Class](how-to-inherit-from-the-control-class.md)</span></span>\
<span data-ttu-id="9fca4-133">Обзор создания расширенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-133">Provides an overview of creating an extended control.</span></span>

<span data-ttu-id="9fca4-134">[Как выровняйте элемент управления по краям форм во время разработки](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-134">[How to: Align a Control to the Edges of Forms at Design Time](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)</span></span>\
<span data-ttu-id="9fca4-135">Показывает, как использовать свойство <xref:System.Windows.Forms.Control.Dock%2A> для согласования элемента управления с границей занимаемой им формы.</span><span class="sxs-lookup"><span data-stu-id="9fca4-135">Shows how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="9fca4-136">[Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-136">[How to: Display a Control in the Choose Toolbox Items Dialog Box](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)</span></span>\
<span data-ttu-id="9fca4-137">Описание процедуры установки элемента управления таким образом, чтобы он отображался в диалоговом окне **Настройка области элементов**.</span><span class="sxs-lookup"><span data-stu-id="9fca4-137">Shows the procedure for installing your control so that it appears in the **Customize Toolbox** dialog box.</span></span>

<span data-ttu-id="9fca4-138">[Руководство. Предоставление точечного рисунка панели элементов для элемента управления](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-138">[How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md)</span></span>\
<span data-ttu-id="9fca4-139">Показывает, как использовать <xref:System.Drawing.ToolboxBitmapAttribute> для отображения значка рядом с пользовательским элементом управления на **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="9fca4-139">Shows how to use the <xref:System.Drawing.ToolboxBitmapAttribute> to display an icon next to your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="9fca4-140">[Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-140">[How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)</span></span>\
<span data-ttu-id="9fca4-141">Демонстрируется использование **тестового контейнера UserControl** для тестирования поведения составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-141">Shows how to use the **UserControl Test Container** to test the behavior of a composite control.</span></span>

<span data-ttu-id="9fca4-142">[Ошибки во время разработки в конструкторе Windows Forms](design-time-errors-in-the-windows-forms-designer.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-142">[Design-Time Errors in the Windows Forms Designer](design-time-errors-in-the-windows-forms-designer.md)</span></span>\
<span data-ttu-id="9fca4-143">Объяснение значения и использования списка ошибок во время разработки, отображаемого в Microsoft Visual Studio при невозможности загрузить конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9fca4-143">Explains the meaning and use of the Design-Time Error List that appears in Microsoft Visual Studio when the Windows Forms designer fails to load.</span></span>

<span data-ttu-id="9fca4-144">[Разрешение вопросов, связанных с созданием элементов управления и компонентов](troubleshooting-control-and-component-authoring.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-144">[Troubleshooting Control and Component Authoring](troubleshooting-control-and-component-authoring.md)</span></span>\
<span data-ttu-id="9fca4-145">Демонстрируются диагностика и исправление распространенных проблем, возникающих при разработке пользовательского компонента или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9fca4-145">Shows how to diagnose and fix common issues that can occur when you author a custom component or control.</span></span>

## <a name="reference"></a><span data-ttu-id="9fca4-146">Справочник</span><span class="sxs-lookup"><span data-stu-id="9fca4-146">Reference</span></span>

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a><span data-ttu-id="9fca4-147">См. также</span><span class="sxs-lookup"><span data-stu-id="9fca4-147">Related sections</span></span>

<span data-ttu-id="9fca4-148">[Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-148">[Developing Custom Windows Forms Controls with the .NET Framework](developing-custom-windows-forms-controls.md)</span></span>\
<span data-ttu-id="9fca4-149">Описывается создание пользовательских элементов управления с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9fca4-149">Discusses how to create your own custom controls with the .NET Framework.</span></span>

<span data-ttu-id="9fca4-150">[Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-150">[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)</span></span>\
<span data-ttu-id="9fca4-151">Основные сведения об общеязыковой среде выполнения (CLR), которая предназначена для упрощения создания и использования компонентов.</span><span class="sxs-lookup"><span data-stu-id="9fca4-151">Introduces the common language runtime, which is designed to simplify the creation and use of components.</span></span> <span data-ttu-id="9fca4-152">Важным аспектом этого упрощения является расширение возможностей взаимодействия между компонентами, написанными на разных языках программирования.</span><span class="sxs-lookup"><span data-stu-id="9fca4-152">An important aspect of this simplification is enhanced interoperability between components written using different programming languages.</span></span> <span data-ttu-id="9fca4-153">Спецификация CLS делает возможным создание инструментов и компонентов, которые работают с несколькими языками программирования.</span><span class="sxs-lookup"><span data-stu-id="9fca4-153">The Common Language Specification (CLS) makes it possible to create tools and components that work with multiple programming languages.</span></span>

<span data-ttu-id="9fca4-154">[Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span><span class="sxs-lookup"><span data-stu-id="9fca4-154">[Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)</span></span>\
<span data-ttu-id="9fca4-155">Описание включения компонентов или элементов управления для отображения в диалоговом окне **Настройка области элементов**.</span><span class="sxs-lookup"><span data-stu-id="9fca4-155">Describes how to enable your component or control to be displayed in the **Customize Toolbox** dialog box.</span></span>
