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
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929008"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="9d0e6-102">Практическое руководство. Предварительный просмотр при печати в приложениях Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d0e6-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="9d0e6-103"><xref:System.Windows.Forms.PrintPreviewDialog> Элемент управления можно использовать для предоставления пользователям возможности отображать документ, часто перед его печатью.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="9d0e6-104">Для этого необходимо указать экземпляр <xref:System.Drawing.Printing.PrintDocument> класса; это документ для печати.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="9d0e6-105">Дополнительные сведения об использовании предварительного просмотра с <xref:System.Drawing.Printing.PrintDocument> компонентом см. в разделе как [ Печать в Windows Forms с помощью предварительного](../advanced/how-to-print-in-windows-forms-using-print-preview.md)просмотра.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d0e6-106">Чтобы использовать <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления во время выполнения, на компьютере пользователя должен быть установлен принтер (локально или через сеть), поскольку он частично определяет, <xref:System.Windows.Forms.PrintPreviewDialog> как именно этот документ будет выглядеть при печати.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="9d0e6-107"><xref:System.Windows.Forms.PrintPreviewDialog> Элемент управления<xref:System.Drawing.Printing.PrinterSettings> использует класс.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="9d0e6-108">Кроме того, <xref:System.Windows.Forms.PrintPreviewDialog> элемент управления <xref:System.Drawing.Printing.PageSettings> использует класс так же, как <xref:System.Windows.Forms.PrintPreviewDialog> и компонент.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="9d0e6-109">Документ <xref:System.Windows.Forms.PrintPreviewDialog> печати, указанный в <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> свойстве элемента управления, относится <xref:System.Drawing.Printing.PrinterSettings> к экземплярам классов и <xref:System.Drawing.Printing.PageSettings> и используется для отрисовки документа в окне предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="9d0e6-110">Просмотр страниц с помощью элемента управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="9d0e6-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="9d0e6-111">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="9d0e6-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="9d0e6-112">В следующем примере <xref:System.Windows.Forms.Button> кода обработчик <xref:System.Windows.Forms.Control.Click> событий элемента управления <xref:System.Windows.Forms.PrintPreviewDialog> открывает экземпляр элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="9d0e6-113">Документ печати задается в <xref:System.Windows.Forms.PrintDialog.Document%2A> свойстве.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="9d0e6-114">В приведенном ниже примере не указан документ Print.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="9d0e6-115">В примере требуется <xref:System.Windows.Forms.Button> , чтобы форма соработала элемент управления <xref:System.Drawing.Printing.PrintDocument> , <xref:System.Windows.Forms.PrintPreviewDialog> компонент `myDocument`с именем и элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="9d0e6-116">(Визуальный C#элемент C++, визуальный элемент) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="9d0e6-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9d0e6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9d0e6-117">See also</span></span>

- [<span data-ttu-id="9d0e6-118">Компонент PrintDocument</span><span class="sxs-lookup"><span data-stu-id="9d0e6-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="9d0e6-119">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="9d0e6-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="9d0e6-120">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d0e6-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="9d0e6-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9d0e6-121">Windows Forms</span></span>](../index.md)
