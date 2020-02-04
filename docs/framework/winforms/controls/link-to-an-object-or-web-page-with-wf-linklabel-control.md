---
title: Ссылка на объект или веб-страницу с помощью элемента управления LinkLabel
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
ms.openlocfilehash: 1669a9d6aba39b02d228c735701ca4e31c8f8291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745211"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms

Элемент управления <xref:System.Windows.Forms.LinkLabel> Windows Forms позволяет создавать веб-ссылки в форме. При нажатии ссылки можно изменить ее цвет, чтобы показать, что ссылка была посещена. Дополнительные сведения об изменении цвета см. в разделе [как изменить внешний вид элемента управления LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).

## <a name="linking-to-another-form"></a>Связывание с другой формой

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>Связывание с другой формой с помощью элемента управления LinkLabel

1. Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.

2. Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка. Способ его указания зависит от свойств метки ссылки, связанных с внешним видом. Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>ным объектом, содержащим два числа: начальную точку символа и число символов. Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> можно задать в окно свойств или в коде так же, как показано ниже:

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

3. В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> вызовите метод <xref:System.Windows.Forms.Form.Show%2A>, чтобы открыть другую форму в проекте, и задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.

    > [!NOTE]
    > Экземпляр класса <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> несет ссылку на элемент управления <xref:System.Windows.Forms.LinkLabel>, который был нажат, поэтому нет необходимости приводить объект `sender`.

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

Элемент управления <xref:System.Windows.Forms.LinkLabel> может также использоваться для показа веб-страницы с помощью браузера по умолчанию.

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Запуск Internet Explorer и связывание с веб-страницей с помощью элемента управления LinkLabel

1. Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.

2. Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка.

3. В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked>, в ходе блока обработки исключений, вызовите вторую процедуру, которая задает свойству <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true` и использует метод <xref:System.Diagnostics.Process.Start%2A> для запуска браузера по умолчанию с URL-адресом. Чтобы использовать метод <xref:System.Diagnostics.Process.Start%2A>, необходимо добавить ссылку на пространство имен <xref:System.Diagnostics?displayProperty=nameWithType>.

    > [!IMPORTANT]
    > Если приведенный ниже код выполняется в среде с частичным доверием (например, на общем диске), JIT-компилятор завершается с ошибкой при вызове метода `VisitLink`. Инструкция `System.Diagnostics.Process.Start` вызывает сбой запроса ссылки. При перехвате исключения при вызове метода `VisitLink` приведенный ниже код гарантирует, что в случае сбоя JIT-компилятора ошибка будет правильно обработана.

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

## <a name="see-also"></a>См. также раздел

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [Общие сведения об элементе управления LinkLabel](linklabel-control-overview-windows-forms.md)
- [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [Элемент управления LinkLabel](linklabel-control-windows-forms.md)
