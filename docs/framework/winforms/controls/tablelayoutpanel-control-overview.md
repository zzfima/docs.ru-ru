---
title: Общие сведения об элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- TableLayoutPanel
helpviewer_keywords:
- controls [Windows Forms], resizing
- resizable controls [Windows Forms]
- Windows Forms controls, proportional resizing
- Windows Forms, proportional resizing of controls
- layout [Windows Forms], TableLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
ms.assetid: 337661c8-61cb-44ee-93e0-3662bddec327
ms.openlocfilehash: 65daba0ce1a6f1c37fb257c1029396577821aad9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009634"
---
# <a name="tablelayoutpanel-control-overview"></a><span data-ttu-id="31051-102">Общие сведения об элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-102">TableLayoutPanel Control Overview</span></span>
<span data-ttu-id="31051-103">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> упорядочивает содержимое в сетке.</span><span class="sxs-lookup"><span data-stu-id="31051-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="31051-104">Так как макет строится как во время разработки, так и во время выполнения, его можно изменять динамически по мере изменения среды приложения.</span><span class="sxs-lookup"><span data-stu-id="31051-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="31051-105">Это позволяет пропорционально изменять размер элементов управления на панели с учетом изменений, например изменения размера родительского элемента управления или изменения длина текста в результате локализации.</span><span class="sxs-lookup"><span data-stu-id="31051-105">This gives the controls in the panel the ability to proportionally resize, so they can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
 <span data-ttu-id="31051-106">Любой элемент управления Windows Forms, включая другие экземпляры <xref:System.Windows.Forms.TableLayoutPanel>, может быть дочерним относительно элемента <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="31051-106">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.TableLayoutPanel> control, including other instances of <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="31051-107">Это позволяет создавать сложные макеты, динамически меняющиеся во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="31051-107">This allows you to construct sophisticated layouts that adapt to changes at run time.</span></span>  
  
 <span data-ttu-id="31051-108">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> может расширяться для размещения новых элементов управления при их добавлении в зависимости от значений свойств <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> и <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="31051-108">The <xref:System.Windows.Forms.TableLayoutPanel> control can expand to accommodate new controls when they are added, depending on the value of the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A>, <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A>, and <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle%2A> properties.</span></span> <span data-ttu-id="31051-109">Значение 0 свойства <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> или <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> указывает на то, что элемент <xref:System.Windows.Forms.TableLayoutPanel> не будет ограничиваться в соответствующем направлении.</span><span class="sxs-lookup"><span data-stu-id="31051-109">Setting either the <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> or <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> property to a value of 0 specifies that the <xref:System.Windows.Forms.TableLayoutPanel> will be unbound in the corresponding direction.</span></span>  
  
 <span data-ttu-id="31051-110">Также можно управлять направлением расширения элемента управления <xref:System.Windows.Forms.TableLayoutPanel> (горизонтальное или вертикальное) после его заполнения дочерними элементами управления.</span><span class="sxs-lookup"><span data-stu-id="31051-110">You can also control the direction of expansion (horizontal or vertical) after the <xref:System.Windows.Forms.TableLayoutPanel> control is full of child controls.</span></span> <span data-ttu-id="31051-111">По умолчанию элемент управления <xref:System.Windows.Forms.TableLayoutPanel> развертывается вниз путем добавления строк.</span><span class="sxs-lookup"><span data-stu-id="31051-111">By default, the <xref:System.Windows.Forms.TableLayoutPanel> control expands downward by adding rows.</span></span>  
  
 <span data-ttu-id="31051-112">Если необходимо изменить поведение строк и столбцов, заданное по умолчанию, используйте свойства <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> и <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="31051-112">If you want rows and columns that behave differently from the default behavior, you can control the properties of rows and columns by using the <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> and <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> properties.</span></span> <span data-ttu-id="31051-113">Свойства строк и столбцов можно задавать по отдельности.</span><span class="sxs-lookup"><span data-stu-id="31051-113">You can set the properties of rows or columns individually.</span></span>  
  
 <span data-ttu-id="31051-114">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> добавляет следующие свойства в свои дочерние элементы управления: `Cell`, `Column`, `Row`, `ColumnSpan` и `RowSpan`.</span><span class="sxs-lookup"><span data-stu-id="31051-114">The <xref:System.Windows.Forms.TableLayoutPanel> control adds the following properties to its child controls: `Cell`, `Column`, `Row`, `ColumnSpan`, and `RowSpan`.</span></span>  
  
 <span data-ttu-id="31051-115">Чтобы объединить ячейки в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>, установите свойство `ColumnSpan` или `RowSpan` дочернего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="31051-115">You can merge cells in the <xref:System.Windows.Forms.TableLayoutPanel> control by setting the `ColumnSpan` or `RowSpan` properties on a child control.</span></span>  
  
1. [<span data-ttu-id="31051-116">Практическое руководство. Выравнивание и Растягивание элемента управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-116">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="31051-117">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-117">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="31051-118">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-118">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="31051-119">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-119">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="see-also"></a><span data-ttu-id="31051-120">См. также</span><span class="sxs-lookup"><span data-stu-id="31051-120">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutSettings>
- [<span data-ttu-id="31051-121">Практическое руководство. Разработка макета формы Windows, с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="31051-121">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="31051-122">Практическое руководство. Создание переменного размера Windows формы для ввода данных</span><span class="sxs-lookup"><span data-stu-id="31051-122">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)
- [<span data-ttu-id="31051-123">Советы по использованию элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="31051-123">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)
