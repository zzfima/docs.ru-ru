---
title: "Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2567a564b5769abd91d34696c1a94c21ad2913ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="4f2f2-102">Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f2f2-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="4f2f2-103">Можно использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления, чтобы разрешить пользователям часто отображение документа, прежде чем он станет для печати.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="4f2f2-104">Чтобы сделать это, необходимо указать экземпляр <xref:System.Drawing.Printing.PrintDocument> класса; это документ для печати.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="4f2f2-105">Дополнительные сведения об использовании предварительного просмотра с <xref:System.Drawing.Printing.PrintDocument> компонента, в разделе [как: печать в Windows Forms с помощью предварительный](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="4f2f2-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f2f2-106">Для использования <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления во время выполнения пользователи должны иметь установленный на своем компьютере, локально или через сеть, принтер, как это отчасти как <xref:System.Windows.Forms.PrintPreviewDialog> компонент определяет, как будет выглядеть при печати документа.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="4f2f2-107"><xref:System.Windows.Forms.PrintPreviewDialog> Управления использует <xref:System.Drawing.Printing.PrinterSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="4f2f2-108">Кроме того <xref:System.Windows.Forms.PrintPreviewDialog> управления использует <xref:System.Drawing.Printing.PageSettings> класса, так же как и <xref:System.Windows.Forms.PrintPreviewDialog> компонент.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="4f2f2-109">Печать документа, указанного в <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> взаимодействует с экземплярами обоих <xref:System.Drawing.Printing.PrinterSettings> и <xref:System.Drawing.Printing.PageSettings> классов и они используются для отображения документа в окне предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="4f2f2-110">Просмотр страниц с помощью элемента управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4f2f2-110">To view pages using the PrintPreviewDialog control</span></span>  
  
-   <span data-ttu-id="4f2f2-111">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="4f2f2-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="4f2f2-112">В следующем примере кода <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> обработчик событий открывает экземпляр <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="4f2f2-113">Печать документа указывается в <xref:System.Windows.Forms.PrintDialog.Document%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="4f2f2-114">В следующем примере указано ни одного печати документа.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="4f2f2-115">В этом примере предполагается, что имеет форму <xref:System.Windows.Forms.Button> управления <xref:System.Drawing.Printing.PrintDocument> компонент с именем `myDocument`и <xref:System.Windows.Forms.PrintPreviewDialog> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="4f2f2-116">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4f2f2-116">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4f2f2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4f2f2-117">See Also</span></span>  
 [<span data-ttu-id="4f2f2-118">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="4f2f2-118">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [<span data-ttu-id="4f2f2-119">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="4f2f2-119">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="4f2f2-120">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f2f2-120">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="4f2f2-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f2f2-121">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
