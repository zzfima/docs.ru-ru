---
title: Архитектура элементов управления DataGridView (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 892168ec282fbf168c43515e0718fe5486a345a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130264"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="d9cd3-102">Архитектура элементов управления DataGridView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d9cd3-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="d9cd3-103"><xref:System.Windows.Forms.DataGridView> Управления и связанные с ним классы предназначены для гибкую, расширяемую систему для отображения и редактирования табличных данных.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="d9cd3-104">Все эти классы содержатся в <xref:System.Windows.Forms?displayProperty=nameWithType> пространства имен и они именуются с префиксом «DataGridView».</span><span class="sxs-lookup"><span data-stu-id="d9cd3-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="d9cd3-105">Элементы архитектуры</span><span class="sxs-lookup"><span data-stu-id="d9cd3-105">Architecture Elements</span></span>  
 <span data-ttu-id="d9cd3-106">Основной <xref:System.Windows.Forms.DataGridView> сопутствующих классов являются производными от <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="d9cd3-107">Приведенные ниже объектные модели иллюстрирует <xref:System.Windows.Forms.DataGridViewElement> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая объектная модель DataGridViewElement иерархии.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="d9cd3-109"><xref:System.Windows.Forms.DataGridViewElement> Класс предоставляет ссылку на родительский <xref:System.Windows.Forms.DataGridView> а <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство, которое содержит значение, которое представляет собой сочетание значений из <xref:System.Windows.Forms.DataGridViewElementStates> перечисления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="d9cd3-110">В следующих разделах описываются <xref:System.Windows.Forms.DataGridView> сопутствующих классов более подробно.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="d9cd3-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="d9cd3-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="d9cd3-112"><xref:System.Windows.Forms.DataGridViewElementStates> Перечисление содержит следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d9cd3-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="d9cd3-113">Значения этого перечисления могут сочетаться с побитовые логические операторы, поэтому <xref:System.Windows.Forms.DataGridViewElement.State%2A> свойство можно выразить несколько состояний одновременно.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="d9cd3-114">Например <xref:System.Windows.Forms.DataGridViewElement> может быть одновременно <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, и <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="d9cd3-115">Ячейки и зоны</span><span class="sxs-lookup"><span data-stu-id="d9cd3-115">Cells and Bands</span></span>  
 <span data-ttu-id="d9cd3-116"><xref:System.Windows.Forms.DataGridView> Элемент управления состоит из двух основных типов объектов: ячейки и зоны.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="d9cd3-117">Все ячейки, являются производными от <xref:System.Windows.Forms.DataGridViewCell> базового класса.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="d9cd3-118">Два вида делений, <xref:System.Windows.Forms.DataGridViewColumn> и <xref:System.Windows.Forms.DataGridViewRow>, оба являются производными от <xref:System.Windows.Forms.DataGridViewBand> базового класса.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="d9cd3-119"><xref:System.Windows.Forms.DataGridView> Управления взаимодействует с несколькими классами, но чаще всего встречаются <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, и <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="d9cd3-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="d9cd3-120">DataGridViewCell</span></span>  
 <span data-ttu-id="d9cd3-121">Ячейка является основной единицей взаимодействия для <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="d9cd3-122">Отображение выравнивается по центру ячейки и ввода данных часто выполняется по ячейкам.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="d9cd3-123">Доступ к ячейкам с помощью <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> коллекцию <xref:System.Windows.Forms.DataGridViewRow> , поэтому для доступа к выбранным ячейкам используется <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> коллекцию <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d9cd3-124">Приведенные ниже объектные модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewCell> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая иерархии объектная модель DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="d9cd3-126"><xref:System.Windows.Forms.DataGridViewCell> Тип является абстрактным базовым классом, от которого наследуют все типы ячеек.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="d9cd3-127"><xref:System.Windows.Forms.DataGridViewCell> и его производные типы не являются элементы управления Windows Forms, но некоторые элементы управления ведущего приложения Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="d9cd3-128">Любые изменения функциональных возможностей, поддерживаемых ячейки обычно обрабатывается размещаемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="d9cd3-129"><xref:System.Windows.Forms.DataGridViewCell> объекты контролирует собственные внешним видом и оформлением так же как элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="d9cd3-130">Вместо этого <xref:System.Windows.Forms.DataGridView> несет ответственность за внешний вид его <xref:System.Windows.Forms.DataGridViewCell> объектов.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="d9cd3-131">Вы может существенно повлиять на внешний вид и поведение ячеек, взаимодействуя с <xref:System.Windows.Forms.DataGridView> свойства и события элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="d9cd3-132">При наличии особых требований к настройкам, выходящих за рамки возможностей <xref:System.Windows.Forms.DataGridView> элемента управления, можно реализовать собственный класс, производный от <xref:System.Windows.Forms.DataGridViewCell> или одного из его дочерних классов.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="d9cd3-133">В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="d9cd3-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
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
  
-   <span data-ttu-id="d9cd3-134">Пользовательские типы ячеек</span><span class="sxs-lookup"><span data-stu-id="d9cd3-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="d9cd3-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="d9cd3-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="d9cd3-136">Схема <xref:System.Windows.Forms.DataGridView> элемента управления хранилища данных выражается в <xref:System.Windows.Forms.DataGridView> столбцов элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="d9cd3-137">Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> столбцов элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Columns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="d9cd3-138">Доступ к выбранным столбцам с помощью <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="d9cd3-139">Приведенные ниже объектные модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewColumn> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая объектная модель DataGridViewColumn иерархии.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="d9cd3-141">Некоторые типы ключей ячейки имеют соответствующие типы столбцов.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="d9cd3-142">Они являются производными от <xref:System.Windows.Forms.DataGridViewColumn> базового класса.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="d9cd3-143">В следующем списке приведены классы, производные от <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="d9cd3-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="d9cd3-144">Пользовательские типы столбцов</span><span class="sxs-lookup"><span data-stu-id="d9cd3-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="d9cd3-145">Элементы управления редактирования DataGridView</span><span class="sxs-lookup"><span data-stu-id="d9cd3-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="d9cd3-146">Ячейки, которые обычно поддерживают расширенные функции редактирования используйте размещаемого элемента управления, который является производным от элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="d9cd3-147">Эти элементы управления также реализовать <xref:System.Windows.Forms.IDataGridViewEditingControl> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="d9cd3-148">Приведенные ниже объектные модели иллюстрирует использование этих элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Схема, показывающая иерархии DataGridView редактирования объектная модель элемента управления.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="d9cd3-150">Следующие элементы управления редактирования входящие в состав <xref:System.Windows.Forms.DataGridView> управления:</span><span class="sxs-lookup"><span data-stu-id="d9cd3-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="d9cd3-151">Сведения о создании собственных редактирования элементов управления, см. в разделе [как: Ведущие элементы управления в формах Windows Forms ячеек элемента управления DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="d9cd3-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="d9cd3-152">В следующей таблице показано отношение между типов ячеек, типы столбцов и элементами управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="d9cd3-153">Тип ячейки</span><span class="sxs-lookup"><span data-stu-id="d9cd3-153">Cell type</span></span>|<span data-ttu-id="d9cd3-154">Размещаемый элемент управления</span><span class="sxs-lookup"><span data-stu-id="d9cd3-154">Hosted control</span></span>|<span data-ttu-id="d9cd3-155">Тип столбца</span><span class="sxs-lookup"><span data-stu-id="d9cd3-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="d9cd3-156">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d9cd3-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="d9cd3-157">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d9cd3-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="d9cd3-158">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d9cd3-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="d9cd3-159">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d9cd3-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="d9cd3-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="d9cd3-160">DataGridViewRow</span></span>  
 <span data-ttu-id="d9cd3-161"><xref:System.Windows.Forms.DataGridViewRow> Хранения класс отображает поля данных записи из данных, к которому <xref:System.Windows.Forms.DataGridView> присоединяется элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="d9cd3-162">Вы можете получить доступ к <xref:System.Windows.Forms.DataGridView> строк элемента управления с помощью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="d9cd3-163">Выбранные строки доступны посредством <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> коллекции.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="d9cd3-164">Приведенные ниже объектные модели показан пример использования и показывает <xref:System.Windows.Forms.DataGridViewRow> иерархии наследования.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Схема, показывающая объектная модель DataGridViewRow иерархии.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="d9cd3-166">Можно создавать производные пользовательские типы из <xref:System.Windows.Forms.DataGridViewRow> класса, несмотря на то, что это обычно не нужно выполнять.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="d9cd3-167"><xref:System.Windows.Forms.DataGridView> Элемент управления имеет несколько событий, связанных со строками и свойств для настройки поведения его <xref:System.Windows.Forms.DataGridViewRow> объектов.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="d9cd3-168">Если вы включаете <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> , отдельную строку для добавления новых строк отображается как последняя строка.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="d9cd3-169">Эта строка является частью <xref:System.Windows.Forms.DataGridView.Rows%2A> коллекции, но он имеет специальные функции, которые могут потребовать вашего внимания.</span><span class="sxs-lookup"><span data-stu-id="d9cd3-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="d9cd3-170">Дополнительные сведения см. в разделе [с помощью строки для новых записей в элементе управления DataGridView Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="d9cd3-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9cd3-171">См. также</span><span class="sxs-lookup"><span data-stu-id="d9cd3-171">See also</span></span>

- [<span data-ttu-id="d9cd3-172">Общие сведения об элементе управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="d9cd3-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="d9cd3-173">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9cd3-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d9cd3-174">Использование строки элемента управления DataGridView, предназначенной для ввода новых данных, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9cd3-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
