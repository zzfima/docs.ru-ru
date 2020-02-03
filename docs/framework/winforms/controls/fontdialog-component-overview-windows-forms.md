---
title: Общие сведения о компоненте FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745702"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="e2a4b-102">Общие сведения о компоненте FontDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e2a4b-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e2a4b-103">Компонент Windows Forms <xref:System.Windows.Forms.FontDialog> является предварительно настроенным диалоговым окном, которое является стандартным диалоговым окном Windows **Font** , используемым для предоставления шрифтов, установленных в данный момент в системе.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="e2a4b-104">Используйте его в приложении Windows в качестве простого решения для выбора шрифта вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="e2a4b-105">По умолчанию в диалоговом окне отображаются списки для шрифта, стиля и размера шрифта. флажки для таких эффектов, как зачеркивание и подчеркивание; раскрывающийся список для скрипта; и пример того, как будет выглядеть шрифт.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="e2a4b-106">(Скрипт ссылается на различные символьные скрипты, доступные для данного шрифта, например иврит или японский.) Чтобы отобразить диалоговое окно Шрифт, вызовите метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e2a4b-107">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="e2a4b-107">Key Properties</span></span>  
 <span data-ttu-id="e2a4b-108">Компонент имеет ряд свойств, которые настраивают его внешний вид.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="e2a4b-109">Свойства, заданные для выбора диалогового окна, <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="e2a4b-110">Свойство <xref:System.Windows.Forms.FontDialog.Font%2A> задает шрифт, стиль, размер, скрипт и эффекты. Например, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="e2a4b-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a4b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2a4b-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="e2a4b-112">Компонент FontDialog</span><span class="sxs-lookup"><span data-stu-id="e2a4b-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
