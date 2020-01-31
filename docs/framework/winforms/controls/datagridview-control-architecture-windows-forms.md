---
title: Архитектура элементов управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742524"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="5bbbe-102">Архитектура элементов управления DataGridView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5bbbe-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="5bbbe-103">Элемент управления <xref:System.Windows.Forms.DataGridView> и связанные с ним классы разработаны как гибкая расширяемая система для отображения и редактирования табличных данных.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="5bbbe-104">Все эти классы содержатся в пространстве имен <xref:System.Windows.Forms?displayProperty=nameWithType> и все они называются префиксом "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="5bbbe-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="5bbbe-105">Элементы архитектуры</span><span class="sxs-lookup"><span data-stu-id="5bbbe-105">Architecture Elements</span></span>  
 <span data-ttu-id="5bbbe-106">Основные <xref:System.Windows.Forms.DataGridView>ные классы являются производными от <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="5bbbe-107">Следующая объектная модель иллюстрирует иерархию наследования <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Схема, на которой показана иерархия объектной модели Датагридвиевелемент.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="5bbbe-109">Класс <xref:System.Windows.Forms.DataGridViewElement> предоставляет ссылку на родительский элемент управления <xref:System.Windows.Forms.DataGridView> и имеет свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A>, которое содержит значение, представляющее сочетание значений перечисления <xref:System.Windows.Forms.DataGridViewElementStates>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="5bbbe-110">В следующих разделах более подробно описаны сопутствующие классы <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="5bbbe-111">датагридвиевелементстатес</span><span class="sxs-lookup"><span data-stu-id="5bbbe-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="5bbbe-112">Перечисление <xref:System.Windows.Forms.DataGridViewElementStates> имеет такие значения:</span><span class="sxs-lookup"><span data-stu-id="5bbbe-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="5bbbe-113">Значения этого перечисления можно сочетать с побитовыми логическими операторами, поэтому свойство <xref:System.Windows.Forms.DataGridViewElement.State%2A> может одновременно выразить несколько состояний.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="5bbbe-114">Например, <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>и <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="5bbbe-115">Ячейки и полосы</span><span class="sxs-lookup"><span data-stu-id="5bbbe-115">Cells and Bands</span></span>  
 <span data-ttu-id="5bbbe-116">Элемент управления <xref:System.Windows.Forms.DataGridView> состоит из двух фундаментальных типов объектов: ячеек и делений.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="5bbbe-117">Все ячейки являются производными от базового класса <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="5bbbe-118">Два типа полос, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>, являются производными от базового класса <xref:System.Windows.Forms.DataGridViewBand>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="5bbbe-119">Элемент управления <xref:System.Windows.Forms.DataGridView> взаимодействует с несколькими классами, но наиболее часто встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>и <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="5bbbe-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="5bbbe-120">DataGridViewCell</span></span>  
 <span data-ttu-id="5bbbe-121">Ячейка является основной единицей взаимодействия для <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="5bbbe-122">Дисплей выравнивается по ячейкам, а ввод данных часто выполняется через ячейки.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="5bbbe-123">Доступ к ячейкам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> класса <xref:System.Windows.Forms.DataGridViewRow>, а также получить доступ к выбранным ячейкам с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5bbbe-124">В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="5bbbe-126">Тип <xref:System.Windows.Forms.DataGridViewCell> является абстрактным базовым классом, от которого наследуются все типы ячеек.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="5bbbe-127"><xref:System.Windows.Forms.DataGridViewCell> и его производные типы не Windows Forms элементы управления, но некоторые элементы управления ведущего Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="5bbbe-128">Любая функция редактирования, поддерживаемая ячейкой, обычно обрабатывается размещаемым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="5bbbe-129"><xref:System.Windows.Forms.DataGridViewCell> объекты не управляют собственными функциями внешнего вида и рисования так же, как Windows Forms элементами управления.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="5bbbe-130">Вместо этого <xref:System.Windows.Forms.DataGridView> отвечает за внешний вид объектов <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="5bbbe-131">Можно значительно повлиять на внешний вид и поведение ячеек, взаимодействуя со свойствами и событиями элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="5bbbe-132">При наличии особых требований к настройкам, которые выходят за пределы возможностей элемента управления <xref:System.Windows.Forms.DataGridView>, можно реализовать собственный класс, производный от <xref:System.Windows.Forms.DataGridViewCell> или одного из его дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="5bbbe-133">В следующем списке показаны классы, производные от <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="5bbbe-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="5bbbe-134">Пользовательские типы ячеек</span><span class="sxs-lookup"><span data-stu-id="5bbbe-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="5bbbe-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="5bbbe-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="5bbbe-136">Схема присоединенного к <xref:System.Windows.Forms.DataGridView> элемента управления хранилища данных выражается в столбцах элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="5bbbe-137">Доступ к столбцам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.Columns%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="5bbbe-138">Доступ к выбранным столбцам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="5bbbe-139">В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="5bbbe-141">Некоторые типы ключевых ячеек имеют соответствующие типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="5bbbe-142">Они являются производными от базового класса <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="5bbbe-143">В следующем списке показаны классы, производные от <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="5bbbe-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="5bbbe-144">Пользовательские типы столбцов</span><span class="sxs-lookup"><span data-stu-id="5bbbe-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="5bbbe-145">Элементы управления редактированием DataGridView</span><span class="sxs-lookup"><span data-stu-id="5bbbe-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="5bbbe-146">Ячейки, поддерживающие расширенные функции редактирования, обычно используют размещенный элемент управления, производный от элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="5bbbe-147">Эти элементы управления также реализуют интерфейс <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="5bbbe-148">Следующая объектная модель иллюстрирует использование этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Схема, показывающая иерархию модели объектов элемента управления редактированием DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="5bbbe-150">Следующие элементы управления для редактирования предоставляются с помощью элемента управления <xref:System.Windows.Forms.DataGridView>:</span><span class="sxs-lookup"><span data-stu-id="5bbbe-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="5bbbe-151">Сведения о создании собственных элементов управления редактирования см. [в разделе как размещать элементы управления в Windows Forms ячейках DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="5bbbe-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="5bbbe-152">В следующей таблице показана связь между типами ячеек, типами столбцов и элементами управления для редактирования.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="5bbbe-153">Тип ячейки</span><span class="sxs-lookup"><span data-stu-id="5bbbe-153">Cell type</span></span>|<span data-ttu-id="5bbbe-154">Размещенный элемент управления</span><span class="sxs-lookup"><span data-stu-id="5bbbe-154">Hosted control</span></span>|<span data-ttu-id="5bbbe-155">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="5bbbe-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="5bbbe-156">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5bbbe-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="5bbbe-157">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5bbbe-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="5bbbe-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5bbbe-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="5bbbe-159">Н/Д</span><span class="sxs-lookup"><span data-stu-id="5bbbe-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="5bbbe-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="5bbbe-160">DataGridViewRow</span></span>  
 <span data-ttu-id="5bbbe-161">Класс <xref:System.Windows.Forms.DataGridViewRow> отображает поля данных записи из хранилища данных, к которому присоединен элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="5bbbe-162">Доступ к строкам элемента управления <xref:System.Windows.Forms.DataGridView> можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.Rows%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="5bbbe-163">Доступ к выбранным строкам можно получить с помощью коллекции <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="5bbbe-164">В следующей объектной модели показано это использование и показана иерархия наследования <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая иерархию объектной модели DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="5bbbe-166">Вы можете создавать собственные типы из класса <xref:System.Windows.Forms.DataGridViewRow>, хотя это и не обязательно.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="5bbbe-167">Элемент управления <xref:System.Windows.Forms.DataGridView> имеет несколько связанных с строками событий и свойств для настройки поведения его <xref:System.Windows.Forms.DataGridViewRow> объектов.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="5bbbe-168">Если включить свойство <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> <xref:System.Windows.Forms.DataGridView> элемента управления, то в качестве последней строки появится специальная строка для добавления новых строк.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="5bbbe-169">Эта строка является частью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции, но она имеет специальные функции, которые могут потребовать вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="5bbbe-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="5bbbe-170">Дополнительные сведения см. в разделе [Использование строки для новых записей в элементе управления Windows Forms DataGridView](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5bbbe-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bbbe-171">См. также:</span><span class="sxs-lookup"><span data-stu-id="5bbbe-171">See also</span></span>

- [<span data-ttu-id="5bbbe-172">Общие сведения об элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="5bbbe-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="5bbbe-173">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bbbe-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="5bbbe-174">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5bbbe-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
