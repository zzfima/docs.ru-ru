---
title: Назначение кнопки "принять"
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743267"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Практическое руководство. Создание кнопки принятия в Windows Forms
В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button>, который будет кнопкой принять, также известный как кнопка по умолчанию. Когда пользователь нажимает клавишу ВВОД, нажата кнопка по умолчанию независимо от того, какой элемент управления формы имеет фокус.  
  
> [!NOTE]
> Исключением является то, что элемент управления с фокусом — это еще одна кнопка — в этом случае будет нажата кнопка с фокусом или многострочное текстовое поле или пользовательский элемент управления, который захватывает клавишу ВВОД.  
  
### <a name="to-designate-the-accept-button"></a>Назначение кнопки «принять»  
  
1. Задайте для свойства <xref:System.Windows.Forms.Form.AcceptButton%2A> формы соответствующий элемент управления <xref:System.Windows.Forms.Button>.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание кнопки отмены в Windows Forms](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Элемент управления Button](button-control-windows-forms.md)
