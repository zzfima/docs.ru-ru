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
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="c128c-102">Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c128c-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="c128c-103">Элемент управления <xref:System.Windows.Forms.LinkLabel> Windows Forms позволяет создавать веб-ссылки в форме.</span><span class="sxs-lookup"><span data-stu-id="c128c-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="c128c-104">При нажатии ссылки можно изменить ее цвет, чтобы показать, что ссылка была посещена.</span><span class="sxs-lookup"><span data-stu-id="c128c-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="c128c-105">Дополнительные сведения об изменении цвета см. в разделе [как изменить внешний вид элемента управления LinkLabel Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="c128c-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="c128c-106">Связывание с другой формой</span><span class="sxs-lookup"><span data-stu-id="c128c-106">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="c128c-107">Связывание с другой формой с помощью элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="c128c-107">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="c128c-108">Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="c128c-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="c128c-109">Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка.</span><span class="sxs-lookup"><span data-stu-id="c128c-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="c128c-110">Способ его указания зависит от свойств метки ссылки, связанных с внешним видом.</span><span class="sxs-lookup"><span data-stu-id="c128c-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="c128c-111">Значение <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> представлено <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>ным объектом, содержащим два числа: начальную точку символа и число символов.</span><span class="sxs-lookup"><span data-stu-id="c128c-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="c128c-112">Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> можно задать в окно свойств или в коде так же, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="c128c-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

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

3. <span data-ttu-id="c128c-113">В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked> вызовите метод <xref:System.Windows.Forms.Form.Show%2A>, чтобы открыть другую форму в проекте, и задайте для свойства <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="c128c-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c128c-114">Экземпляр класса <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> несет ссылку на элемент управления <xref:System.Windows.Forms.LinkLabel>, который был нажат, поэтому нет необходимости приводить объект `sender`.</span><span class="sxs-lookup"><span data-stu-id="c128c-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

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

## <a name="linking-to-a-web-page"></a><span data-ttu-id="c128c-115">Связывание с веб-страницей</span><span class="sxs-lookup"><span data-stu-id="c128c-115">Linking to a Web Page</span></span>

<span data-ttu-id="c128c-116">Элемент управления <xref:System.Windows.Forms.LinkLabel> может также использоваться для показа веб-страницы с помощью браузера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c128c-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="c128c-117">Запуск Internet Explorer и связывание с веб-страницей с помощью элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="c128c-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="c128c-118">Задайте для свойства <xref:System.Windows.Forms.LinkLabel.Text%2A> соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="c128c-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="c128c-119">Задайте свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, чтобы определить, какая часть заголовка будет указана как ссылка.</span><span class="sxs-lookup"><span data-stu-id="c128c-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="c128c-120">В обработчике событий <xref:System.Windows.Forms.LinkLabel.LinkClicked>, в ходе блока обработки исключений, вызовите вторую процедуру, которая задает свойству <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> значение `true` и использует метод <xref:System.Diagnostics.Process.Start%2A> для запуска браузера по умолчанию с URL-адресом.</span><span class="sxs-lookup"><span data-stu-id="c128c-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="c128c-121">Чтобы использовать метод <xref:System.Diagnostics.Process.Start%2A>, необходимо добавить ссылку на пространство имен <xref:System.Diagnostics?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c128c-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c128c-122">Если приведенный ниже код выполняется в среде с частичным доверием (например, на общем диске), JIT-компилятор завершается с ошибкой при вызове метода `VisitLink`.</span><span class="sxs-lookup"><span data-stu-id="c128c-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="c128c-123">Инструкция `System.Diagnostics.Process.Start` вызывает сбой запроса ссылки.</span><span class="sxs-lookup"><span data-stu-id="c128c-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="c128c-124">При перехвате исключения при вызове метода `VisitLink` приведенный ниже код гарантирует, что в случае сбоя JIT-компилятора ошибка будет правильно обработана.</span><span class="sxs-lookup"><span data-stu-id="c128c-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c128c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c128c-125">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c128c-126">Общие сведения об элементе управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="c128c-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="c128c-127">Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c128c-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="c128c-128">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="c128c-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
