---
title: "Общие сведения о компоненте ColorDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5df0d7ddd16de5bd8bb052c09731df6583ca4903
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="581ba-102">Общие сведения о компоненте ColorDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="581ba-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="581ba-103">Windows Forms <xref:System.Windows.Forms.ColorDialog> компонент является стандартным диалоговым окном, который позволяет пользователю выбрать цвет из палитры и добавления в нее пользовательских цветов.</span><span class="sxs-lookup"><span data-stu-id="581ba-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="581ba-104">Это то же диалоговое окно, которое вы видите в других приложениях Windows для выбора цветов.</span><span class="sxs-lookup"><span data-stu-id="581ba-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="581ba-105">Он используется в приложении Windows в качестве простого решения вместо настройки собственного диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="581ba-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="581ba-106">Цвет, выбранный в диалоговом окне, возвращается в <xref:System.Windows.Forms.ColorDialog.Color%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="581ba-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="581ba-107">Если <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> свойству `false`, кнопка «Определить цвет» становится недоступной, и пользователь будет ограничен стандартных цветов в палитре.</span><span class="sxs-lookup"><span data-stu-id="581ba-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="581ba-108">Если <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> свойству `true`, пользователь может выбрать сглаженный цвет.</span><span class="sxs-lookup"><span data-stu-id="581ba-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="581ba-109">Чтобы открыть диалоговое окно, необходимо вызвать его <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="581ba-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581ba-110">См. также</span><span class="sxs-lookup"><span data-stu-id="581ba-110">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="581ba-111">Компонент ColorDialog</span><span class="sxs-lookup"><span data-stu-id="581ba-111">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="581ba-112">Элементы управления и компоненты диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="581ba-112">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [<span data-ttu-id="581ba-113">Практическое руководство. Изменение внешнего вида компонента ColorDialog в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="581ba-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
