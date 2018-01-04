---
title: "Оптимизация производительности элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Оптимизация производительности элемента управления DataGridView в Windows Forms
При работе с большими объемами данных, `DataGridView` элемент управления может использовать большой объем памяти, если не используется внимательно. На клиентских компьютерах с ограниченным объемом памяти некоторые из этих затрат можно избежать, чтобы избежать возможностей, которые имеют требовательных к памяти. Можно также управлять некоторые или все данные обслуживания и извлечения задач вручную с помощью виртуального режима для настройки использования памяти для вашего сценария.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Описывает использование `DataGridView` управления способом, чтобы избежать ненужных памяти использования и снижения производительности при работе с большими объемами данных.  
  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Описывает, как использовать виртуальный режим дополнить или заменить стандартный механизм привязки данных.  
  
 [Пошаговое руководство. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Описывает, как реализовать обработчики для нескольких событий в виртуальном режиме. Также показано, как реализовать отката на уровне строк и фиксация пользовательские изменения.  
  
 [Реализация виртуального режима с JIT-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Описание способа загрузки данных по требованию, что полезно при наличии дополнительных данных для отображения, чем может уместиться в памяти для клиента.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> свойство.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
