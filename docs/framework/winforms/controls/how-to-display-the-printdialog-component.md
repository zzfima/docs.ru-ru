---
title: Отображение компонента PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941574"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="806ad-102">Отображение компонента PrintDialog</span><span class="sxs-lookup"><span data-stu-id="806ad-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="806ad-103"><xref:System.Windows.Forms.PrintDialog> Компонент является стандартным, многие ваши пользователи будут знакомы с окном диалогового окна печати Windows.</span><span class="sxs-lookup"><span data-stu-id="806ad-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="806ad-104">Так как пользователям будет удобно работать с ним, полезно было бы использовать <xref:System.Windows.Forms.PrintDialog> компонента.</span><span class="sxs-lookup"><span data-stu-id="806ad-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="806ad-105">Отображение компонента PrintDialog</span><span class="sxs-lookup"><span data-stu-id="806ad-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="806ad-106">Вызовите <xref:System.Windows.Forms.Form.ShowDialog%2A> метода в код приложения.</span><span class="sxs-lookup"><span data-stu-id="806ad-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="806ad-107">После отображения этого компонента пользователи смогут взаимодействовать с ним, задавая свойства задания печати.</span><span class="sxs-lookup"><span data-stu-id="806ad-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="806ad-108">Они сохраняются в <xref:System.Drawing.Printing.PrinterSettings> класс (и <xref:System.Drawing.Printing.PageSettings> класса, если пользователь обращается к [компонент PageSetupDialog](pagesetupdialog-component-windows-forms.md) через <xref:System.Windows.Forms.PrintDialog> компонент) связанные с этим заданием печати.</span><span class="sxs-lookup"><span data-stu-id="806ad-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="806ad-109">Затем можно вызывать заданные пользователями свойства для определения специфики задания печати.</span><span class="sxs-lookup"><span data-stu-id="806ad-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="806ad-110">См. также</span><span class="sxs-lookup"><span data-stu-id="806ad-110">See also</span></span>

- [<span data-ttu-id="806ad-111">Практическое руководство. Создание заданий печати стандартный Windows Forms</span><span class="sxs-lookup"><span data-stu-id="806ad-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="806ad-112">Практическое руководство. Захват данных пользователем в PrintDialog во время выполнения</span><span class="sxs-lookup"><span data-stu-id="806ad-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="806ad-113">Элемент управления PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="806ad-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="806ad-114">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="806ad-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="806ad-115">Поддержка печати в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="806ad-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="806ad-116">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="806ad-116">Windows Forms Controls</span></span>](index.md)