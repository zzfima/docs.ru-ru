---
title: Общие сведения об элементе управления MenuStrip (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975602"
---
# <a name="menustrip-control-overview-windows-forms"></a><span data-ttu-id="8e6b0-102">Общие сведения об элементе управления MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8e6b0-102">MenuStrip Control Overview (Windows Forms)</span></span>
<span data-ttu-id="8e6b0-103">Меню предоставлять функциональные возможности для пользователей, команд, сгруппированные по общей теме.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-103">Menus expose functionality to your users by holding commands that are grouped by a common theme.</span></span>  
  
 <span data-ttu-id="8e6b0-104"><xref:System.Windows.Forms.MenuStrip> Элемент управления является новой возможностью в этой версии Visual Studio и .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-104">The <xref:System.Windows.Forms.MenuStrip> control is new to this version of Visual Studio and the .NET Framework.</span></span> <span data-ttu-id="8e6b0-105">С помощью элемента управления можно легко создать меню, например, используемых в Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-105">With the control, you can easily create menus like those found in Microsoft Office.</span></span>  
  
 <span data-ttu-id="8e6b0-106"><xref:System.Windows.Forms.MenuStrip> Элемент управления поддерживает многодокументного интерфейса (MDI) и слияние меню, всплывающие подсказки и переполнения.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-106">The <xref:System.Windows.Forms.MenuStrip> control supports the multiple-document interface (MDI) and menu merging, tool tips, and overflow.</span></span> <span data-ttu-id="8e6b0-107">Можно улучшить удобство использования и меню, добавив ключи доступа, сочетания клавиш, метки, изображения и разделителей.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-107">You can enhance the usability and readability of your menus by adding access keys, shortcut keys, check marks, images, and separator bars.</span></span>  
  
 <span data-ttu-id="8e6b0-108"><xref:System.Windows.Forms.MenuStrip> Управления заменяет и расширяет его функциональные возможности <xref:System.Windows.Forms.MainMenu> управления; Однако <xref:System.Windows.Forms.MainMenu> элемент управления можно сохранить для обратной совместимости и использования в будущем, если выбран.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-108">The <xref:System.Windows.Forms.MenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.MainMenu> control; however, the <xref:System.Windows.Forms.MainMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
## <a name="ways-to-use-the-menustrip-control"></a><span data-ttu-id="8e6b0-109">Способы использования элемента управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="8e6b0-109">Ways to Use the MenuStrip Control</span></span>  
 <span data-ttu-id="8e6b0-110">Используйте <xref:System.Windows.Forms.MenuStrip> управления:</span><span class="sxs-lookup"><span data-stu-id="8e6b0-110">Use the <xref:System.Windows.Forms.MenuStrip> control to:</span></span>  
  
-   <span data-ttu-id="8e6b0-111">Создание легко настраиваемых, стандартных меню, которые поддерживают Расширенный пользовательский интерфейс и структура функции, такие как текст и изображения упорядочение и выравнивание, операции перетаскивания и вставки, MDI, переполнения и альтернативные режимы доступа к пунктам меню.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-111">Create easily customized, commonly employed menus that support advanced user interface and layout features, such as text and image ordering and alignment, drag-and-drop operations, MDI, overflow, and alternate modes of accessing menu commands.</span></span>  
  
-   <span data-ttu-id="8e6b0-112">Поддерживает типичные внешний вид и поведение операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-112">Support the typical appearance and behavior of the operating system.</span></span>  
  
-   <span data-ttu-id="8e6b0-113">Согласованная обработка событий для всех контейнеров и вложенными элементами, так же, обработки событий для других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-113">Handle events consistently for all containers and contained items, in the same way you handle events for other controls.</span></span>  
  
 <span data-ttu-id="8e6b0-114">В следующей таблице показаны некоторые особенно важно свойства <xref:System.Windows.Forms.MenuStrip> и связанные классы.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-114">The following table shows some particularly important properties of <xref:System.Windows.Forms.MenuStrip> and associated classes.</span></span>  
  
|<span data-ttu-id="8e6b0-115">Свойство</span><span class="sxs-lookup"><span data-stu-id="8e6b0-115">Property</span></span>|<span data-ttu-id="8e6b0-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8e6b0-116">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|<span data-ttu-id="8e6b0-117">Возвращает или задает <xref:System.Windows.Forms.ToolStripMenuItem> , используемый для отображения списка дочерних форм интерфейса MDI.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-117">Gets or sets the <xref:System.Windows.Forms.ToolStripMenuItem> that is used to display a list of MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|<span data-ttu-id="8e6b0-118">Возвращает или задает способ слияния дочерних меню с родительскими меню в приложениях MDI.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-118">Gets or sets how child menus are merged with parent menus in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|<span data-ttu-id="8e6b0-119">Возвращает или задает положение элемента при слиянии в меню в приложениях MDI.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-119">Gets or sets the position of a merged item within a menu in MDI applications.</span></span>|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|<span data-ttu-id="8e6b0-120">Возвращает или задает значение, указывающее, находится ли форма контейнером для дочерних MDI-форм.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-120">Gets or sets a value indicating whether the form is a container for MDI child forms.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|<span data-ttu-id="8e6b0-121">Возвращает или задает значение, указывающее, отображаются ли всплывающие подсказки для <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-121">Gets or sets a value indicating whether tool tips are shown for the <xref:System.Windows.Forms.MenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|<span data-ttu-id="8e6b0-122">Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.MenuStrip> область переполнения.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-122">Gets or sets a value indicating whether the <xref:System.Windows.Forms.MenuStrip> supports overflow functionality.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|<span data-ttu-id="8e6b0-123">Возвращает или задает сочетания клавиш, связанные с <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-123">Gets or sets the shortcut keys associated with the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|<span data-ttu-id="8e6b0-124">Получает или задает значение, указывающее, является ли сочетание клавиш, связанных с <xref:System.Windows.Forms.ToolStripMenuItem> , отображаться рядом с <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-124">Gets or sets a value indicating whether the shortcut keys that are associated with the <xref:System.Windows.Forms.ToolStripMenuItem> are displayed next to the <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>|  
  
 <span data-ttu-id="8e6b0-125">В следующей таблице показаны важные <xref:System.Windows.Forms.MenuStrip> сопутствующих классов.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-125">The following table shows the important <xref:System.Windows.Forms.MenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="8e6b0-126">Класс</span><span class="sxs-lookup"><span data-stu-id="8e6b0-126">Class</span></span>|<span data-ttu-id="8e6b0-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8e6b0-127">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="8e6b0-128">Представляет отдельные пункты, отображаемые на <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-128">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<span data-ttu-id="8e6b0-129">Представляет контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-129">Represents a shortcut menu.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="8e6b0-130">Представляет элемент управления, позволяющий пользователю выбрать один элемент из списка, который отображается, когда пользователь щелкает <xref:System.Windows.Forms.ToolStripDropDownButton> или пункта меню более высокого уровня.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-130">Represents a control that allows the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="8e6b0-131">Предоставляет базовую функциональность для элементов управления, производных от <xref:System.Windows.Forms.ToolStripItem> , отображения элементов раскрывающегося списка при нажатии.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-131">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e6b0-132">См. также</span><span class="sxs-lookup"><span data-stu-id="8e6b0-132">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
