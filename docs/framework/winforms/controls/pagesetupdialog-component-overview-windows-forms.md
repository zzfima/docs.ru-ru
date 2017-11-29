---
title: "Общие сведения о компоненте PageSetupDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 082dbff66c8a0f06635936011f802c99b88e41df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="4d25d-102">Общие сведения о компоненте PageSetupDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4d25d-102">PageSetupDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="4d25d-103">Windows Forms <xref:System.Windows.Forms.PageSetupDialog> компонент является предварительно настроенным диалоговым окном, используемым для задания сведений о странице для печати в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="4d25d-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="4d25d-104">Он используется в приложении Windows в качестве простого решения для задания параметров настройки страницы вместо настройки собственного диалогового.</span><span class="sxs-lookup"><span data-stu-id="4d25d-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="4d25d-105">Можно разрешить пользователям задавать границ и полей, верхние и нижние колонтитулы и книжной и альбомной ориентации.</span><span class="sxs-lookup"><span data-stu-id="4d25d-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="4d25d-106">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="4d25d-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="4d25d-107">Ключевые свойства и методы</span><span class="sxs-lookup"><span data-stu-id="4d25d-107">Key Properties and Methods</span></span>  
 <span data-ttu-id="4d25d-108">Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4d25d-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="4d25d-109">Этот компонент имеет свойства, можно задать, которые связаны с либо одной странице (<xref:System.Drawing.Printing.PrintDocument> класс) или любой документ (<xref:System.Drawing.Printing.PageSettings> класса).</span><span class="sxs-lookup"><span data-stu-id="4d25d-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="4d25d-110">Кроме того <xref:System.Windows.Forms.PageSetupDialog> компонент может использоваться для определения параметров определенного принтера, которые хранятся в <xref:System.Drawing.Printing.PrinterSettings> класса.</span><span class="sxs-lookup"><span data-stu-id="4d25d-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>  
  
 <span data-ttu-id="4d25d-111">При добавлении в форму, <xref:System.Windows.Forms.PageSetupDialog> компонент появится в области в нижней части конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4d25d-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d25d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4d25d-112">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="4d25d-113">Компонент PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="4d25d-113">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
