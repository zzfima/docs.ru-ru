---
title: "Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки"
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
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81716be53468242734c3d722eb21e020e58f65ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
Можно задать <xref:System.Windows.Forms.ToolTip> строки в коде или в конструкторе Windows Forms. Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компонента, в разделе [Общие сведения о компоненте ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-a-tooltip-programmatically"></a>Задание всплывающей подсказки программным способом  
  
1.  Добавьте элемент управления, который будет отображаться всплывающая подсказка.  
  
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
  
2.  Выберите элемент управления, который будет отображаться всплывающая подсказка, или добавьте его в форму.  
  
3.  В **свойства** задайте **ToolTip on ToolTip1** значение соответствующую строку текста.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [Компонент ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
