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
Большинство форм разрабатываются путем добавления элементов управления в область формы для создания пользовательского интерфейса (UI). *Элемент управления* — это компонент на форме, использующийся для отображения сведений или ввода данных пользователем. Дополнительные сведения об элементах управления см. в разделе [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-draw-a-control-on-a-form"></a>Чтобы нарисовать элемент управления на форме  
  
1.  Откройте форму. Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](https://msdn.microsoft.com/ru-ru/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  На **панели элементов**, нажмите элемент управления, который требуется добавить на форму.  
  
3.  В области формы нажмите на место желаемого положения верхнего левого угла элемента и перетащите указатель к месту желаемого положения нижнего правого угла элемента.  
  
     Элемент управления будет добавлен на форму с заданным расположением и размером.  
  
    > [!NOTE]
    >  Каждый элемент управления имеет определенный размер по умолчанию. Можно добавить элемент управления на форму с его размером по умолчанию, перетащив его из **панели элементов** на форму.  
  
### <a name="to-drag-a-control-to-a-form"></a>Чтобы перетащить элемент управления на форму  
  
1.  Откройте форму. Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](https://msdn.microsoft.com/ru-ru/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2. На **панели элементов** нажмите на элемент управления и перетащите его на форму.  
  
     Элемент управления будет добавлен на форму в указанном месте с размером по умолчанию.  
  
    > [!NOTE]
    >  Можно дважды щелкнуть элемент управления на **нанели элементов**, чтобы добавить его в левом верхнем углу формы с размером по умолчанию.  
  
     Вы можете добавить элементы управления на форму динамически во время выполнения. В следующем примере кода элемент управления  <xref:System.Windows.Forms.TextBox> будет добавлен на форму при нажатии элемента управления <xref:System.Windows.Forms.Button>.  
  
    > [!NOTE]
    > Следующая процедура требует наличия формы с уже расположенным на ней элементом управления **button** — `Button1`.  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a>Добавление в форму элемента управления программными средствами  
  
1.  В метод, обрабатывающий событие `Click` кнопки в классе формы, вставьте код, аналогичный приведенному ниже, чтобы создать ссылку на переменную элемента управления, установить его свойство `Location` и добавить элемент управления на форму.  
  
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
    >  Кроме того, можно добавить код для инициализации других свойств элемента управления.  
  
    > [!IMPORTANT]
    > Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети. Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Практическое руководство. Изменение размера элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
