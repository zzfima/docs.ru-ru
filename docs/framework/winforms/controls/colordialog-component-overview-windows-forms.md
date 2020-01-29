---
title: Общие сведения о компоненте ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736961"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="f4a94-102">Общие сведения о компоненте ColorDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f4a94-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f4a94-103">Компонент Windows Forms <xref:System.Windows.Forms.ColorDialog> является предварительно настроенным диалоговым окном, позволяющим пользователю выбрать цвет из палитры и добавить пользовательские цвета в эту палитру.</span><span class="sxs-lookup"><span data-stu-id="f4a94-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="f4a94-104">Это то же диалоговое окно, которое вы видите в других приложениях Windows для выбора цветов.</span><span class="sxs-lookup"><span data-stu-id="f4a94-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="f4a94-105">Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="f4a94-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="f4a94-106">Цвет, выбранный в диалоговом окне, возвращается в свойстве <xref:System.Windows.Forms.ColorDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4a94-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="f4a94-107">Если свойство <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> имеет значение `false`, кнопка "определить пользовательский цвет" будет отключена, а пользователь будет ограничен стандартными цветами палитры.</span><span class="sxs-lookup"><span data-stu-id="f4a94-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="f4a94-108">Если свойство <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> имеет значение `true`, пользователь не может выбрать другие цвета.</span><span class="sxs-lookup"><span data-stu-id="f4a94-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="f4a94-109">Чтобы отобразить диалоговое окно, необходимо вызвать его метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4a94-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a94-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="f4a94-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="f4a94-111">Компонент ColorDialog</span><span class="sxs-lookup"><span data-stu-id="f4a94-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="f4a94-112">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="f4a94-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="f4a94-113">Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4a94-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
