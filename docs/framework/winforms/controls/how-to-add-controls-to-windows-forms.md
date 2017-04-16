---
title: "Практическое руководство. Добавление элементов управления в формы Windows Forms. | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], добавление"
  - "элементы управления Windows Forms, добавление в форму"
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Добавление элементов управления в формы Windows Forms.
Большинство форм разрабатываются путем добавления элементов управления на поверхность формы с целью создания пользовательского интерфейса.  *Элемент управления* — это компонент на форме, использующийся для отображения сведений или ввода пользовательских данных.  Дополнительные сведения об элементах управления см. в разделе [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы нарисовать элемент управления в форме, выполните следующие действия.  
  
1.  Откройте форму.  Дополнительные сведения см. в разделе [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ru-ru/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  В **панели элементов** щелкните элемент управления, который требуется добавить в форму.  
  
3.  Щелкните место в форме, где должен располагаться левый верхний угол элемента управления, а затем перетащите указатель мыши на место, в котором должен располагаться правый нижний угол элемента управления.  
  
     Элемент управления добавляется на форму в указанное место с указанными размерами.  
  
    > [!NOTE]
    >  Для каждого элемента управления существует размер, определенный по умолчанию.  На форму можно добавить элемент управления, который будет иметь размер по умолчанию. Для этого требуется перетащить элемент управления из **панели элементов** на форму.  
  
### Чтобы перетащить элемент управления в форму, выполните следующие действия.  
  
1.  Откройте форму.  Дополнительные сведения см. в разделе [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ru-ru/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  В **панели элементов** щелкните требуемый элемент управления и перетащите его в форму.  
  
     Элемент добавляется в форму в указанное место с размером по умолчанию.  
  
    > [!NOTE]
    >  Чтобы добавить элемент управления с размером по умолчанию в верхний левый угол формы, щелкните его два раза в **панели элементов**.  
  
     Можно также добавлять элементы управления на форму динамически во время выполнения.  В приведенном ниже примере элемент управления <xref:System.Windows.Forms.TextBox> будет добавлен на форму после щелчка элемента управления <xref:System.Windows.Forms.Button>.  
  
    > [!NOTE]
    >  Для следующей процедуры требуется форма с уже расположенным в ней элементом управления **Кнопка** `Button1`.  
  
### Чтобы добавить элемент управления в форму с помощью программных средств, выполните следующие действия.  
  
1.  В метод, который обрабатывает событие `Click` кнопки в классе формы, вставьте код, идентичный приведенному ниже, чтобы добавить ссылку на переменную элемента управления, задать свойство `Location` элемента управления и добавить сам элемент управления.  
  
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
    >  Можно также добавить код для инициализации остальных свойств элемента управления.  
  
    > [!IMPORTANT]
    >  Ссылка на `UserControl`, созданный злонамеренным пользователем, может сделать систему безопасности локального компьютера уязвимой из сети.  Это произойдет только в том случае, если злонамеренный пользователь создаст разрушающий пользовательский элемент управления, а разработчик по ошибке добавит его в проект.  
  
## См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Расположение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Практическое руководство. Изменение размера элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)   
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)