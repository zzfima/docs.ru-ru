---
title: "Практическое руководство. Обработка события нажатия кнопки в Windows Forms"
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
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28b0467c8b589882fe5afd7e884d0de55d8ca564
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Практическое руководство. Обработка события нажатия кнопки в Windows Forms
Чаще всего в Windows Forms <xref:System.Windows.Forms.Button> элемент управления должен выполнять определенный код, при нажатии кнопки.  
  
 Щелкнув <xref:System.Windows.Forms.Button> управления также создает ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, и <xref:System.Windows.Forms.Control.MouseUp> события. Если вы собираетесь добавить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют. Например если нажатие кнопки удаляет данные, данные, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображать подсказки с несуществующими сведениями.  
  
 Если пользователь пытается дважды щелкните <xref:System.Windows.Forms.Button> элемента управления, каждый щелчок будет обрабатываться отдельно; то есть элемент управления не поддерживает событие двойного щелчка.  
  
### <a name="to-respond-to-a-button-click"></a>Ответ на нажатие кнопки  
  
-   На кнопке панели `Click` <xref:System.EventHandler> написать код для выполнения. `Button1_Click`должен быть привязан к элементу управления. Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
