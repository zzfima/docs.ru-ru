---
title: Отображение веб-ссылок с помощью элемента управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 78a07a250744018f121b03f2973b1661ed6bf764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745529"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms

Элемент управления Windows Forms <xref:System.Windows.Forms.RichTextBox> может отображать веб-ссылки как цветные и подчеркнутые. Можно написать код, открывающий окно браузера, в котором отображается веб-сайт, указанный в тексте ссылки при щелчке ссылки.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>Ссылка на веб-страницу с помощью элемента управления RichTextBox

1. Задайте для свойства <xref:System.Windows.Forms.RichTextBox.Text%2A> строку, содержащую допустимый URL-адрес (например, "http://www.microsoft.com/").

2. Убедитесь, что для свойства <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> задано значение `true` (по умолчанию).

3. Создайте новый глобальный экземпляр объекта <xref:System.Diagnostics.Process>.

4. Напишите обработчик событий для <xref:System.Windows.Forms.RichTextBox.LinkClicked> события, которое отправляет браузеру нужный текст.

    В приведенном ниже примере событие <xref:System.Windows.Forms.RichTextBox.LinkClicked> открывает экземпляр Internet Explorer по URL-адресу, указанному в свойстве <xref:System.Windows.Forms.RichTextBox.Text%2A> элемента управления <xref:System.Windows.Forms.RichTextBox>. В этом примере предполагается, что форма имеет элемент управления <xref:System.Windows.Forms.RichTextBox>.

    > [!IMPORTANT]
    > При вызове метода <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> возникает исключение <xref:System.Security.SecurityException>, если код выполняется в контексте частичного доверия из-за недостаточных привилегий. Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../misc/code-access-security-basics.md).

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    (Визуальный C++элемент) Необходимо инициализировать процесс `p`, который можно сделать, включив в конструктор формы следующую инструкцию:

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    (Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    Важно немедленно завершить процесс, созданный после завершения работы с ним. При указании кода, приведенного выше, код для завершения процесса может выглядеть следующим образом:

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [Элемент управления RichTextBox](richtextbox-control-windows-forms.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
