---
title: Оптимизация производительности элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 79f74db4ebd095156207a6218f59c0e9ae423085
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076598"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="66aa4-102">Оптимизация производительности элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="66aa4-103">При работе с большими объемами данных, `DataGridView` управления можно будет использовать большой объем памяти, если использовать осторожно.</span><span class="sxs-lookup"><span data-stu-id="66aa4-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="66aa4-104">На клиентах с ограниченным объемом памяти некоторые из этих затрат можно избежать за счет отключения функций, имеющих требовательных к памяти.</span><span class="sxs-lookup"><span data-stu-id="66aa4-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="66aa4-105">Вы также можете управлять, некоторые или все данные обслуживания и извлечения задач вручную с помощью виртуального режима для настройки использования памяти для вашего сценария.</span><span class="sxs-lookup"><span data-stu-id="66aa4-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66aa4-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="66aa4-106">In This Section</span></span>  
 [<span data-ttu-id="66aa4-107">Масштабирование элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="66aa4-108">Описывает использование `DataGridView` управления способом, который позволяет избежать ненужных памяти использования и снижения производительности при работе с большими объемами данных.</span><span class="sxs-lookup"><span data-stu-id="66aa4-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="66aa4-109">Виртуальный режим элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="66aa4-110">В этой статье описывается использование виртуального режима для добавления или замены стандартный механизм привязки данных.</span><span class="sxs-lookup"><span data-stu-id="66aa4-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="66aa4-111">Пошаговое руководство: Реализация виртуального режима для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="66aa4-112">В этой статье описывается реализация обработчиков для нескольких событий в виртуальном режиме.</span><span class="sxs-lookup"><span data-stu-id="66aa4-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="66aa4-113">Также показано, как реализовать отката на уровне строк и фиксации для изменения пользователем.</span><span class="sxs-lookup"><span data-stu-id="66aa4-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="66aa4-114">Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="66aa4-115">В этой статье описывается загрузка данных по требованию, что полезно при наличии дополнительных данных для отображения, чем может уместиться в памяти доступных клиентских.</span><span class="sxs-lookup"><span data-stu-id="66aa4-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="66aa4-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="66aa4-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="66aa4-117">Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="66aa4-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="66aa4-118">Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="66aa4-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66aa4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="66aa4-119">See also</span></span>

- [<span data-ttu-id="66aa4-120">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="66aa4-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="66aa4-121">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66aa4-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
