---
title: Реагирование на нажатия кнопок
ms.date: 03/30/2017
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
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735713"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Практическое руководство. Обработка события нажатия кнопки в Windows Forms
Наиболее базовым использованием элемента управления Windows Forms <xref:System.Windows.Forms.Button> является выполнение некоторого кода при нажатии кнопки.  
  
 При щелчке элемента управления <xref:System.Windows.Forms.Button> также создается ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>и события <xref:System.Windows.Forms.Control.MouseUp>. Если вы планируете присоединить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют. Например, если нажать кнопку, чтобы очистить сведения, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображаться всплывающая подсказка с несуществующими сведениями.  
  
 Если пользователь пытается дважды щелкнуть элемент управления <xref:System.Windows.Forms.Button>, каждый щелчок будет обрабатываться отдельно. то есть элемент управления не поддерживает событие двойного щелчка.  
  
### <a name="to-respond-to-a-button-click"></a>Реагирование на нажатие кнопки  
  
- В `Click` кнопки <xref:System.EventHandler> записать код для выполнения. `Button1_Click` должны быть привязаны к элементу управления. Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Элемент управления Button](button-control-windows-forms.md)
