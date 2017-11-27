---
title: "Общие сведения об элементе управления Panel (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62adba598f59b4662bfb4c51b868bad1aa2e53b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="panel-control-overview-windows-forms"></a>Общие сведения об элементе управления Panel (Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> элементы управления используются для предоставления возможность группировки других элементов управления. Как правило панели используются для разделения формы по функциям. Например имеется формой заказа, указаны параметры доставки почты ночное для использования. Объединение всех параметров на панели предоставляет пользователю логическую визуальную подсказку. В режиме разработки все элементы управления можно легко переместить — при перемещении <xref:System.Windows.Forms.Panel> управления, все содержащиеся в нем элементы перемещаются также. Элементы управления, сгруппированные на панели можно получить с помощью его <xref:System.Windows.Forms.Control.Controls%2A> свойство. Это свойство возвращает коллекцию <xref:System.Windows.Forms.Control> получить экземпляры, поэтому обычно необходимо привести элемент управления таким образом, чтобы его определенного типа.  
  
## <a name="panel-versus-groupbox"></a>Панель и GroupBox  
 <xref:System.Windows.Forms.Panel> Управления аналогичен <xref:System.Windows.Forms.GroupBox> управления; Однако только <xref:System.Windows.Forms.Panel> управления можно использовать полосы прокрутки и только <xref:System.Windows.Forms.GroupBox> управления отображается заголовок.  
  
## <a name="key-properties"></a>Основные свойства  
 Для отображения полос прокрутки, задайте <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> свойства `true`. Также можно настроить внешний вид панели с помощью <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, и <xref:System.Windows.Forms.Panel.BorderStyle%2A> свойства. Дополнительные сведения о <xref:System.Windows.Forms.Control.BackColor%2A> и <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойствах см. [как: Установка фона панели](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md). <xref:System.Windows.Forms.Panel.BorderStyle%2A> Свойство определяет, если описанные без видимой границы панели (<xref:System.Windows.Forms.BorderStyle.None>), простой линии (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), или затемненных строки (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Panel>  
 [Элемент управления GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [Практическое руководство. Группирование элементов управления с элементом управления Panel в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
