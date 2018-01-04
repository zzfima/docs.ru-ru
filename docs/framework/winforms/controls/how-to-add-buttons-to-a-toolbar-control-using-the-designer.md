---
title: "Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccd63cb88661db7601b87eec6bdf3a959afb8bbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="dd069-102">Практическое руководство. Добавление кнопок в элемент управления ToolBar с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="dd069-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="dd069-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="dd069-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="dd069-104">Неотъемлемой частью <xref:System.Windows.Forms.ToolBar> элемент управления является кнопок, добавьте к нему.</span><span class="sxs-lookup"><span data-stu-id="dd069-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="dd069-105">Они используются для обеспечения быстрого доступа к командам меню или, кроме того, их можно разместить в другой области пользовательского интерфейса приложения для представления пользователям, которые недоступны в структуре меню команд.</span><span class="sxs-lookup"><span data-stu-id="dd069-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="dd069-106">В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dd069-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="dd069-107">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="dd069-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd069-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="dd069-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dd069-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="dd069-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dd069-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="dd069-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="dd069-111">Чтобы добавить кнопки во время разработки</span><span class="sxs-lookup"><span data-stu-id="dd069-111">To add buttons at design time</span></span>  
  
1.  <span data-ttu-id="dd069-112">Выберите элемент управления <xref:System.Windows.Forms.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dd069-112">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="dd069-113">В **свойства** окно, нажмите кнопку <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство, чтобы выбрать ее и нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) кнопку, чтобы открыть **редактора коллекции**.</span><span class="sxs-lookup"><span data-stu-id="dd069-113">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="dd069-114">Используйте **добавить** и **удалить** кнопки, чтобы добавить или удалить кнопки из <xref:System.Windows.Forms.ToolBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dd069-114">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
4.  <span data-ttu-id="dd069-115">Настройте свойства отдельных кнопок в **свойства** окно, которое появляется в области в правой части редактора.</span><span class="sxs-lookup"><span data-stu-id="dd069-115">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="dd069-116">В следующей таблице показаны некоторые важные свойства.</span><span class="sxs-lookup"><span data-stu-id="dd069-116">The following table shows some important properties to consider.</span></span>  
  
    |<span data-ttu-id="dd069-117">Свойство.</span><span class="sxs-lookup"><span data-stu-id="dd069-117">Property</span></span>|<span data-ttu-id="dd069-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="dd069-118">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="dd069-119">Задает меню, отображаемое на кнопке панели инструментов, раскрывающийся список.</span><span class="sxs-lookup"><span data-stu-id="dd069-119">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="dd069-120">Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="dd069-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="dd069-121">Это свойство принимает экземпляр <xref:System.Windows.Forms.ContextMenu> класса в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="dd069-121">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="dd069-122">Задает ли кнопка-переключатель в нейтральном положении.</span><span class="sxs-lookup"><span data-stu-id="dd069-122">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="dd069-123">Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="dd069-123">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="dd069-124">Задает, является ли кнопка-переключатель в данный момент в нажатом состоянии.</span><span class="sxs-lookup"><span data-stu-id="dd069-124">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="dd069-125">Кнопки панели инструментов <xref:System.Windows.Forms.ToolBarButton.Style%2A> свойству необходимо присвоить значение <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> или <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span><span class="sxs-lookup"><span data-stu-id="dd069-125">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="dd069-126">Задает стиль кнопки панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="dd069-126">Sets the style of the toolbar button.</span></span> <span data-ttu-id="dd069-127">Должно быть одно из значений в <xref:System.Windows.Forms.ToolBarButtonStyle> перечисления.</span><span class="sxs-lookup"><span data-stu-id="dd069-127">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="dd069-128">Текстовая строка, отображающийся на кнопке.</span><span class="sxs-lookup"><span data-stu-id="dd069-128">The text string displayed by the button.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="dd069-129">Текст, отображаемый в виде всплывающей подсказки для кнопки.</span><span class="sxs-lookup"><span data-stu-id="dd069-129">The text that appears as a ToolTip for the button.</span></span>|  
  
5.  <span data-ttu-id="dd069-130">Нажмите кнопку **ОК** закрыть диалоговое окно и создать указанное панелей.</span><span class="sxs-lookup"><span data-stu-id="dd069-130">Click **OK** to close the dialog box and create the panels you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd069-131">См. также</span><span class="sxs-lookup"><span data-stu-id="dd069-131">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="dd069-132">Практическое руководство. Определение значка для кнопки элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="dd069-132">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [<span data-ttu-id="dd069-133">Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="dd069-133">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="dd069-134">Общие сведения об элементе управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="dd069-134">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [<span data-ttu-id="dd069-135">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="dd069-135">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
