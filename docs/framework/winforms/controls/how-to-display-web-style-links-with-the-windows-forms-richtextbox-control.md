---
title: Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b82a5251cb5e1f632d126105cfae5cf2b8f62fc0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="8247d-102">Практическое руководство. Отображение ссылок веб-типа с помощью элемента управления RichTextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8247d-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="8247d-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> элемент управления может отображать веб-ссылки цветом и подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="8247d-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="8247d-104">Можно написать код, который открывает окно браузера веб-сайт, указанный в тексте ссылки, при щелчке ссылки.</span><span class="sxs-lookup"><span data-stu-id="8247d-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="8247d-105">Чтобы связать веб-страницей с помощью элемента управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8247d-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="8247d-106">Задать <xref:System.Windows.Forms.RichTextBox.Text%2A> свойства в строку, содержащую допустимый URL-адрес (например, «http://www.microsoft.com/»).</span><span class="sxs-lookup"><span data-stu-id="8247d-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="8247d-107">Убедитесь, что <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> свойству `true` (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8247d-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="8247d-108">Создать новый глобальный экземпляр класса <xref:System.Diagnostics.Process> объекта.</span><span class="sxs-lookup"><span data-stu-id="8247d-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="8247d-109">Написать обработчик событий для <xref:System.Windows.Forms.RichTextBox.LinkClicked> событие, которое передает браузер нужный текст.</span><span class="sxs-lookup"><span data-stu-id="8247d-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="8247d-110">В следующем примере <xref:System.Windows.Forms.RichTextBox.LinkClicked> событий открывает экземпляр из Internet Explorer для URL-адрес, указанный в <xref:System.Windows.Forms.RichTextBox.Text%2A> свойства <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8247d-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="8247d-111">В этом примере предполагается наличие формы с <xref:System.Windows.Forms.RichTextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8247d-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="8247d-112">В вызывающем <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> метода, вы столкнетесь с <xref:System.Security.SecurityException> исключение, если код выполняется в контексте частичного доверия из-за недостатка прав.</span><span class="sxs-lookup"><span data-stu-id="8247d-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="8247d-113">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="8247d-113">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="8247d-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Необходимо инициализировать процесс `p`, это можно сделать, включив в конструктор формы следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="8247d-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="8247d-115">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="8247d-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="8247d-116">Важно, чтобы немедленно остановить процесс, созданный после завершения работы с ним.</span><span class="sxs-lookup"><span data-stu-id="8247d-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="8247d-117">Код, чтобы остановить процесс обращения к коду, представленные выше, может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8247d-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8247d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8247d-118">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="8247d-119">Элемент управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8247d-119">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="8247d-120">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8247d-120">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
