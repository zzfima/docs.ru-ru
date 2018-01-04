---
title: "Архитектура элементов управления DataGridView (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b3e51b87cdd766adcc10aa3f682647b28fbbe4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="f6ed3-102">Архитектура элементов управления DataGridView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f6ed3-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="f6ed3-103"><xref:System.Windows.Forms.DataGridView> Управления и его связанные классы предназначены для гибкую расширяемую систему для отображения и изменения табличных данных.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="f6ed3-104">Эти классы содержатся в <xref:System.Windows.Forms?displayProperty=nameWithType> пространства имен и они именуются с префиксом «DataGridView».</span><span class="sxs-lookup"><span data-stu-id="f6ed3-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="f6ed3-105">Элементы архитектуры</span><span class="sxs-lookup"><span data-stu-id="f6ed3-105">Architecture Elements</span></span>  
 <span data-ttu-id="f6ed3-106">Основной <xref:System.Windows.Forms.DataGridView> сопутствующих классов являются производными от <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="f6ed3-107">Следующей объектной модели показано <xref:System.Windows.Forms.DataGridViewElement> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f6ed3-108">![Объектная модель DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="f6ed3-108">![DataGridViewElement Object Model](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="f6ed3-109">Объектная модель DataGridViewElement</span><span class="sxs-lookup"><span data-stu-id="f6ed3-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="f6ed3-110"><xref:System.Windows.Forms.DataGridViewElement> Класс предоставляет ссылку на родительский объект <xref:System.Windows.Forms.DataGridView> управления и имеет <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство, которое содержит значение, которое представляет сочетание значений из <xref:System.Windows.Forms.DataGridViewElementStates> перечисления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="f6ed3-111">В следующих разделах описаны <xref:System.Windows.Forms.DataGridView> сопутствующих классов более подробно.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="f6ed3-112">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="f6ed3-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="f6ed3-113"><xref:System.Windows.Forms.DataGridViewElementStates> Перечисление содержит следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f6ed3-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="f6ed3-114">Значения этого перечисления могут объединяться с побитовые логические операторы, поэтому <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойства можно выразить несколько состояний одновременно.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="f6ed3-115">Например <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, и <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="f6ed3-116">Ячейки и зоны</span><span class="sxs-lookup"><span data-stu-id="f6ed3-116">Cells and Bands</span></span>  
 <span data-ttu-id="f6ed3-117"><xref:System.Windows.Forms.DataGridView> Управления состоит из двух основных типов объектов: ячеек и зон.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="f6ed3-118">Все ячейки являются производными от <xref:System.Windows.Forms.DataGridViewCell> базового класса.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="f6ed3-119">Два вида делений, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>, оба являются производными от <xref:System.Windows.Forms.DataGridViewBand> базового класса.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="f6ed3-120"><xref:System.Windows.Forms.DataGridView> Управления взаимодействует с несколькими классами, но чаще всего встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, и <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="f6ed3-121">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="f6ed3-121">DataGridViewCell</span></span>  
 <span data-ttu-id="f6ed3-122">Ячейка является базовой единицей взаимодействия для <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="f6ed3-123">Отображение выравнивается по центру ячейки и ввода данных часто осуществляется с помощью ячеек.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="f6ed3-124">Доступ к ячейкам с помощью <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> коллекцию <xref:System.Windows.Forms.DataGridViewRow> класса и имеют доступ к выбранным ячейкам с помощью <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> коллекцию <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f6ed3-125">В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewCell> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f6ed3-126">![Объектная модель DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="f6ed3-126">![DataGridViewCell Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="f6ed3-127">Объектная модель DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="f6ed3-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="f6ed3-128"><xref:System.Windows.Forms.DataGridViewCell> Тип является абстрактным базовым классом, от которого наследуют все типы ячеек.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="f6ed3-129"><xref:System.Windows.Forms.DataGridViewCell>и его производные типы не являются элементы управления Windows Forms, но некоторые элементы управления ведущего приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="f6ed3-130">Любые изменения функциональных возможностей, поддерживаемых ячейки обычно обрабатываются размещенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="f6ed3-131"><xref:System.Windows.Forms.DataGridViewCell>объекты контролирует собственные внешним видом и оформлением так же как элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="f6ed3-132">Вместо этого <xref:System.Windows.Forms.DataGridView> отвечает за внешний вид его <xref:System.Windows.Forms.DataGridViewCell> объектов.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="f6ed3-133">Вы может существенно повлиять на внешний вид и поведение ячеек, взаимодействуя с <xref:System.Windows.Forms.DataGridView> свойства и события для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="f6ed3-134">При наличии особых требований к настройкам, выходящих за рамки возможностей <xref:System.Windows.Forms.DataGridView> управления, можно реализовать собственный класс, производный от <xref:System.Windows.Forms.DataGridViewCell> или один из его дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="f6ed3-135">В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="f6ed3-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="f6ed3-136">Пользовательские типы ячеек</span><span class="sxs-lookup"><span data-stu-id="f6ed3-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="f6ed3-137">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="f6ed3-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="f6ed3-138">Схема <xref:System.Windows.Forms.DataGridView> элемента управления хранилища данных представляется в формате <xref:System.Windows.Forms.DataGridView> столбцов элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="f6ed3-139">Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> столбцов элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Columns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="f6ed3-140">Выбранные столбцы доступны с помощью <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="f6ed3-141">В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewColumn> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f6ed3-142">![Объектная модель DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="f6ed3-142">![DataGridViewColumn Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="f6ed3-143">Объектная модель DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="f6ed3-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="f6ed3-144">Некоторые типы ключей ячейки имеют соответствующие типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="f6ed3-145">Они являются производными <xref:System.Windows.Forms.DataGridViewColumn> базового класса.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="f6ed3-146">В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="f6ed3-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="f6ed3-147">Пользовательские типы столбцов</span><span class="sxs-lookup"><span data-stu-id="f6ed3-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="f6ed3-148">Элементы управления редактирования DataGridView</span><span class="sxs-lookup"><span data-stu-id="f6ed3-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="f6ed3-149">Ячейки, поддерживающие расширенные функции редактирования, обычно используют размещенного элемента управления, который является производным от элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="f6ed3-150">Эти элементы управления также реализовать <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="f6ed3-151">В следующей объектной модели показано использование этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="f6ed3-152">![Объектная модель элемента управления редактирования DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="f6ed3-152">![DataGridView Editing Control Object Model](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="f6ed3-153">Объектная модель редактирования элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="f6ed3-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="f6ed3-154">Следующие элементы управления для редактирования, предоставляемых с <xref:System.Windows.Forms.DataGridView> управления:</span><span class="sxs-lookup"><span data-stu-id="f6ed3-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="f6ed3-155">Сведения о создании собственных редактирования элементов управления см. в разделе [как: элементы управления ведущего приложения в ячеек элемента управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="f6ed3-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="f6ed3-156">В следующей таблице показаны отношения между типов ячеек, типы столбцов и элементами управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="f6ed3-157">Тип ячейки</span><span class="sxs-lookup"><span data-stu-id="f6ed3-157">Cell type</span></span>|<span data-ttu-id="f6ed3-158">Размещаемый элемент управления</span><span class="sxs-lookup"><span data-stu-id="f6ed3-158">Hosted control</span></span>|<span data-ttu-id="f6ed3-159">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="f6ed3-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="f6ed3-160">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6ed3-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="f6ed3-161">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6ed3-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="f6ed3-162">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6ed3-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="f6ed3-163">Н/Д</span><span class="sxs-lookup"><span data-stu-id="f6ed3-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="f6ed3-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="f6ed3-164">DataGridViewRow</span></span>  
 <span data-ttu-id="f6ed3-165"><xref:System.Windows.Forms.DataGridViewRow> Хранения класс отображает поля данных записи из данных, к которому <xref:System.Windows.Forms.DataGridView> присоединенного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="f6ed3-166">Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> строк элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="f6ed3-167">Выбранные строки доступны с помощью <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="f6ed3-168">В следующей объектной модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewRow> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="f6ed3-169">![Объектная модель DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="f6ed3-169">![DataGridViewRow Object Model](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="f6ed3-170">Объектная модель DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="f6ed3-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="f6ed3-171">Можно создавать производные типы из <xref:System.Windows.Forms.DataGridViewRow> класса, хотя это обычно не требуется.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="f6ed3-172"><xref:System.Windows.Forms.DataGridView> Управления имеет несколько связанных со строками событий и свойств для настройки поведения его <xref:System.Windows.Forms.DataGridViewRow> объектов.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="f6ed3-173">При включении <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> , специальную строку для добавления новых строк отображается в виде последней строки.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="f6ed3-174">Эта строка является частью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции, но он имеет специальные функции, которые могут потребовать вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="f6ed3-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="f6ed3-175">Дополнительные сведения см. в разделе [с помощью строки для новых записей в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f6ed3-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ed3-176">См. также</span><span class="sxs-lookup"><span data-stu-id="f6ed3-176">See Also</span></span>  
 [<span data-ttu-id="f6ed3-177">Общие сведения об элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="f6ed3-177">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [<span data-ttu-id="f6ed3-178">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6ed3-178">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="f6ed3-179">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6ed3-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
