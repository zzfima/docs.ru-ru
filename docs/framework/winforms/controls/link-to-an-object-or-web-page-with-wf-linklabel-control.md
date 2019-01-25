---
title: Как выполнить Ссылка на объект или веб-страницей с помощью элемента управления LinkLabel в Windows Forms
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
ms.openlocfilehash: fd397f9a6462ad9da06b1cc258a51b3cccf5d21c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628452"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="db8f5-102">Как выполнить Ссылка на объект или веб-страницей с помощью элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db8f5-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="db8f5-103">Windows Forms <xref:System.Windows.Forms.LinkLabel> управления позволяет создавать веб-ссылок в форме.</span><span class="sxs-lookup"><span data-stu-id="db8f5-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="db8f5-104">При щелчке ссылки, можно изменить его цвет, чтобы указать, что связь была посещена.</span><span class="sxs-lookup"><span data-stu-id="db8f5-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="db8f5-105">Дополнительные сведения об изменении цвета см. в разделе [как: Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span><span class="sxs-lookup"><span data-stu-id="db8f5-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>  
  
## <a name="linking-to-another-form"></a><span data-ttu-id="db8f5-106">Связывание с другой формой</span><span class="sxs-lookup"><span data-stu-id="db8f5-106">Linking to Another Form</span></span>  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="db8f5-107">Для связи с другой формой с помощью элемента управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="db8f5-107">To link to another form with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="db8f5-108">Задайте <xref:System.Windows.Forms.LinkLabel.Text%2A> свойство соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="db8f5-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="db8f5-109">Задать <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойства, чтобы определить, какая часть заголовка будет представлена в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="db8f5-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="db8f5-110">Как это указано зависит от свойств внешний вид метки ссылки.</span><span class="sxs-lookup"><span data-stu-id="db8f5-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="db8f5-111"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Значение представлено <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> объект, содержащий два числа, положение начального знака и число символов.</span><span class="sxs-lookup"><span data-stu-id="db8f5-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="db8f5-112"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Свойство можно задать в окне «Свойства» или в коде способом, аналогичным следующему:</span><span class="sxs-lookup"><span data-stu-id="db8f5-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>  
  
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
  
3.  <span data-ttu-id="db8f5-113">В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчик событий вызова <xref:System.Windows.Forms.Form.Show%2A> метод, чтобы открыть другую форму в проекте и задать <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="db8f5-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db8f5-114">Экземпляр <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> несет ссылку на класс <xref:System.Windows.Forms.LinkLabel> нажатый элемент управления, поэтому нет необходимости приводить `sender` объекта.</span><span class="sxs-lookup"><span data-stu-id="db8f5-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>  
  
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
  
## <a name="linking-to-a-web-page"></a><span data-ttu-id="db8f5-115">Связывание с веб-страницы</span><span class="sxs-lookup"><span data-stu-id="db8f5-115">Linking to a Web Page</span></span>  
 <span data-ttu-id="db8f5-116"><xref:System.Windows.Forms.LinkLabel> Управления также может использоваться для отображения веб-страницы в браузере по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="db8f5-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="db8f5-117">Чтобы запустить Internet Explorer и ссылку на веб-страницу с элементом управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="db8f5-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="db8f5-118">Задайте <xref:System.Windows.Forms.LinkLabel.Text%2A> свойство соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="db8f5-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
2.  <span data-ttu-id="db8f5-119">Задать <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойства, чтобы определить, какая часть заголовка будет представлена в качестве ссылки.</span><span class="sxs-lookup"><span data-stu-id="db8f5-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
3.  <span data-ttu-id="db8f5-120">В <xref:System.Windows.Forms.LinkLabel.LinkClicked> обработчика событий блоке обработки исключений, вызовите вторую процедуру, которая задает <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> свойства `true` и использует <xref:System.Diagnostics.Process.Start%2A> метод, чтобы запустить браузер по умолчанию URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="db8f5-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="db8f5-121">Чтобы использовать <xref:System.Diagnostics.Process.Start%2A> необходимо добавить ссылку на метод <xref:System.Diagnostics?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="db8f5-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="db8f5-122">Если приведенный ниже код выполняется в среде с частичным доверием (например, на общем диске), JIT-компилятор происходит отказ при `VisitLink` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="db8f5-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="db8f5-123">`System.Diagnostics.Process.Start` Инструкция вызывает запрос компоновки, который не удается.</span><span class="sxs-lookup"><span data-stu-id="db8f5-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="db8f5-124">Перехват исключения при `VisitLink` вызывается метод, приведенный ниже код гарантирует, что JIT-компилятор в случае сбоя ошибки будет постепенно обработана.</span><span class="sxs-lookup"><span data-stu-id="db8f5-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="db8f5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="db8f5-125">See also</span></span>
- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="db8f5-126">Общие сведения об элементе управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="db8f5-126">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="db8f5-127">Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db8f5-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="db8f5-128">Элемент управления LinkLabel</span><span class="sxs-lookup"><span data-stu-id="db8f5-128">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
