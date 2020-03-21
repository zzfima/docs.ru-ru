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
ms.openlocfilehash: 369946581847b4bdcf8bc658aeb94b14c529061c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182291"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a>Практическое руководство. Добавление или удаление элемента в коллекции элементов управления во время выполнения
Общие задачи в разработке приложений — добавление элементов управления и удаление <xref:System.Windows.Forms.Panel> <xref:System.Windows.Forms.GroupBox> элементов управления любым и снимаемым элементом управления на формах (например, элемент управления или даже сама форма). Во время разработки элементы управления можно перетаскивать непосредственно на панель или в группу. Во время выполнения эти элементы управления поддерживают коллекцию `Controls`, которая отслеживает размещенные в них элементы управления.  
  
> [!NOTE]
> Следующий пример кода применяется к любому элементу управления, который поддерживает внутри себя коллекцию элементов управления.  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a>Программное добавление элемента управления в коллекцию  
  
1. Создайте экземпляр элемента управления, подлежащий добавлению.  
  
2. Задайте свойства нового элемента управления.  
  
3. Добавьте этот элемент управления в коллекцию `Controls` родительского элемента управления.  
  
     Следующий пример кода показывает, как <xref:System.Windows.Forms.Button> создать экземпляр элемента управления. Для этого требуется <xref:System.Windows.Forms.Panel> форма с управлением и что метод `NewPanelButton_Click`обработки событий для создаваемых кнопки, уже существует.  
  
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
  
1. Удалите обработчик событий из события. В Visual Basic используйте ключевое слово [заявление Удаления;](../../../visual-basic/language-reference/statements/removehandler-statement.md) в СЗ используйте [оператор -'](../../../csharp/language-reference/operators/subtraction-operator.md).  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Panel>
- [Элемент управления Panel](panel-control-windows-forms.md)
