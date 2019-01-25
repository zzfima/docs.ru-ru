---
title: Как выполнить Создание в Windows Forms кнопки отмены
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 74d025677682735fc7f1c68116b2364887f0519c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701473"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Как выполнить Создание в Windows Forms кнопки отмены
В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления кнопки "Отмена". Каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, что другой элемент управления в форме имеет фокус, нажатии кнопки "Отмена". Такая кнопка обычно создается, чтобы пользователи могли быстро прервать операцию, не выполняя никаких действий.  
  
### <a name="to-designate-the-cancel-button"></a>Чтобы создать кнопку «Отмена»  
  
1.  Формы задайте <xref:System.Windows.Forms.Form.CancelButton%2A> свойство в соответствующий <xref:System.Windows.Forms.Button> элемента управления.  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Ответ на нажатие кнопки Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание кнопки принятия Windows Forms](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
