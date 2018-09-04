---
title: Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 7f698a517fbf72ceafde4a117b4d92dd9d352834
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43540566"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
Можно задать <xref:System.Windows.Forms.ToolTip> строку в коде или в конструкторе Windows Forms. Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компонента, см. в разделе [Общие сведения о компоненте ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Чтобы задать подсказку программным способом  
  
1.  Добавьте элемент управления, который будет отображаться объект ToolTip.  
  
2.  Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a>Для задания подсказки в конструкторе  
  
1.  Добавьте в форму компонент <xref:System.Windows.Forms.ToolTip>.  
  
2.  Выберите элемент управления, который будет отображаться объект ToolTip, или добавьте его в форму.  
  
3.  В **свойства** окне **во всплывающей подсказке над ToolTip1** значение соответствующую строку текста.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
