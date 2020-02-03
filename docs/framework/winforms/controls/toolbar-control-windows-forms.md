---
title: Элемент управления ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 027c96bb49e9446244e4b08ba93c551ef043b3c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735456"
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="9874b-102">Элемент управления ToolBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9874b-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="9874b-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления `ToolBar` и расширяет его функциональные возможности; однако при необходимости элемент управления `ToolBar` можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="9874b-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9874b-104">Элемент управления Windows Forms `ToolBar` используется в формах в качестве панели управления, на которой выводится ряд раскрывающихся меню и кнопок с растровыми изображениями, активирующих команды.</span><span class="sxs-lookup"><span data-stu-id="9874b-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="9874b-105">То есть щелчок по кнопке на панели инструментов эквивалентен выбору команды в меню.</span><span class="sxs-lookup"><span data-stu-id="9874b-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="9874b-106">Для кнопок можно настроить режим поведения кнопок, раскрывающихся меню или разделителей.</span><span class="sxs-lookup"><span data-stu-id="9874b-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="9874b-107">Обычно на панели инструментов содержатся кнопки и меню, соответствующие элементам в структуре меню приложения, которые предоставляют быстрый доступ к наиболее часто используемым в приложении функциям и командам.</span><span class="sxs-lookup"><span data-stu-id="9874b-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9874b-108">Свойство `ToolBar` элемента управления <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> принимает в качестве ссылки экземпляр класса <xref:System.Windows.Forms.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="9874b-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="9874b-109">При использовании подобных кнопок на панели инструментов приложения будьте внимательны в выборе передаваемой ссылки, так как это свойство принимает любой объект, наследуемый от класса <xref:System.Windows.Forms.Menu>.</span><span class="sxs-lookup"><span data-stu-id="9874b-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9874b-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="9874b-110">In This Section</span></span>  
 [<span data-ttu-id="9874b-111">Общие сведения об элементе управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="9874b-111">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="9874b-112">Общие понятия, связанные с элементом управления `ToolBar`, который позволяет разрабатывать пользовательские панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="9874b-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="9874b-113">Практическое руководство. Добавление кнопок в элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="9874b-113">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="9874b-114">Описываются способы добавления кнопок в элемент управления `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="9874b-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="9874b-115">Практическое руководство. Определение значка для кнопки элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="9874b-115">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="9874b-116">Описываются способы отображения значков на кнопках элемента управления `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="9874b-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="9874b-117">Практическое руководство. Активация событий меню для кнопок элемента управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="9874b-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="9874b-118">Инструкции по написанию кода для определения нажатой пользователем кнопки элемента управления `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="9874b-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="9874b-119">Также см. раздел [как определить значок для кнопки панели инструментов с помощью конструктора](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [как добавить кнопки в элемент управления ToolBar с помощью конструктора](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9874b-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [How to: Add Buttons to a ToolBar Control Using the Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9874b-120">Справочник</span><span class="sxs-lookup"><span data-stu-id="9874b-120">Reference</span></span>  
 <span data-ttu-id="9874b-121">Класс <xref:System.Windows.Forms.ToolBar></span><span class="sxs-lookup"><span data-stu-id="9874b-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="9874b-122">Справочная информация о классе и его членах.</span><span class="sxs-lookup"><span data-stu-id="9874b-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9874b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9874b-123">Related Sections</span></span>  
 [<span data-ttu-id="9874b-124">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9874b-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="9874b-125">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="9874b-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="9874b-126">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9874b-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)  
 <span data-ttu-id="9874b-127">Описываются панели инструментов, на которых можно разместить меню, элементы управления и пользовательские элементы управления в приложениях Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9874b-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
