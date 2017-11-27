---
title: "Элемент управления ListView (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lists
- checked list items [Windows Forms], Windows Forms controls
- user interface [Windows Forms], creating
- lists [Windows Forms], items with icons
- icons [Windows Forms], listing with items
- list views
- ListView control [Windows Forms]
- list controls [Windows Forms], List view
ms.assetid: 9f71cf5c-82da-488a-a04e-ef52c0817187
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bdecc3ba33b65b09dd277374b5ea96ce5b0f572e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="listview-control-windows-forms"></a><span data-ttu-id="da75a-102">Элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="da75a-102">ListView Control (Windows Forms)</span></span>
<span data-ttu-id="da75a-103">Элемент управления `ListView` Windows Forms отображает список элементов со значками.</span><span class="sxs-lookup"><span data-stu-id="da75a-103">The Windows Forms `ListView` control displays a list of items with icons.</span></span> <span data-ttu-id="da75a-104">Представление списка можно использовать для создания пользовательского интерфейса, аналогичного правой области окна проводника.</span><span class="sxs-lookup"><span data-stu-id="da75a-104">You can use a list view to create a user interface like the right pane of Windows Explorer.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da75a-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="da75a-105">In This Section</span></span>  
 [<span data-ttu-id="da75a-106">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="da75a-106">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 <span data-ttu-id="da75a-107">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="da75a-107">Describes this control and its key features and properties.</span></span>  
  
 [<span data-ttu-id="da75a-108">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-108">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-109">Описывается, как добавлять и удалять элементы из представления списка.</span><span class="sxs-lookup"><span data-stu-id="da75a-109">Describes how to add or remove items from a list view.</span></span>  
  
 [<span data-ttu-id="da75a-110">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-110">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-111">Описывается, как создавать столбцы для вывода сведений о каждом элементе списка.</span><span class="sxs-lookup"><span data-stu-id="da75a-111">Describes how to create columns in order to display information about each list item.</span></span>  
  
 [<span data-ttu-id="da75a-112">Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-112">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-113">Описывается, как связать представление списка с соответствующим списком изображений для отображения крупных или мелких значков.</span><span class="sxs-lookup"><span data-stu-id="da75a-113">Describes how to associate a list view with an appropriate image list for displaying large or small icons.</span></span>  
  
 [<span data-ttu-id="da75a-114">Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-114">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-115">Описывается, как отобразить сведения о каждом элементе списка в столбцах.</span><span class="sxs-lookup"><span data-stu-id="da75a-115">Describes how to display information about each list item in columns.</span></span>  
  
 [<span data-ttu-id="da75a-116">Практическое руководство. Выделение строки элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-116">How to: Select an Item in the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-117">Описывается, как программно выбрать элемент.</span><span class="sxs-lookup"><span data-stu-id="da75a-117">Describes how to programmatically select an item.</span></span>  
  
 [<span data-ttu-id="da75a-118">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-118">How to: Group Items in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-119">Описывается, как создать группы для отображения по категориям и как назначить элементы каждой группе.</span><span class="sxs-lookup"><span data-stu-id="da75a-119">Describes how to create groups for categorized display and how to assign items to each group.</span></span>  
  
 <span data-ttu-id="da75a-120">Эта возможность доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da75a-120">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="da75a-121">Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления</span><span class="sxs-lookup"><span data-stu-id="da75a-121">How to: Enable Tile View in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-122">Описывается, как отобразить элементы в виде плиток, каждая из которых состоит из большого значка и нескольких строк текста.</span><span class="sxs-lookup"><span data-stu-id="da75a-122">Describes how to display items as tiles, each of which is comprised of a large icon and multiple lines of text.</span></span>  
  
 <span data-ttu-id="da75a-123">Эта возможность доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da75a-123">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="da75a-124">Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-124">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)  
 <span data-ttu-id="da75a-125">Описывается, как реализовать обратную связь с пользователем при выполнении операций перетаскивания, в ходе которых метка вставки указывает расположение сброса для каждого положения указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="da75a-125">Describes how to implement user-feedback for drag-and-drop operations in which an insertion mark indicates the drop location for each mouse-pointer position.</span></span>  
  
 <span data-ttu-id="da75a-126">Эта возможность доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da75a-126">This feature is available only for [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)].</span></span>  
  
 [<span data-ttu-id="da75a-127">Практическое руководство. Добавление в элемент управления ListView возможностей поиска</span><span class="sxs-lookup"><span data-stu-id="da75a-127">How to: Add Search Capabilities to a ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
 <span data-ttu-id="da75a-128">Описывается, как программным способом найти элемент с помощью текстового поиска или экранных координат.</span><span class="sxs-lookup"><span data-stu-id="da75a-128">Describes how to programmatically find an item using either text search or screen coordinates.</span></span>  
  
-   <span data-ttu-id="da75a-129">[Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/ms233655\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="da75a-129">[How to: Enable Tile View in a Windows Forms ListView Control Using the Designer](http://msdn.microsoft.com/library/ms233655\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="da75a-130">[Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/ms233671\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="da75a-130">[How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer](http://msdn.microsoft.com/library/ms233671\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="da75a-131">[Практическое руководство. Добавление столбцов в элемент управления ListView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/ms233652\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="da75a-131">[How to: Add Columns to the Windows Forms ListView Control Using the Designer](http://msdn.microsoft.com/library/ms233652\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="da75a-132">[Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора](http://msdn.microsoft.com/library/ms233663\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="da75a-132">[How to: Group Items in a Windows Forms ListView Control Using the Designer](http://msdn.microsoft.com/library/ms233663\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="da75a-133">[Пример. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора](http://msdn.microsoft.com/library/ms171645\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="da75a-133">[Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer](http://msdn.microsoft.com/library/ms171645\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="da75a-134">Ссылка</span><span class="sxs-lookup"><span data-stu-id="da75a-134">Reference</span></span>  
 <span data-ttu-id="da75a-135">Класс <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="da75a-135"><xref:System.Windows.Forms.ListView> class</span></span>  
 <span data-ttu-id="da75a-136">Описание класса и ссылки на все его члены.</span><span class="sxs-lookup"><span data-stu-id="da75a-136">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da75a-137">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="da75a-137">Related Sections</span></span>  
 [<span data-ttu-id="da75a-138">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="da75a-138">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 <span data-ttu-id="da75a-139">Описывается, как выполнять наследование от элемента в представлении списка или узла дерева для добавления любых необходимых полей, методов или конструкторов.</span><span class="sxs-lookup"><span data-stu-id="da75a-139">Describes how to inherit from an item in a list view or a node in a tree view in order to add any fields, methods, or constructors you need.</span></span>  
  
 [<span data-ttu-id="da75a-140">Компонент ImageList</span><span class="sxs-lookup"><span data-stu-id="da75a-140">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 <span data-ttu-id="da75a-141">Описание списка изображений, его основных возможностей и свойств.</span><span class="sxs-lookup"><span data-stu-id="da75a-141">Explains what an image list is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="da75a-142">Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-142">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="da75a-143">Инструкции по компоновке формы Windows Forms с несколькими панелями.</span><span class="sxs-lookup"><span data-stu-id="da75a-143">Gives instructions for laying out a Windows Form with multiple panes.</span></span>  
  
 [<span data-ttu-id="da75a-144">Возможности Windows XP и элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-144">Windows XP Features and Windows Forms Controls</span></span>](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 <span data-ttu-id="da75a-145">Объясняется, как использовать преимущества Windows XP, относящиеся к элементу управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="da75a-145">Explains how to take advantage of Windows XP-specific features that apply to the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da75a-146">См. также</span><span class="sxs-lookup"><span data-stu-id="da75a-146">See Also</span></span>  
 [<span data-ttu-id="da75a-147">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da75a-147">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
