---
title: Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154366"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="7717f-102">Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7717f-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="7717f-103">Можно использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления, чтобы пользователи могли отображение документа, часто, прежде чем он станет для печати.</span><span class="sxs-lookup"><span data-stu-id="7717f-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="7717f-104">Чтобы сделать это, необходимо указать экземпляр <xref:System.Drawing.Printing.PrintDocument> класса; это документа на печать.</span><span class="sxs-lookup"><span data-stu-id="7717f-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="7717f-105">Дополнительные сведения об использовании предварительного просмотра с <xref:System.Drawing.Printing.PrintDocument> компонента, см. в разделе [как: В Windows Forms с использованием предварительного просмотра печати](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="7717f-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7717f-106">Чтобы использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления во время выполнения, пользователи должны иметь установленный на компьютере, локально или через сеть, принтер, как это отчасти как <xref:System.Windows.Forms.PrintPreviewDialog> компонент определяет, как будет выглядеть при печати документа.</span><span class="sxs-lookup"><span data-stu-id="7717f-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="7717f-107"><xref:System.Windows.Forms.PrintPreviewDialog> Управления использует <xref:System.Drawing.Printing.PrinterSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="7717f-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="7717f-108">Кроме того <xref:System.Windows.Forms.PrintPreviewDialog> управления использует <xref:System.Drawing.Printing.PageSettings> класса, так же, как <xref:System.Windows.Forms.PrintPreviewDialog> компонент.</span><span class="sxs-lookup"><span data-stu-id="7717f-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="7717f-109">Печать документа, указанного в <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> свойство ссылается на обоих экземпляров <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классы, которые используются для отображения документа в окне предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="7717f-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="7717f-110">Для просмотра страниц, используя элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="7717f-110">To view pages using the PrintPreviewDialog control</span></span>  
  
-   <span data-ttu-id="7717f-111">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="7717f-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="7717f-112">В следующем примере кода <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий открывает экземпляр <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7717f-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="7717f-113">Печать документа указывается в <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7717f-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="7717f-114">В следующем примере указывается не печать документа.</span><span class="sxs-lookup"><span data-stu-id="7717f-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="7717f-115">В этом примере предполагается, что форма содержит <xref:System.Windows.Forms.Button> управления <xref:System.Drawing.Printing.PrintDocument> компонент с именем `myDocument`и <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7717f-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="7717f-116">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="7717f-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7717f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7717f-117">See also</span></span>

- [<span data-ttu-id="7717f-118">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="7717f-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="7717f-119">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="7717f-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="7717f-120">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7717f-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="7717f-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7717f-121">Windows Forms</span></span>](../index.md)
