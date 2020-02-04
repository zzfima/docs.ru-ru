---
title: Пошаговое руководство. выполнение операции перетаскивания
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746789"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Пример. Выполнение операции перетаскивания в Windows Forms
Для выполнения операций перетаскивания в приложениях на основе Windows необходимо выполнить обработку ряда событий, особенно в <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>и <xref:System.Windows.Forms.Control.DragDrop> событий. Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.  
  
## <a name="dragging-data"></a>Перетаскивание данных  
 Все операции перетаскивания начинаются с переноса данных. Функция, позволяющая собирать данные при начале перетаскивания, реализуется в методе <xref:System.Windows.Forms.Control.DoDragDrop%2A>.  
  
 В следующем примере событие <xref:System.Windows.Forms.Control.MouseDown> используется для запуска операции перетаскивания, поскольку оно является наиболее интуитивно понятным (большинство действий по перетаскиванию начинается с нажатия кнопки мыши). Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.  
  
> [!NOTE]
> Некоторые элементы управления имеют собственные события перетаскивания. Например, для элементов управления <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView> есть событие <xref:System.Windows.Forms.TreeView.ItemDrag>.  
  
#### <a name="to-start-a-drag-operation"></a>Начало операции перетаскивания  
  
1. В событии <xref:System.Windows.Forms.Control.MouseDown> для элемента управления, в котором начнется перетаскивание, используйте метод `DoDragDrop`, чтобы задать перетаскиваемые данные и разрешить перетаскивание разрешенных эффектов. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     В следующем примере показан запуск операции перетаскивания. Элемент управления, в котором начинается перетаскивание, является элементом управления <xref:System.Windows.Forms.Button>, перетаскиваемые данные — это строка, представляющая свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button>, а допустимые эффекты — копирование или перемещение.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > Любые данные можно использовать в качестве параметра в методе `DoDragDrop`; в приведенном выше примере использовалось свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> (вместо того, чтобы жестко кодировать значение или извлечь данные из набора данных), так как свойство было связано с расположением, которое перетаскивается из (элемент управления <xref:System.Windows.Forms.Button>). Учитывайте это при реализации операций перетаскивания в приложениях Windows.  
  
 Пока действует операция перетаскивания, можно выполнить обработку события <xref:System.Windows.Forms.Control.QueryContinueDrag>, которое "запрашивает разрешение", чтобы продолжить операцию перетаскивания. При обработке этого метода также можно вызвать методы, которые влияют на операцию перетаскивания, например, расширение <xref:System.Windows.Forms.TreeNode> в элементе управления <xref:System.Windows.Forms.TreeView>, когда курсор наведен на него.  
  
## <a name="dropping-data"></a>Завершение перетаскивания данных  
 После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить. При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится. Любую область внутри формы или элемента управления Windows можно сделать для приема пропущенных данных, задав свойство <xref:System.Windows.Forms.Control.AllowDrop%2A> и обрабатывая события <xref:System.Windows.Forms.Control.DragEnter> и <xref:System.Windows.Forms.Control.DragDrop>.  
  
#### <a name="to-perform-a-drop"></a>Завершение операции перетаскивания  
  
1. Присвойте свойству <xref:System.Windows.Forms.Control.AllowDrop%2A> значение true.  
  
2. В событии `DragEnter` для элемента управления, в котором будет выполняться перетаскивание, убедитесь, что перетаскиваемые данные имеют допустимый тип (в данном случае <xref:System.Windows.Forms.Control.Text%2A>). Затем код задает результат, который будет выполняться при выполнении перетаскивания в значение в перечислении <xref:System.Windows.Forms.DragDropEffects>. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > Вы можете определить собственный <xref:System.Windows.Forms.DataFormats>, указав собственный объект в качестве параметра <xref:System.Object> метода <xref:System.Windows.Forms.DataObject.SetData%2A>. При этом необходимо убедиться, что указанный объект является сериализуемым. Дополнительные сведения см. в разделе <xref:System.Runtime.Serialization.ISerializable>.  
  
3. В событии <xref:System.Windows.Forms.Control.DragDrop> для элемента управления, в котором будет выполняться перетаскивание, используйте метод <xref:System.Windows.Forms.DataObject.GetData%2A> для получения перетаскиваемых данных. Дополнительные сведения см. в разделе <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     В приведенном ниже примере элемент управления <xref:System.Windows.Forms.TextBox> — это элемент управления, к которому выполняется перетаскивание (где произойдет перетаскивание). Этот код задает <xref:System.Windows.Forms.Control.Text%2A> свойство элемента управления <xref:System.Windows.Forms.TextBox>, равное перетаскиваемых данным.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > Кроме того, можно работать со свойством <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>, чтобы в зависимости от нажатых клавиш во время операции перетаскивания были выполнены определенные эффекты (например, при нажатии клавиши CTRL в стандартном режиме копируется перетаскивание данных).  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Добавление данных в буфер обмена](how-to-add-data-to-the-clipboard.md)
- [Практическое руководство. Извлечение данных из буфера обмена](how-to-retrieve-data-from-the-clipboard.md)
- [Операции перетаскивания и поддержка буфера обмена](drag-and-drop-operations-and-clipboard-support.md)
