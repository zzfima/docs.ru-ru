---
title: "Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения | Microsoft Docs"
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
  - "коллекции, добавление элементов"
  - "элементы управления [Windows Forms], добавление пользовательских коллекций"
  - "элементы управления [Windows Forms], удаление пользовательских коллекций"
  - "коллекции элементов управления"
  - "время выполнения, добавление элементов управления"
  - "время выполнения, удаление элементов управления"
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения
Стандартными задачами при разработке приложения является задача добавления элементов управления в любой элемент управления контейнерами в формах и их удаление оттуда \(например, в элемент управления <xref:System.Windows.Forms.Panel> или <xref:System.Windows.Forms.GroupBox>, либо в саму форму\).  В процессе разработки можно перетащить элементы управления непосредственно в панель или в группу.  Во время выполнения эти элементы управления образуют коллекцию `Controls`, которая следит за размещаемыми элементами управления.  
  
> [!NOTE]
>  Приведенный ниже пример кода относится к любому элементу управления, который поддерживает коллекцию элементов управления.  
  
### Чтобы добавить элемент управления в коллекцию программными средствами, выполните следующие действия:  
  
1.  Создайте экземпляр элемента управления, который требуется добавить.  
  
2.  Задайте свойства нового элемента управления.  
  
3.  Добавьте элемент управления к коллекции `Controls` родительского элемента управления.  
  
     В приведенном ниже примере кода показано, как создать экземпляр элемента управления <xref:System.Windows.Forms.Button>.  Для этого необходима форма с элементом управления <xref:System.Windows.Forms.Panel> и уже существующий метод обработки события `NewPanelButton_Click` для создаваемой кнопки.  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substite the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### Чтобы удалить элементы управления из коллекции программными средствами, выполните следующие действия:  
  
1.  Из события удалите его обработчик.  В [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] используйте ключевое слово [Оператор RemoveHandler](../../../../ocs/visual-basic/language-reference/statements/removehandler-statement.md); в [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] используйте [Оператор \-\=](../Topic/-=%20Operator%20\(C%23%20Reference\)2.md).  
  
2.  Для удаления требуемого элемента управления из коллекции `Controls` панели используйте метод `Remove`.  
  
3.  Вызовите метод <xref:System.Windows.Forms.Control.Dispose%2A> для освобождения всех ресурсов, используемых элементом управления.  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.Panel>   
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)