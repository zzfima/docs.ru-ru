---
title: Как выполнить Изменение внешнего вида компонента ColorDialog в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: b516a88b4830c5ed1bccfc5ecb76ebc97c6e3b56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530301"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="7c222-102">Как выполнить Изменение внешнего вида компонента ColorDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c222-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="7c222-103">Можно настроить внешний вид форм Windows <xref:System.Windows.Forms.ColorDialog> компонент с номером из его свойств.</span><span class="sxs-lookup"><span data-stu-id="7c222-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="7c222-104">Диалоговое окно состоит из двух разделов — один из них основных цветов, а второй пользователь может определить собственные цвета.</span><span class="sxs-lookup"><span data-stu-id="7c222-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="7c222-105">Большинство свойств ограничивают набор цветов, пользователь может выбрать в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7c222-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="7c222-106">Если <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> свойству `true`, пользователь может определить собственные цвета.</span><span class="sxs-lookup"><span data-stu-id="7c222-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="7c222-107"><xref:System.Windows.Forms.ColorDialog.FullOpen%2A> Свойство `true` Если диалоговое окно будет расширен, чтобы определить собственные цвета; в противном случае пользователь должен нажать кнопку «Определить цвет».</span><span class="sxs-lookup"><span data-stu-id="7c222-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="7c222-108">Когда <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> свойству `true`, диалоговое окно отображает все доступные цвета в наборе основных цветов.</span><span class="sxs-lookup"><span data-stu-id="7c222-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="7c222-109">Если <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> свойству `true`, пользователь может выбрать сглаживания цвета; для выбора доступны только сплошные цвета.</span><span class="sxs-lookup"><span data-stu-id="7c222-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="7c222-110">Если <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> свойству `true`, кнопка справки отображается в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="7c222-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="7c222-111">Когда пользователь нажимает кнопку "Справка" <xref:System.Windows.Forms.ColorDialog> компонента <xref:System.Windows.Forms.CommonDialog.HelpRequest> события.</span><span class="sxs-lookup"><span data-stu-id="7c222-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="7c222-112">Чтобы настроить внешний вид диалогового окна «цвет»</span><span class="sxs-lookup"><span data-stu-id="7c222-112">To configure the appearance of the color dialog box</span></span>  
  
1.  <span data-ttu-id="7c222-113">Задайте <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, и <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> свойства требуемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="7c222-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7c222-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7c222-114">See also</span></span>
- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="7c222-115">Компонент ColorDialog</span><span class="sxs-lookup"><span data-stu-id="7c222-115">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)
- [<span data-ttu-id="7c222-116">Общие сведения о компоненте ColorDialog</span><span class="sxs-lookup"><span data-stu-id="7c222-116">ColorDialog Component Overview</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md)
