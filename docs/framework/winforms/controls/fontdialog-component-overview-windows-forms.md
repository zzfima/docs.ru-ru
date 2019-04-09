---
title: Общие сведения о компоненте FontDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 7f140807bf4b42e530302190042e729c59248e7f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098563"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="20f64-102">Общие сведения о компоненте FontDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="20f64-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="20f64-103">Windows Forms <xref:System.Windows.Forms.FontDialog> компонент является стандартным диалоговым окном, который является стандартной Windows **шрифта** диалоговое окно, используемое для предоставления шрифтов, установленных в системе.</span><span class="sxs-lookup"><span data-stu-id="20f64-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="20f64-104">Используйте его в приложении Windows в качестве простого решения для выбора шрифтов, вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="20f64-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="20f64-105">По умолчанию в диалоговом окне отображаются списки с множественным для шрифта, стиль шрифта и размера; Установите флажки для эффектов, как зачеркивание и подчеркивание; стрелку раскрывающегося списка для скрипта; и пример того, как будет выглядеть шрифт.</span><span class="sxs-lookup"><span data-stu-id="20f64-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="20f64-106">(Сценарий ссылается на другой символ сценарии, которые доступны для данного шрифта, к примеру, иврит или японский.) Чтобы отобразить диалоговое окно "Шрифт", вызовите <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20f64-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="20f64-107">Ключевые свойства</span><span class="sxs-lookup"><span data-stu-id="20f64-107">Key Properties</span></span>  
 <span data-ttu-id="20f64-108">Компонент содержит ряд свойств, определяющих его внешний вид.</span><span class="sxs-lookup"><span data-stu-id="20f64-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="20f64-109">Свойства, задайте параметры диалогового окна, <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="20f64-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="20f64-110"><xref:System.Windows.Forms.FontDialog.Font%2A> Задает свойства шрифта, стиль, размер, скрипт и эффектов; например, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="20f64-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f64-111">См. также</span><span class="sxs-lookup"><span data-stu-id="20f64-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="20f64-112">Компонент FontDialog</span><span class="sxs-lookup"><span data-stu-id="20f64-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
