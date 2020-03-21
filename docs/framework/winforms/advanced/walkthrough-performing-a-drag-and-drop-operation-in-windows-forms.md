---
title: 'Прохождение: Выполните операцию перетаскивания'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: b5e4bf753733cb9bd010672f40e8fbeb0cf036bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182441"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a>Пример. Выполнение операции перетаскивания в Windows Forms
Для выполнения операций перетаскивания в приложениях на базе Windows необходимо <xref:System.Windows.Forms.Control.DragEnter>обрабатывать <xref:System.Windows.Forms.Control.DragLeave>ряд <xref:System.Windows.Forms.Control.DragDrop> событий, в первую очередь , и события. Работая со сведениями, доступными через аргументы этих событий, можно значительно упростить операции перетаскивания.  
  
## <a name="dragging-data"></a>Перетаскивание данных  
 Все операции перетаскивания начинаются с переноса данных. Функциональность, позволяющая собирать данные при начале <xref:System.Windows.Forms.Control.DoDragDrop%2A> перетаскивания, реализована в методе.  
  
 В следующем примере <xref:System.Windows.Forms.Control.MouseDown> событие используется для запуска операции перетаскивания, поскольку оно является наиболее интуитивным (большинство действий перетаскивания начинаются с нажатия кнопки мыши). Однако не забывайте, что любое событие может использоваться для инициализации процедуры перетаскивания.  
  
> [!NOTE]
> Некоторые элементы управления имеют собственные события перетаскивания. Например, <xref:System.Windows.Forms.ListView> в <xref:System.Windows.Forms.TreeView> элементах <xref:System.Windows.Forms.TreeView.ItemDrag> управления есть событие.  
  
#### <a name="to-start-a-drag-operation"></a>Начало операции перетаскивания  
  
1. В <xref:System.Windows.Forms.Control.MouseDown> случае, если элемент управления начнется, `DoDragDrop` используйте метод для установки данных, которые будут перетасканы, и допустимый эффект перетаскивания будет иметь. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     В следующем примере показан запуск операции перетаскивания. Элемент управления, в котором <xref:System.Windows.Forms.Button> начинается перетащивание, является <xref:System.Windows.Forms.Control.Text%2A> элементом <xref:System.Windows.Forms.Button> управления, перетаскивание множец данных — строкой, представляющей свойство элемента управления, а допустимые эффекты — копированием или перемещением.  
  
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
    > Любые данные могут быть `DoDragDrop` использованы в качестве параметра в методе; в приведенном выше <xref:System.Windows.Forms.Control.Text%2A> примере <xref:System.Windows.Forms.Button> использовалось свойство элемента управления (а не жесткое кодирование значения или извлечение данных из <xref:System.Windows.Forms.Button> набора данных), поскольку свойство было связано с местом, перетащенным из (элементуправления). Учитывайте это при реализации операций перетаскивания в приложениях Windows.  
  
 В то время как операция перетаскивания действует, можно обрабатывать <xref:System.Windows.Forms.Control.QueryContinueDrag> событие, которое "запрашивает разрешение" системы на продолжение операции перетаскивания. При обработке этого метода, это также подходящий момент для вызова методов, которые будут <xref:System.Windows.Forms.TreeNode> иметь <xref:System.Windows.Forms.TreeView> влияние на операцию перетаскивания, такие как расширение в элементе управления, когда курсор парит над ним.  
  
## <a name="dropping-data"></a>Завершение перетаскивания данных  
 После начала перетаскивания данных из расположения в форме Windows Forms или элементе управления их требуется куда-то поместить. При попадании курсора в область формы или элемента управления, которые правильно настроены для размещения данных, вид курсора изменится. Любая область в форме или элементе управления Windows <xref:System.Windows.Forms.Control.AllowDrop%2A> может быть <xref:System.Windows.Forms.Control.DragEnter> сделана для принятия отброшенных данных путем установки свойства и обработки и <xref:System.Windows.Forms.Control.DragDrop> событий.  
  
#### <a name="to-perform-a-drop"></a>Завершение операции перетаскивания  
  
1. Установите <xref:System.Windows.Forms.Control.AllowDrop%2A> свойство на истину.  
  
2. В `DragEnter` случае элемента управления, <xref:System.Windows.Forms.Control.Text%2A>где произойдет падение, убедитесь, что перетаскиваемые данные являются приемлемым типом (в данном случае). Затем код устанавливает эффект, который произойдет, когда происходит <xref:System.Windows.Forms.DragDropEffects> падение к значению в перечислении. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
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
    > Вы можете определить <xref:System.Windows.Forms.DataFormats> свой собственный, указав свой собственный объект в <xref:System.Object> качестве параметра метода. <xref:System.Windows.Forms.DataObject.SetData%2A> При этом необходимо убедиться, что указанный объект является сериализуемым. Дополнительные сведения см. в разделе <xref:System.Runtime.Serialization.ISerializable>.  
  
3. В <xref:System.Windows.Forms.Control.DragDrop> случае элемента управления, где произойдет <xref:System.Windows.Forms.DataObject.GetData%2A> падение, используйте метод для извлечения перетаскиваемых данных. Дополнительные сведения см. в разделе <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.  
  
     В приведенном ниже <xref:System.Windows.Forms.TextBox> примере элемент управления, перетащаемый в (там, где происходит падение). Код устанавливает <xref:System.Windows.Forms.Control.Text%2A> свойство <xref:System.Windows.Forms.TextBox> элемента управления, равное перетаскиваемым данным.  
  
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
    > Кроме того, вы можете <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> работать с свойством, так что, в зависимости от ключей, подавленных во время операции перетаскивания, возникают определенные эффекты (например, обычно копирование перетащенных данных при нажатии ключа CTRL).  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Добавление данных в буфер обмена](how-to-add-data-to-the-clipboard.md)
- [Практическое руководство. Извлечение данных из буфера обмена](how-to-retrieve-data-from-the-clipboard.md)
- [Операции перетаскивания и поддержка буфера обмена](drag-and-drop-operations-and-clipboard-support.md)
