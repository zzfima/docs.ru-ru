---
title: Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 87ad4c957ac5b99438684d398a0c5ad7d126c406
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925043"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения
Распространенные задачи при разработке приложений — это добавление элементов управления и удаление элементов управления из любого контейнера в формах (например <xref:System.Windows.Forms.Panel> , или <xref:System.Windows.Forms.GroupBox> , или даже самой формы). Во время разработки элементы управления можно перетаскивать непосредственно на панель или в группу. Во время выполнения эти элементы управления поддерживают коллекцию `Controls`, которая отслеживает размещенные в них элементы управления.  
  
> [!NOTE]
> Следующий пример кода применяется к любому элементу управления, который поддерживает внутри себя коллекцию элементов управления.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Программное добавление элемента управления в коллекцию  
  
1. Создайте экземпляр элемента управления, подлежащий добавлению.  
  
2. Задайте свойства нового элемента управления.  
  
3. Добавьте этот элемент управления в коллекцию `Controls` родительского элемента управления.  
  
     В следующем примере кода показано, как создать экземпляр <xref:System.Windows.Forms.Button> элемента управления. Для этого требуется форма с <xref:System.Windows.Forms.Panel> элементом управления и метод обработки событий для `NewPanelButton_Click`создаваемой кнопки, уже существует.  
  
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
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a>Программное удаление элементов управления из коллекции  
  
1. Удалите обработчик событий из события. В Visual Basic используйте ключевое слово [оператора RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md) . в C#используйте [оператор-=](../../../csharp/language-reference/operators/subtraction-operator.md).  
  
2. Используйте метод `Remove` для удаления требуемого элемента управления из коллекции `Controls` панели.  
  
3. Вызовите <xref:System.Windows.Forms.Control.Dispose%2A> метод, чтобы освободить все ресурсы, используемые элементом управления.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Panel>
- [Элемент управления Panel](panel-control-windows-forms.md)
