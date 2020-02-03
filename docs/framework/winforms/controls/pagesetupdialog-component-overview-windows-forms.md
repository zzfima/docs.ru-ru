---
title: Общие сведения о компоненте PageSetupDialog
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: a891cb8cc77007d7591d41461c94f61c077eb300
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744340"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a><span data-ttu-id="bcc60-102">Общие сведения о компоненте PageSetupDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bcc60-102">PageSetupDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="bcc60-103">Компонент Windows Forms <xref:System.Windows.Forms.PageSetupDialog> является предварительно настроенным диалоговым окном, используемым для задания сведений о странице для печати в приложениях Windows.</span><span class="sxs-lookup"><span data-stu-id="bcc60-103">The Windows Forms <xref:System.Windows.Forms.PageSetupDialog> component is a pre-configured dialog box used to set page details for printing in Windows-based applications.</span></span> <span data-ttu-id="bcc60-104">Используйте его в приложении Windows в качестве простого решения для пользователей, чтобы задать параметры страницы вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="bcc60-104">Use it within your Windows-based application as a simple solution for users to set page preferences in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="bcc60-105">Можно разрешить пользователям задавать настройки границ и полей, верхние и нижние колонтитулы, а также книжную или альбомную ориентацию.</span><span class="sxs-lookup"><span data-stu-id="bcc60-105">You can enable users to set border and margin adjustments, headers and footers, and portrait or landscape orientation.</span></span> <span data-ttu-id="bcc60-106">Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.</span><span class="sxs-lookup"><span data-stu-id="bcc60-106">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="bcc60-107">Ключевые свойства и методы</span><span class="sxs-lookup"><span data-stu-id="bcc60-107">Key Properties and Methods</span></span>

<span data-ttu-id="bcc60-108">Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bcc60-108">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="bcc60-109">Этот компонент имеет свойства, которые могут быть связаны с одной страницей (<xref:System.Drawing.Printing.PrintDocument> класс) или с любым документом (<xref:System.Drawing.Printing.PageSettings> класса).</span><span class="sxs-lookup"><span data-stu-id="bcc60-109">This component has properties you can set that relate to either a single page (<xref:System.Drawing.Printing.PrintDocument> class) or any document (<xref:System.Drawing.Printing.PageSettings> class).</span></span> <span data-ttu-id="bcc60-110">Кроме того, компонент <xref:System.Windows.Forms.PageSetupDialog> можно использовать для определения конкретных параметров принтера, которые хранятся в классе <xref:System.Drawing.Printing.PrinterSettings>.</span><span class="sxs-lookup"><span data-stu-id="bcc60-110">Additionally, the <xref:System.Windows.Forms.PageSetupDialog> component can be used to determine specific printer settings, which are stored in the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span>

<span data-ttu-id="bcc60-111">При добавлении в форму <xref:System.Windows.Forms.PageSetupDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bcc60-111">When it is added to a form, the <xref:System.Windows.Forms.PageSetupDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcc60-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcc60-112">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="bcc60-113">Компонент PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="bcc60-113">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
