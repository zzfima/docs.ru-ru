---
title: "Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8506df062729a98adc1aa1e0dcb524aa4ec812c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms
Существует несколько значений задержек, которые можно задать для Windows Forms <xref:System.Windows.Forms.ToolTip> компонента. Единицы измерения для этих свойств — миллисекунд. <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Свойство определяет, как долго пользователь должен указывать на элементом управления, чтобы появилась строка ToolTip. <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Свойство задает время в миллисекундах, затрачиваемое строки ToolTip отображаться при перемещении мыши с одного элемента управления связанный всплывающей подсказки в другую. <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Свойство определяет время строки всплывающей подсказки. Эти значения можно задать по отдельности или установив значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойство; другие свойства задаются с учетом на значение, присваиваемое задержка <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойство. Например, если <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> присваивается значение N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> равно N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> присвоено значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> деленное на пять (или N-5), и <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> присвоено значение, которое является пять раз значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойства (5N).  
  
### <a name="to-set-the-delay"></a>Чтобы задать значение задержки  
  
1.  Задайте следующие свойства, как показано в следующем примере.  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
