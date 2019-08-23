---
title: Практическое руководство. Отключение кнопок в кнопочном столбе элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], disabling buttons
- buttons [Windows Forms], disabling in button columns
- DataGridView control [Windows Forms], disabling button cells
ms.assetid: 5c344d01-013a-4a6b-8f8d-62ec9321d81e
ms.openlocfilehash: b8bb503186e41c682b0685e4c9c4bf0bb3adcbe8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967385"
---
# <a name="how-to-disable-buttons-in-a-button-column-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="ced91-102">Практическое руководство. Отключение кнопок в кнопочном столбе элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ced91-102">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ced91-103">Элемент управления <xref:System.Windows.Forms.DataGridView> включает класс <xref:System.Windows.Forms.DataGridViewButtonCell> для отображения ячеек с пользовательским интерфейсом, похожим на кнопку.</span><span class="sxs-lookup"><span data-stu-id="ced91-103">The <xref:System.Windows.Forms.DataGridView> control includes the <xref:System.Windows.Forms.DataGridViewButtonCell> class for displaying cells with a user interface (UI) like a button.</span></span> <span data-ttu-id="ced91-104">Однако элемент управления <xref:System.Windows.Forms.DataGridViewButtonCell> не дает возможности отключить показ кнопки в ячейке.</span><span class="sxs-lookup"><span data-stu-id="ced91-104">However, <xref:System.Windows.Forms.DataGridViewButtonCell> does not provide a way to disable the appearance of the button displayed by the cell.</span></span>  
  
 <span data-ttu-id="ced91-105">В примере кода ниже показано, как настроить класс <xref:System.Windows.Forms.DataGridViewButtonCell> для отображения кнопок, которые выглядят как отключенные.</span><span class="sxs-lookup"><span data-stu-id="ced91-105">The following code example demonstrates how to customize the <xref:System.Windows.Forms.DataGridViewButtonCell> class to display buttons that can appear disabled.</span></span> <span data-ttu-id="ced91-106">В этом примере определен новый тип ячейки, `DataGridViewDisableButtonCell`, производный от <xref:System.Windows.Forms.DataGridViewButtonCell>.</span><span class="sxs-lookup"><span data-stu-id="ced91-106">The example defines a new cell type, `DataGridViewDisableButtonCell`, that derives from <xref:System.Windows.Forms.DataGridViewButtonCell>.</span></span> <span data-ttu-id="ced91-107">Этот тип предоставляет новое свойство `Enabled`, которому можно присвоить значение `false` для отрисовки отключенной кнопки в ячейке.</span><span class="sxs-lookup"><span data-stu-id="ced91-107">This cell type provides a new `Enabled` property that can be set to `false` to draw a disabled button in the cell.</span></span> <span data-ttu-id="ced91-108">В этом примере также определен новый тип столбца, `DataGridViewDisableButtonColumn`, в котором отображаются объекты `DataGridViewDisableButtonCell`.</span><span class="sxs-lookup"><span data-stu-id="ced91-108">The example also defines a new column type, `DataGridViewDisableButtonColumn`, that displays `DataGridViewDisableButtonCell` objects.</span></span> <span data-ttu-id="ced91-109">Для демонстрации этих новых типов ячеек и столбцов текущее значение каждого объекта <xref:System.Windows.Forms.DataGridViewCheckBoxCell> в родительском элементе <xref:System.Windows.Forms.DataGridView> определяет значение свойства `Enabled` элемента `DataGridViewDisableButtonCell` в одной и той же строке: `true` или `false`.</span><span class="sxs-lookup"><span data-stu-id="ced91-109">To demonstrate this new cell and column type, the current value of each <xref:System.Windows.Forms.DataGridViewCheckBoxCell> in the parent <xref:System.Windows.Forms.DataGridView> determines whether the `Enabled` property of the `DataGridViewDisableButtonCell` in the same row is `true` or `false`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ced91-110">При наследовании от класса <xref:System.Windows.Forms.DataGridViewCell> или <xref:System.Windows.Forms.DataGridViewColumn> и добавлении новых свойств к производному классу необходимо переопределить метод `Clone`, чтобы скопировать новые свойства во время операций копирования.</span><span class="sxs-lookup"><span data-stu-id="ced91-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="ced91-111">Кроме того, необходимо вызвать метод `Clone` базового класса, чтобы свойства базового класса скопировались в новую ячейку или столбец.</span><span class="sxs-lookup"><span data-stu-id="ced91-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced91-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ced91-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.DisabledButtons#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DisabledButtons/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ced91-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ced91-113">Compiling the Code</span></span>  
 <span data-ttu-id="ced91-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="ced91-114">This example requires:</span></span>  
  
- <span data-ttu-id="ced91-115">ссылки на сборки System, System.Drawing, System.Windows.Forms и System.Windows.Forms.VisualStyles.</span><span class="sxs-lookup"><span data-stu-id="ced91-115">References to the System, System.Drawing, System.Windows.Forms and System.Windows.Forms.VisualStyles assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced91-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ced91-116">See also</span></span>

- [<span data-ttu-id="ced91-117">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ced91-117">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ced91-118">Архитектура элементов управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="ced91-118">DataGridView Control Architecture</span></span>](datagridview-control-architecture-windows-forms.md)
- [<span data-ttu-id="ced91-119">Типы столбцов элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ced91-119">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
