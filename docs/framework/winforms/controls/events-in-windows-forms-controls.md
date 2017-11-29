---
title: "События элементов управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e568dd7fadea8af399a63aa95347f368b4e13a54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="events-in-windows-forms-controls"></a>События элементов управления Windows Forms
Элемент управления Windows Forms наследует более шестидесяти событий <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. К ним относятся <xref:System.Windows.Forms.Control.Paint> событие, которое вызывает в элементе управления для отображения, события, связанные с отображением окна, такие как <xref:System.Windows.Forms.Control.Resize> и <xref:System.Windows.Forms.Control.Layout> события и низкоуровневые события мыши и клавиатуры. Некоторые низкоуровневые события полученные по <xref:System.Windows.Forms.Control> в семантические события, такие как <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.DoubleClick>. Дополнительные сведения о наследуемых событиях см. в разделе <xref:System.Windows.Forms.Control>.  
  
 Если для пользовательского элемента управления требуется переопределение функциональности наследуемых событий, переопределите наследуемый метод `On` *EventName*, а не присоединяйте делегат. Если вы не знакомы с моделью событий в .NET Framework, ознакомьтесь с разделом [Инициирование событий из компонента](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
## <a name="see-also"></a>См. также  
 [Переопределение метода OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Обработка введенных пользователем данных](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Определение событий](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [События](../../../../docs/standard/events/index.md)
