---
title: "Практическое руководство. Определение свойств страницы с помощью компонента PageSetupDialog"
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
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dc3603d37106c122f3e92503b37dcfc02d7fef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="f2f4e-102">Практическое руководство. Определение свойств страницы с помощью компонента PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="f2f4e-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="f2f4e-103">Компонент [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) предоставляет пользователю макет, размер бумаги и другие параметры разметки страницы для документа.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-103">The [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="f2f4e-104">Необходимо указать экземпляр класса <xref:System.Drawing.Printing.PrintDocument> — это распечатываемый документ.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="f2f4e-105">Кроме того, на компьютере пользователя должен быть установлен локальный или сетевой принтер, поскольку компонент <xref:System.Windows.Forms.PageSetupDialog> использует эти сведения, чтобы определить параметры форматирования страницы, предоставляемые пользователю.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="f2f4e-106">Важный аспект работы с компонентом <xref:System.Windows.Forms.PageSetupDialog> заключается в способе его взаимодействия с классом <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="f2f4e-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="f2f4e-107">Класс <xref:System.Drawing.Printing.PageSettings> используется для указания параметров, которые влияют на способ печати страницы, например ориентации, размера страницы и полей.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="f2f4e-108">Каждый из этих параметров представлен в виде свойства класса <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="f2f4e-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="f2f4e-109">Класс <xref:System.Windows.Forms.PageSetupDialog> изменяет значения этих свойств для заданного экземпляра класса <xref:System.Drawing.Printing.PageSettings> , который связан с документом (и представлен в виде свойства <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> ).</span><span class="sxs-lookup"><span data-stu-id="f2f4e-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="f2f4e-110">Задание свойств страницы с помощью компонента PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="f2f4e-110">To set page properties using the PageSetupDialog component</span></span>  
  
1.  <span data-ttu-id="f2f4e-111">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для отображения диалогового окна, указав используемый <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="f2f4e-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="f2f4e-112">В следующем примере обработчик событий <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> открывает экземпляр компонента <xref:System.Windows.Forms.PageSetupDialog> .</span><span class="sxs-lookup"><span data-stu-id="f2f4e-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="f2f4e-113">Существующий документ указывается в свойстве <xref:System.Windows.Forms.PageSetupDialog.Document%2A>, а его свойство <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="f2f4e-114">В этом примере предполагается, имеет форму <xref:System.Windows.Forms.Button> управления <xref:System.Drawing.Printing.PrintDocument> компонент с именем `myDocument`и <xref:System.Windows.Forms.PageSetupDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="f2f4e-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] и [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="f2f4e-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f2f4e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f4e-116">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="f2f4e-117">Практическое руководство. Создание стандартных заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f2f4e-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="f2f4e-118">Компонент PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="f2f4e-118">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
