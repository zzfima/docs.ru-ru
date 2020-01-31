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
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Оптимизация производительности элемента управления DataGridView в Windows Forms
При работе с большими объемами данных элемент управления `DataGridView` может использовать большой объем памяти, если он не используется осторожно. На клиентах с ограниченным объемом памяти можно избежать некоторых из этих издержек, избегая использования функций с высокими затратами на память. Вы также можете самостоятельно управлять некоторыми или всеми задачами по обслуживанию и извлечению данных с помощью виртуального режима, чтобы настроить использование памяти для сценария.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Масштабирование элемента управления DataGridView в Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Описывает использование элемента управления `DataGridView` способом, который позволяет избежать ненужного использования памяти и снижения производительности при работе с большими объемами данных.  
  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Описывает, как использовать виртуальный режим для дополнения или замены стандартного механизма привязки данных.  
  
 [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)  
 Описывает, как реализовать обработчики для нескольких событий виртуального режима. Также демонстрируется, как реализовать откат и фиксацию на уровне строк для пользовательских изменений.  
  
 [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Описывает, как загружать данные по требованию, что полезно при наличии большего объема данных, чем может храниться доступная память клиента.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Содержит справочную документацию по свойству <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## <a name="see-also"></a>См. также:

- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
- [Режимы отображения данных в элементе управления DataGridView в Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
