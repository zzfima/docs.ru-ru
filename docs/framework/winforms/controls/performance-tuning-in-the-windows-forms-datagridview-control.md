---
title: "Оптимизация производительности элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView - элемент управления [Windows Forms], настройка производительности"
  - "настройка производительности, таблицы данных"
  - "производительность, DataGridView - элемент управления"
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Оптимизация производительности элемента управления DataGridView в Windows Forms
При работе с большими объемами данных элемент управления `DataGridView` может потреблять значительное количество памяти, если не принять особых мер.  На клиентах с ограниченным размером памяти этих издержек можно избежать путем отключения требовательных к памяти функций.  Настройка использования памяти для конкретного случая может также осуществляться путем управления некоторыми или всеми задачами поддержания и извлечения данных в виртуальном режиме.  
  
## В этом подразделе  
 [Масштабирование элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Описание способов использования элемента управления `DataGridView`, позволяющих избежать избыточного потребления памяти и снижения производительности при работе с большими объемами данных.  
  
 [Виртуальный режим элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Описание использования виртуального режима, позволяющего дополнить или заменить стандартный механизм привязки данных.  
  
 [Пример. Реализация виртуального режима для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Описание способов реализации обработчиков для ряда событий виртуального режима.  Также демонстрируется способ реализации механизма отката и фиксации на уровне строк для вносимых пользователем изменений.  
  
 [Реализация виртуального режима с JIT\-загрузкой данных для элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Описание способа загрузки данных по требованию, который может быть полезен, если доступный размер памяти клиента не способен вместить всех данных, предназначенных для отображения.  
  
## Ссылка  
 <xref:System.Windows.Forms.DataGridView>  
 Справочная документация по элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Содержит справочную документацию для свойства <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## См. также  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Режимы отображения данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)