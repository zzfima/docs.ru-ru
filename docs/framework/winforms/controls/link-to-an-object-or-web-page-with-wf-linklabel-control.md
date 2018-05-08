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
ms.openlocfilehash: 9957eae7e15c99ec259574b435402420c6bcf5f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms
Windows Forms <xref:System.Windows.Forms.LinkLabel> управления позволяет создавать веб-ссылок в форме. При щелчке ссылки, можно изменить его цвет, чтобы указать, что она была открыта. Дополнительные сведения об изменении цвета см. в разделе [как: изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## <a name="linking-to-another-form"></a>Связывание с другой формой  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Для связи с другой формой с помощью элемента управления LinkLabel  
  
1.  Задать <xref:System.Windows.Forms.LinkLabel.Text%2A> свойства соответствующий заголовок.  
  
2.  Задать <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойства, чтобы определить, какая часть заголовка будет представлена в качестве ссылки. Как указывается зависит от свойств внешнего метки ссылки. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Значение которого представлено параметром <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> объект, содержащий два числа, начальной позицией знака и количество символов. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Свойство можно задать в окне «Свойства» или в коде аналогично следующему:  
  
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
  
3.  В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчик событий вызова <xref:System.Windows.Forms.Form.Show%2A> метод, чтобы открыть другую форму в проекте и задать <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства `true`.  
  
    > [!NOTE]
    >  Экземпляр <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> несет ссылку на класс <xref:System.Windows.Forms.LinkLabel> управления, которая была нажата, поэтому нет необходимости для приведения `sender` объекта.  
  
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
  
## <a name="linking-to-a-web-page"></a>Связывание с веб-страницы  
 <xref:System.Windows.Forms.LinkLabel> Элемент управления может также использоваться для отображения веб-страницы с помощью браузера по умолчанию.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Чтобы запустить Internet Explorer и ссылку на веб-страницу с помощью элемента управления LinkLabel  
  
1.  Задать <xref:System.Windows.Forms.LinkLabel.Text%2A> свойства соответствующий заголовок.  
  
2.  Задать <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойства, чтобы определить, какая часть заголовка будет представлена в качестве ссылки.  
  
3.  В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчика событий блок обработки исключений, вызовите вторую процедуру, которая задает <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства `true` и использует <xref:System.Diagnostics.Process.Start%2A> метод, чтобы запустить браузер по умолчанию с URL-адреса. Для использования <xref:System.Diagnostics.Process.Start%2A> необходимо добавить ссылку на метод <xref:System.Diagnostics?displayProperty=nameWithType> пространства имен.  
  
    > [!IMPORTANT]
    >  Если приведенный ниже код выполняется в среде с частичным доверием (например, на общем диске), JIT-компилятор происходит отказ при `VisitLink` вызывается метод. `System.Diagnostics.Process.Start` Инструкция вызывает требование связывания, завершаются с ошибкой. Перехват исключения при `VisitLink` вызывается метод, приведенный ниже код гарантирует, что при сбое JIT-компилятором, ошибка будет постепенно обработана.  
  
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
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>  
 [Общие сведения об элементе управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)  
 [Элемент управления LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
