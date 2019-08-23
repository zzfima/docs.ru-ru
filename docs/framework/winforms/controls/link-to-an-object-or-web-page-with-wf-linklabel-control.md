---
title: Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 1ed27826b92d34f05055ab7fdda2a16eb4a79b17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952178"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms
Элемент управления <xref:System.Windows.Forms.LinkLabel> Windows Forms позволяет создавать веб-ссылки в форме. При нажатии ссылки можно изменить ее цвет, чтобы показать, что ссылка была посещена. Дополнительные сведения об изменении цвета см. в разделе [как Изменение внешнего вида Windows Forms элемента управления](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)LinkLabel.  
  
## <a name="linking-to-another-form"></a>Связывание с другой формой  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Связывание с другой формой с помощью элемента управления LinkLabel  
  
1. Задайте для <xref:System.Windows.Forms.LinkLabel.Text%2A> свойства соответствующий заголовок.  
  
2. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Задайте свойство, чтобы определить, какая часть заголовка будет указана как ссылка. Способ его указания зависит от свойств метки ссылки, связанных с внешним видом. Значение представлено <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> объектом, содержащим два числа, начальную и символьную позиции. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Свойство можно задать в окно свойств или в коде следующим образом:  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3. В обработчике <xref:System.Windows.Forms.Form.Show%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`событий вызовите метод, чтобы открыть другую форму в проекте, и присвойте свойству значение. <xref:System.Windows.Forms.LinkLabel.LinkClicked>  
  
    > [!NOTE]
    > Экземпляр <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> класса несет ссылку <xref:System.Windows.Forms.LinkLabel> на элемент управления, который был нажат, поэтому `sender` нет необходимости приводить объект.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a>Связывание с веб-страницей  
 <xref:System.Windows.Forms.LinkLabel> Элемент управления также может использоваться для показа веб-страницы с помощью браузера по умолчанию.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Запуск Internet Explorer и связывание с веб-страницей с помощью элемента управления LinkLabel  
  
1. Задайте для <xref:System.Windows.Forms.LinkLabel.Text%2A> свойства соответствующий заголовок.  
  
2. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Задайте свойство, чтобы определить, какая часть заголовка будет указана как ссылка.  
  
3. В обработчике <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true` <xref:System.Diagnostics.Process.Start%2A> событий в процессе блока обработки исключений вызовите вторую процедуру, которая задает свойству значение и использует метод для запуска браузера по умолчанию с URL-адресом. <xref:System.Windows.Forms.LinkLabel.LinkClicked> Чтобы использовать <xref:System.Diagnostics.Process.Start%2A> метод, необходимо добавить ссылку <xref:System.Diagnostics?displayProperty=nameWithType> на пространство имен.  
  
    > [!IMPORTANT]
    >  Если приведенный ниже код выполняется в среде с частичным доверием (например, на общем диске), JIT-компилятор завершается с `VisitLink` ошибкой при вызове метода. `System.Diagnostics.Process.Start` Инструкция вызывает сбой запроса компоновки. При перехвате исключения при `VisitLink` вызове метода приведенный ниже код гарантирует, что в случае сбоя JIT-компилятора ошибка будет правильно обработана.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [Общие сведения об элементе управления LinkLabel](linklabel-control-overview-windows-forms.md)
- [Практическое руководство. Изменение внешнего вида Windows Forms элемента управления LinkLabel](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [Элемент управления LinkLabel](linklabel-control-windows-forms.md)
