---
title: Оптимизация производительности элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 97bf6f36ce029f879c3524fa92df08a483c2cb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536986"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="22d73-102">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="22d73-103">При работе с большими объемами данных, `DataGridView` элемент управления может использовать большой объем памяти, если не используется внимательно.</span><span class="sxs-lookup"><span data-stu-id="22d73-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="22d73-104">На клиентских компьютерах с ограниченным объемом памяти некоторые из этих затрат можно избежать, чтобы избежать возможностей, которые имеют требовательных к памяти.</span><span class="sxs-lookup"><span data-stu-id="22d73-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="22d73-105">Можно также управлять некоторые или все данные обслуживания и извлечения задач вручную с помощью виртуального режима для настройки использования памяти для вашего сценария.</span><span class="sxs-lookup"><span data-stu-id="22d73-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22d73-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="22d73-106">In This Section</span></span>  
 [<span data-ttu-id="22d73-107">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="22d73-108">Описывает использование `DataGridView` управления способом, чтобы избежать ненужных памяти использования и снижения производительности при работе с большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="22d73-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="22d73-109">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="22d73-110">Описывает, как использовать виртуальный режим дополнить или заменить стандартный механизм привязки данных.</span><span class="sxs-lookup"><span data-stu-id="22d73-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="22d73-111">Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="22d73-112">Описывает, как реализовать обработчики для нескольких событий в виртуальном режиме.</span><span class="sxs-lookup"><span data-stu-id="22d73-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="22d73-113">Также показано, как реализовать отката на уровне строк и фиксация пользовательские изменения.</span><span class="sxs-lookup"><span data-stu-id="22d73-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="22d73-114">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="22d73-115">Описание способа загрузки данных по требованию, что полезно при наличии дополнительных данных для отображения, чем может уместиться в памяти для клиента.</span><span class="sxs-lookup"><span data-stu-id="22d73-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="22d73-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="22d73-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="22d73-117">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="22d73-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="22d73-118">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="22d73-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d73-119">См. также</span><span class="sxs-lookup"><span data-stu-id="22d73-119">See Also</span></span>  
 [<span data-ttu-id="22d73-120">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="22d73-120">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="22d73-121">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d73-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
