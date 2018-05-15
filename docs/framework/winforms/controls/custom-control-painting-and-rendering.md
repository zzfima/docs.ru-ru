---
title: Рисование и отрисовка пользовательского элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 18a05a739f42d41a650e66723f44aae69c1707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="d3e2c-102">Рисование и отрисовка пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="d3e2c-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="d3e2c-103">Пользовательское рисование элементов управления является одним из сложных задач, стало проще платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="d3e2c-104">При создании пользовательского элемента управления, существует несколько вариантов относительно графического внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="d3e2c-105">При создании элемента управления, который наследует от `Control`, необходимо предоставить код, позволяющий элементу управления выполнить визуализацию графического представления.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="d3e2c-106">При создании пользовательского элемента управления путем наследования от `UserControl`, или при наследовании от одного из элементов управления Windows Forms, может переопределить стандартное графическое представление и предоставить собственный код графики.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="d3e2c-107">Если вы хотите предоставить пользовательскую отрисовку для составных элементов управления `UserControl` при разработке, параметров становится более ограниченным, но по-прежнему можно воспользоваться широкими графическими возможностями для элементов управления и приложений.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3e2c-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d3e2c-108">In This Section</span></span>  
 [<span data-ttu-id="d3e2c-109">Отрисовка элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d3e2c-109">Rendering a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 <span data-ttu-id="d3e2c-110">Показано, как запрограммировать логику отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="d3e2c-111">Элементы управления, разработанные пользователем</span><span class="sxs-lookup"><span data-stu-id="d3e2c-111">User-Drawn Controls</span></span>](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 <span data-ttu-id="d3e2c-112">Обзор действий, необходимых для записи и переопределения код отрисовки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="d3e2c-113">Составные элементы управления</span><span class="sxs-lookup"><span data-stu-id="d3e2c-113">Constituent Controls</span></span>](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 <span data-ttu-id="d3e2c-114">Описывает, как реализовать пользовательский код отрисовки для составных элементов управления в пользовательских элементах управления и формах.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="d3e2c-115">Практическое руководство. Скрытие элемента управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="d3e2c-115">How to: Make Your Control Invisible at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="d3e2c-116">Показано, как использовать <xref:System.Windows.Forms.Control.Visible%2A> свойство, чтобы скрыть или отобразить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="d3e2c-117">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="d3e2c-117">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="d3e2c-118">Показано, как использовать <xref:System.Windows.Forms.Control.SetStyle%2A> метод для создания цвет фона, который является непрозрачным, прозрачным или полупрозрачным.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="d3e2c-119">Отрисовка элементов управления с применением визуальных стилей</span><span class="sxs-lookup"><span data-stu-id="d3e2c-119">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="d3e2c-120">Показано, как отображать элементы управления с использованием стилей оформления в операционных системах, которые их поддерживают.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d3e2c-121">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d3e2c-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="d3e2c-122">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="d3e2c-123">Описывает данный класс и предоставляет ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="d3e2c-124">Описание этого метода.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d3e2c-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d3e2c-125">Related Sections</span></span>  
 [<span data-ttu-id="d3e2c-126">Практическое руководство. Создание графических объектов для рисования</span><span class="sxs-lookup"><span data-stu-id="d3e2c-126">How to: Create Graphics Objects for Drawing</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="d3e2c-127">Представляет [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] функциональных возможностей графики из Visual Studio и ссылки на дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-127">Introduces [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="d3e2c-128">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="d3e2c-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="d3e2c-129">Описание типов пользовательских элементов управления, которые можно создать.</span><span class="sxs-lookup"><span data-stu-id="d3e2c-129">Describes the kinds of custom controls you can author.</span></span>
