---
title: "Практическое руководство. Добавление элементов управления в формы Windows Forms."
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
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d9075c93181b68828a307924259a9170c046baa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-controls-to-windows-forms"></a>Практическое руководство. Добавление элементов управления в формы Windows Forms.
Большинство форм разрабатываются путем добавления элементов управления в область формы для создания пользовательского интерфейса (UI). Объект *управления* — это компонент на форме, использующийся для отображения сведений или ввода пользователя. Дополнительные сведения об элементах управления см. в разделе [элементов управления Windows Forms](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-draw-a-control-on-a-form"></a>Чтобы нарисовать элемент управления на форме  
  
1.  Откройте форму. Дополнительные сведения см. в разделе [как: отображение Windows Forms в конструкторе](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  В **элементов**, щелкните элемент управления, который требуется добавить в форму.  
  
3.  В форме щелкните место верхнего левого угла элемента управления располагаться и перетащите место нижнего правого угла элемента управления располагаться.  
  
     Элемент управления добавляется в форму с заданным расположением и размером.  
  
    > [!NOTE]
    >  Каждый элемент управления имеет определенный размер по умолчанию. Можно добавить элемент управления в форму по умолчанию размер элемента управления, перетащив его из **элементов** в форму.  
  
### <a name="to-drag-a-control-to-a-form"></a>Чтобы перетащить элемент управления в форму  
  
1.  Откройте форму. Дополнительные сведения см. в разделе [как: отображение Windows Forms в конструкторе](http://msdn.microsoft.com/en-us/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  В **элементов**, щелкните и перетащите его в форму элемент управления.  
  
     Элемент управления добавляется в форму в указанном месте с размером по умолчанию.  
  
    > [!NOTE]
    >  Можно дважды щелкнуть элемент управления в **элементов** Чтобы добавить его в левом верхнем углу формы с размером по умолчанию.  
  
     Вы можно добавить элементы управления динамически в форму во время выполнения. В следующем примере кода <xref:System.Windows.Forms.TextBox> управления будет добавлен в форму при <xref:System.Windows.Forms.Button> нажатии элемента управления.  
  
    > [!NOTE]
    >  Следующая процедура требуется наличие формы с **кнопку** управления `Button1`, уже расположенным в ней.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Добавление в форму элемента управления программными средствами  
  
1.  В метод, обрабатывающий кнопки `Click` события в классе формы, вставьте код, аналогичный приведенному ниже, чтобы добавить ссылку на переменную элемента управления, задайте в качестве `Location`и добавить элемент управления.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  Кроме того, можно добавить код для инициализации другие свойства элемента управления.  
  
    > [!IMPORTANT]
    >  Может предоставлять локального компьютера под угрозу безопасность по сети с помощью ссылки на злонамеренный `UserControl`. Это произойдет только в случае злонамеренный пользователь создаст небезопасный элемент управления, а затем по ошибке добавит его в проект.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Практическое руководство. Изменение размера элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
