---
title: Настройка производительности в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744276"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="dd4f0-102">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dd4f0-103">При работе с большими объемами данных элемент управления `DataGridView` может использовать большой объем памяти, если он не используется осторожно.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="dd4f0-104">На клиентах с ограниченным объемом памяти можно избежать некоторых из этих издержек, избегая использования функций с высокими затратами на память.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="dd4f0-105">Вы также можете самостоятельно управлять некоторыми или всеми задачами по обслуживанию и извлечению данных с помощью виртуального режима, чтобы настроить использование памяти для сценария.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd4f0-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="dd4f0-106">In This Section</span></span>  
 [<span data-ttu-id="dd4f0-107">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd4f0-108">Описывает использование элемента управления `DataGridView` способом, который позволяет избежать ненужного использования памяти и снижения производительности при работе с большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="dd4f0-109">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd4f0-110">Описывает, как использовать виртуальный режим для дополнения или замены стандартного механизма привязки данных.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="dd4f0-111">Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="dd4f0-112">Описывает, как реализовать обработчики для нескольких событий виртуального режима.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="dd4f0-113">Также демонстрируется, как реализовать откат и фиксацию на уровне строк для пользовательских изменений.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="dd4f0-114">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="dd4f0-115">Описывает, как загружать данные по требованию, что полезно при наличии большего объема данных, чем может храниться доступная память клиента.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dd4f0-116">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="dd4f0-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="dd4f0-117">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="dd4f0-118">Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="dd4f0-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd4f0-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="dd4f0-119">See also</span></span>

- [<span data-ttu-id="dd4f0-120">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="dd4f0-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="dd4f0-121">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd4f0-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
