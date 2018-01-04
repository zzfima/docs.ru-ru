---
title: "Практическое руководство. Назначение кнопок принятия в Windows Forms"
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
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80503cd6fc2fc1c624cdd2aeb1ca3f699ffd9832
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>Практическое руководство. Назначение кнопок принятия в Windows Forms
В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления «принять», также известные как кнопка по умолчанию. Каждый раз, когда пользователь нажимает клавишу ВВОД, нажатии кнопки по умолчанию независимо от других элементов управления в форме имеет фокус.  
  
> [!NOTE]
>  Исключение составляют при другой кнопки элемента управления с фокусом — в этом случае будет нажата кнопка с фокусом, многострочное текстовое поле, или пользовательский элемент управления, который перехватывает клавишу ВВОД.  
  
### <a name="to-designate-the-accept-button"></a>Чтобы создать кнопку «принять»  
  
1.  Формы задайте <xref:System.Windows.Forms.Form.AcceptButton%2A> свойство к соответствующему <xref:System.Windows.Forms.Button> элемента управления.  
  
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
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Создание кнопки отмены в Windows Forms](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
