---
title: Общие сведения о компоненте PrintDialog
ms.date: 03/30/2017
f1_keywords:
- PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
ms.openlocfilehash: 0ed7f7a1f9770f71b75ae744a056b6943335c852
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728676"
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="b623e-102">Общие сведения о компоненте PrintDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b623e-102">PrintDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="b623e-103">Компонент Windows Forms [PrintDialog](printdialog-component-windows-forms.md) — это предварительно настроенное диалоговое окно, используемое для выбора принтера, выбора страниц для печати и определения других параметров печати в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="b623e-103">The Windows Forms [PrintDialog](printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="b623e-104">Он используется в качестве простого решения для выбора принтера и параметров печати вместо самостоятельной настройки диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="b623e-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="b623e-105">Вы можете разрешить пользователям печатать много частей документов: Печать всего, Печать выделенного диапазона страниц или Печать выделенного фрагмента.</span><span class="sxs-lookup"><span data-stu-id="b623e-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="b623e-106">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="b623e-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="b623e-107">Компонент <xref:System.Windows.Forms.PrintDialog> наследуется от класса <xref:System.Windows.Forms.CommonDialog>.</span><span class="sxs-lookup"><span data-stu-id="b623e-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-component"></a><span data-ttu-id="b623e-108">Работа с компонентом</span><span class="sxs-lookup"><span data-stu-id="b623e-108">Working with the Component</span></span>

<span data-ttu-id="b623e-109">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b623e-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="b623e-110">Этот компонент имеет свойства, относящиеся к одному заданию печати (<xref:System.Drawing.Printing.PrintDocument> класс) или параметрам отдельного принтера (класс<xref:System.Drawing.Printing.PrinterSettings>).</span><span class="sxs-lookup"><span data-stu-id="b623e-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="b623e-111">Любой из них, в свою очередь, может совместно использоваться несколькими принтерами.</span><span class="sxs-lookup"><span data-stu-id="b623e-111">Either of these, in turn, may be shared by multiple printers.</span></span>

<span data-ttu-id="b623e-112">При добавлении в форму <xref:System.Windows.Forms.PrintDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b623e-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="b623e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b623e-113">See also</span></span>

- <xref:System.Windows.Forms.PrintDialog>
- [<span data-ttu-id="b623e-114">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="b623e-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
