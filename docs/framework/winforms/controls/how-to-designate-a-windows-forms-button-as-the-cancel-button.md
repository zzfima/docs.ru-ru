---
title: Назначить кнопку кнопкой "Отмена"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743258"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Практическое руководство. Создание кнопки "Отмена" в Windows Forms
В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button> в качестве кнопки отмены. Нажатие кнопки «отмена» происходит каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, какой элемент управления формы имеет фокус. Такая кнопка обычно запрограммирована, позволяя пользователю быстро выйти из операции без фиксации каких-либо действий.  
  
### <a name="to-designate-the-cancel-button"></a>Назначение кнопки «Отмена»  
  
1. Задайте для свойства <xref:System.Windows.Forms.Form.CancelButton%2A> формы соответствующий элемент управления <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание кнопки принятия в Windows Forms](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Элемент управления Button](button-control-windows-forms.md)
