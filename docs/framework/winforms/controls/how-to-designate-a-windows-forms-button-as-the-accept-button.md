---
title: Обозначите кнопку как кнопку «Принять»
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142151"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Практическое руководство. Назначение кнопок принятия в Windows Forms
В любой форме Windows <xref:System.Windows.Forms.Button> можно назначить элемент управления как кнопку «принять», также известную как кнопка «По умолчанию». Всякий раз, когда пользователь нажимает на ключ ENTER, кнопка по умолчанию нажимается независимо от того, какой другой элемент управления в форме имеет фокус.  
  
> [!NOTE]
> Исключением является, когда управление с фокусом является еще одной кнопкой - в этом случае, кнопка с фокусом будет нажата - или многолинейный текстовый ящик, или пользовательский контроль, который ловушки enter ключ.  
  
### <a name="to-designate-the-accept-button"></a>Обозначить кнопку «Принять»  
  
1. Установите свойство <xref:System.Windows.Forms.Form.AcceptButton%2A> формы на <xref:System.Windows.Forms.Button> соответствующий контроль.  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание кнопки "Отмена" в Windows Forms](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Элемент управления Button](button-control-windows-forms.md)
