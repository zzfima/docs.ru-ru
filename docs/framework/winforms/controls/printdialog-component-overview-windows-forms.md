---
title: Общие сведения о компоненте PrintDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 982c52dbe9243e69bbb0452513e78798f4d1fd0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072445"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="95d44-102">Общие сведения о компоненте PrintDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="95d44-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="95d44-103">Windows Forms [PrintDialog](printdialog-component-windows-forms.md) компонент является стандартным диалоговым окном, используемый для выбора принтера, печатаемых страниц и определения других параметров печати в приложениях на базе Windows.</span><span class="sxs-lookup"><span data-stu-id="95d44-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="95d44-104">Он используется в качестве простого решения для выбора принтера и параметров печати вместо самостоятельной настройки диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="95d44-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="95d44-105">Вы можете включить пользователям возможность распечатывать многие части своих документов: печать всех, указанного диапазона страниц или выделенного фрагмента текста.</span><span class="sxs-lookup"><span data-stu-id="95d44-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="95d44-106">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="95d44-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="95d44-107"><xref:System.Windows.Forms.PrintDialog> Компонент наследуется от <xref:System.Windows.Forms.CommonDialog> класса.</span><span class="sxs-lookup"><span data-stu-id="95d44-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="95d44-108">Работа с компонентом</span><span class="sxs-lookup"><span data-stu-id="95d44-108">Working with the Component</span></span>  
 <span data-ttu-id="95d44-109">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="95d44-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="95d44-110">Этот компонент имеет свойства, которые относятся к либо одного задания печати (<xref:System.Drawing.Printing.PrintDocument> класс) или параметры отдельных принтера (<xref:System.Drawing.Printing.PrinterSettings> класса).</span><span class="sxs-lookup"><span data-stu-id="95d44-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="95d44-111">Любой из них, в свою очередь, могут совместно использоваться несколько принтеров.</span><span class="sxs-lookup"><span data-stu-id="95d44-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="95d44-112">При добавлении в форму, <xref:System.Windows.Forms.PrintDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="95d44-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d44-113">См. также</span><span class="sxs-lookup"><span data-stu-id="95d44-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="95d44-114">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="95d44-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
