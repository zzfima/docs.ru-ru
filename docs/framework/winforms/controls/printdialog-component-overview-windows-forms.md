---
title: "Общие сведения о компоненте PrintDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20bbfd02c7fe8f5ca89d67e045b0edd4f2db996c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="printdialog-component-overview-windows-forms"></a><span data-ttu-id="800f5-102">Общие сведения о компоненте PrintDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="800f5-102">PrintDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="800f5-103">Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) компонент является стандартным диалоговым окном, используемый для выбора принтера, печатаемых страниц и определения других параметров печати в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="800f5-103">The Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component is a pre-configured dialog box used to select a printer, choose the pages to print, and determine other print-related settings in Windows-based applications.</span></span> <span data-ttu-id="800f5-104">Он используется в качестве простого решения для выбора принтера и параметров печати вместо самостоятельной настройки диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="800f5-104">Use it as a simple solution for printer and print-related settings selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="800f5-105">Можно разрешить пользователям печатать много частей документов: печать всех, указанного диапазона страниц или выделенного фрагмента текста.</span><span class="sxs-lookup"><span data-stu-id="800f5-105">You can enable users to print many parts of their documents: print all, print a selected page range, or print a selection.</span></span> <span data-ttu-id="800f5-106">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="800f5-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="800f5-107"><xref:System.Windows.Forms.PrintDialog> Компонент наследуется от <xref:System.Windows.Forms.CommonDialog> класса.</span><span class="sxs-lookup"><span data-stu-id="800f5-107">The <xref:System.Windows.Forms.PrintDialog> component inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-component"></a><span data-ttu-id="800f5-108">Работа с компонентом</span><span class="sxs-lookup"><span data-stu-id="800f5-108">Working with the Component</span></span>  
 <span data-ttu-id="800f5-109">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="800f5-109">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="800f5-110">Этот компонент имеет свойства, относящиеся либо заданиях (<xref:System.Drawing.Printing.PrintDocument> класс) или параметры отдельных принтера (<xref:System.Drawing.Printing.PrinterSettings> класса).</span><span class="sxs-lookup"><span data-stu-id="800f5-110">This component has properties that relate to either a single print job (<xref:System.Drawing.Printing.PrintDocument> class) or the settings of an individual printer (<xref:System.Drawing.Printing.PrinterSettings> class).</span></span> <span data-ttu-id="800f5-111">Любой из этих, в свою очередь, могут совместно использоваться несколькими принтерами.</span><span class="sxs-lookup"><span data-stu-id="800f5-111">Either of these, in turn, may be shared by multiple printers.</span></span>  
  
 <span data-ttu-id="800f5-112">При добавлении в форму, <xref:System.Windows.Forms.PrintDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="800f5-112">When it is added to a form, the <xref:System.Windows.Forms.PrintDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800f5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="800f5-113">See Also</span></span>  
 <xref:System.Windows.Forms.PrintDialog>  
 [<span data-ttu-id="800f5-114">Компонент PrintDialog</span><span class="sxs-lookup"><span data-stu-id="800f5-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
