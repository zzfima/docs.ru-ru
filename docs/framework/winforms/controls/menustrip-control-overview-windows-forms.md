---
title: Общие сведения об элементе управления MenuStrip
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734468"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="6ac57-102">Общие сведения об элементе управления MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6ac57-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="6ac57-103">Меню предоставляют пользователям функциональные возможности, сохраняя команды, сгруппированные по общей теме.</span><span class="sxs-lookup"><span data-stu-id="6ac57-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="6ac57-104">Элемент управления <xref:System.Windows.Forms.MenuStrip> был представлен в версии 2,0 .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6ac57-104">The <xref:System.Windows.Forms.MenuStrip> control was introduced in version 2.0 of the .NET Framework.</span></span> <span data-ttu-id="6ac57-105">С помощью элемента управления <xref:System.Windows.Forms.MenuStrip> можно легко создавать меню, аналогичные тем, которые находятся в Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="6ac57-105">With the <xref:System.Windows.Forms.MenuStrip> control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="6ac57-106">Элемент управления <xref:System.Windows.Forms.MenuStrip> поддерживает многодокументный интерфейс (MDI) и слияние меню, всплывающие подсказки и переполнение.</span><span class="sxs-lookup"><span data-stu-id="6ac57-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="6ac57-107">Вы можете повысить удобство использования и удобочитаемость меню, добавив ключи доступа, сочетания клавиш, флажки, изображения и разделители.</span><span class="sxs-lookup"><span data-stu-id="6ac57-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="6ac57-108">Элемент управления <xref:System.Windows.Forms.MenuStrip> заменяет и расширяет функциональные возможности элемента управления <xref:System.Windows.Forms.MainMenu>; Однако элемент управления <xref:System.Windows.Forms.MainMenu> сохраняется для обеспечения обратной совместимости и использования в будущем при выборе.</span><span class="sxs-lookup"><span data-stu-id="6ac57-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="6ac57-109">Способы использования элемента управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="6ac57-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="6ac57-110">Используйте элемент управления <xref:System.Windows.Forms.MenuStrip> для:</span><span class="sxs-lookup"><span data-stu-id="6ac57-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
- <span data-ttu-id="6ac57-111">Создание легко настраиваемых, часто используемых меню, поддерживающих расширенные функции пользовательского интерфейса и макета, таких как упорядочение текста и изображений и выравнивание, операции перетаскивания, MDI, переполнение и альтернативные режимы доступа к командам меню.</span><span class="sxs-lookup"><span data-stu-id="6ac57-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
- <span data-ttu-id="6ac57-112">Поддержка типичного внешнего вида и поведения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="6ac57-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
- <span data-ttu-id="6ac57-113">Согласованность событий для всех контейнеров и содержащихся в них элементов аналогично обработке событий для других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6ac57-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="6ac57-114">В следующей таблице приведены некоторые особо важные свойства <xref:System.Windows.Forms.MenuStrip> и связанных классов.</span><span class="sxs-lookup"><span data-stu-id="6ac57-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="6ac57-115">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="6ac57-115">Property</span></span>|<span data-ttu-id="6ac57-116">Описание</span><span class="sxs-lookup"><span data-stu-id="6ac57-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="6ac57-117">Возвращает или задает <xref:System.Windows.Forms.ToolStripMenuItem>, используемый для вывода списка дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="6ac57-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="6ac57-118">Возвращает или задает, как дочерние меню объединяются с родительскими меню в приложениях MDI.</span><span class="sxs-lookup"><span data-stu-id="6ac57-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="6ac57-119">Возвращает или задает позицию объединенного элемента в меню в приложениях MDI.</span><span class="sxs-lookup"><span data-stu-id="6ac57-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="6ac57-120">Возвращает или задает значение, указывающее, является ли форма контейнером для дочерних форм MDI.</span><span class="sxs-lookup"><span data-stu-id="6ac57-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="6ac57-121">Возвращает или задает значение, указывающее, отображаются ли подсказки для <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ac57-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="6ac57-122">Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.MenuStrip> область переполнения.</span><span class="sxs-lookup"><span data-stu-id="6ac57-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="6ac57-123">Возвращает или задает сочетания клавиш, связанные с <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="6ac57-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="6ac57-124">Возвращает или задает значение, указывающее, отображаются ли сочетания клавиш, связанные с <xref:System.Windows.Forms.ToolStripMenuItem>, рядом с <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="6ac57-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="6ac57-125">В следующей таблице показаны важные <xref:System.Windows.Forms.MenuStrip> сопутствующие классы.</span><span class="sxs-lookup"><span data-stu-id="6ac57-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="6ac57-126">Класс</span><span class="sxs-lookup"><span data-stu-id="6ac57-126">Class</span></span>|<span data-ttu-id="6ac57-127">Описание</span><span class="sxs-lookup"><span data-stu-id="6ac57-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="6ac57-128">Представляет выбираемый параметр, отображаемый в <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6ac57-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="6ac57-129">Представляет контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="6ac57-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="6ac57-130">Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или пункт меню более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="6ac57-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="6ac57-131">Предоставляет базовые функциональные возможности для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem>, которые отображают раскрывающиеся элементы при щелчке.</span><span class="sxs-lookup"><span data-stu-id="6ac57-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ac57-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="6ac57-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
