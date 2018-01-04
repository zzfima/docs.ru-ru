---
title: "Практическое руководство. Отображение компонента PrintDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d955febe528add4b774766a3b204f96eef5a119d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="a332c-102">Практическое руководство. Отображение компонента PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a332c-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="a332c-103"><xref:System.Windows.Forms.PrintDialog> Компонент является стандартной Windows диалоговое окно печати, многие ваши пользователи будут знакомы с.</span><span class="sxs-lookup"><span data-stu-id="a332c-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="a332c-104">Поскольку пользователям будет удобно работать с ней, он может оказаться эффективным для использования <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="a332c-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="a332c-105">Отображение компонента PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a332c-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="a332c-106">Вызовите <xref:System.Windows.Forms.Form.ShowDialog%2A> метода в код приложения.</span><span class="sxs-lookup"><span data-stu-id="a332c-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="a332c-107">После отображения этого компонента пользователи смогут взаимодействовать с ним, задавая свойства задания печати.</span><span class="sxs-lookup"><span data-stu-id="a332c-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="a332c-108">Они сохраняются в <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` класса (и <xref:System.Drawing.Printing.PageSettings> класса, если пользователь обращается к [компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) через <xref:System.Windows.Forms.PrintDialog> компонента) связанный с этим заданием печати.</span><span class="sxs-lookup"><span data-stu-id="a332c-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="a332c-109">Затем можно вызывать заданные пользователями свойства для определения специфики задания печати.</span><span class="sxs-lookup"><span data-stu-id="a332c-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a332c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a332c-110">See Also</span></span>  
 [<span data-ttu-id="a332c-111">Практическое руководство. Создание стандартных заданий печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a332c-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="a332c-112">Практическое руководство. Захват данных, введенных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a332c-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="a332c-113">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="a332c-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="a332c-114">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="a332c-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [<span data-ttu-id="a332c-115">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a332c-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="a332c-116">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a332c-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
