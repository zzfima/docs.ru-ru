---
title: Практическое руководство. Создание кнопки принятия Windows Forms
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
ms.openlocfilehash: 00d9f4acffb88b5047b40df91799cea1caaf2cf2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714701"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Практическое руководство. Создание кнопки принятия Windows Forms
В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления "Принять", также известный как кнопка по умолчанию. Каждый раз, когда пользователь нажимает клавишу ВВОД, нажатии кнопки по умолчанию, независимо от того, что другой элемент управления в форме имеет фокус.  
  
> [!NOTE]
>  Исключение составляют случаи, когда элемент управления с фокусом является еще одну кнопку — в этом случае будет нажата кнопка с фокусом, или многострочного текстового окна, или пользовательский элемент управления, который перехватывает клавишу ВВОД.  
  
### <a name="to-designate-the-accept-button"></a>Чтобы создать кнопку «принять»  
  
1.  Формы задайте <xref:System.Windows.Forms.Form.AcceptButton%2A> свойство в соответствующий <xref:System.Windows.Forms.Button> элемента управления.  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Общие сведения об элементе управления Button](button-control-overview-windows-forms.md)
- [Способы активации элемента управления Button в Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Практическое руководство. Ответ на нажатие кнопки Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Создание в Windows Forms кнопки отмены](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Элемент управления Button](button-control-windows-forms.md)
