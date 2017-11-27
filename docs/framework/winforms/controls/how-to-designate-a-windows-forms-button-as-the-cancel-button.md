---
title: "Практическое руководство. Создание кнопки \"Отмена\" в Windows Forms"
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
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bbdf2ec4f2353662f1077b9d95966e0a2ebd316
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>Практическое руководство. Создание кнопки "Отмена" в Windows Forms
В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> элемента управления "Отмена". Каждый раз, когда пользователь нажимает клавишу ESC, независимо от других элементов управления в форме имеет фокус по нажатию кнопки "Отмена". Такая кнопка обычно создается, чтобы пользователь мог быстро прервать операцию, не выполняя никаких действий.  
  
### <a name="to-designate-the-cancel-button"></a>Чтобы создать кнопку «Отмена»  
  
1.  Формы задайте <xref:System.Windows.Forms.Form.CancelButton%2A> свойство к соответствующему <xref:System.Windows.Forms.Button> элемента управления.  
  
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
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Создание кнопки принятия в Windows Forms](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
