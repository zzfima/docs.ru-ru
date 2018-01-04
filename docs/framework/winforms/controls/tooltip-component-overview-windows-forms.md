---
title: "Общие сведения о компоненте ToolTip (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="cae33-102">Общие сведения о компоненте ToolTip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="cae33-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="cae33-103">Компонент <xref:System.Windows.Forms.ToolTip> в Windows Forms отображает текст при наведении указателя мыши на элементы управления.</span><span class="sxs-lookup"><span data-stu-id="cae33-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="cae33-104">Компонент ToolTip можно связать с любым элементом управления.</span><span class="sxs-lookup"><span data-stu-id="cae33-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="cae33-105">Пример использования этого компонента: для экономии места в форме маленького значка для кнопки и использовать компонент ToolTip для объяснения ее функции.</span><span class="sxs-lookup"><span data-stu-id="cae33-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="cae33-106">Работа с компонентом ToolTip</span><span class="sxs-lookup"><span data-stu-id="cae33-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="cae33-107">Объект <xref:System.Windows.Forms.ToolTip> компонент предоставляет `ToolTip` свойства для нескольких элементов управления на форму Windows или другой контейнер.</span><span class="sxs-lookup"><span data-stu-id="cae33-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="cae33-108">Например, если одна <xref:System.Windows.Forms.ToolTip> компонент на форме, можно отобразить «Введите здесь имя» для <xref:System.Windows.Forms.TextBox> управления и щелкните здесь, чтобы сохранить изменения» для <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cae33-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="cae33-109">Основные методы <xref:System.Windows.Forms.ToolTip> , компонент <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> и <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span><span class="sxs-lookup"><span data-stu-id="cae33-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="cae33-110">Можно использовать <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод, чтобы задать подсказки, отображаемый для элементов управления.</span><span class="sxs-lookup"><span data-stu-id="cae33-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="cae33-111">Дополнительные сведения см. в разделе [как: задайте подсказки для элементов управления формы Windows Forms во время разработки](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="cae33-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="cae33-112">Ключевые свойства, <xref:System.Windows.Forms.ToolTip.Active%2A>, которое должно быть равно `true` для подсказки, которая отображается, и <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, который задает время, строки всплывающей подсказки, как долго пользователь должен указывать на элемент управления для подсказки, которая отображается и как его длину принимает окна очередной всплывающей подсказки для отображения.</span><span class="sxs-lookup"><span data-stu-id="cae33-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="cae33-113">Дополнительные сведения см. в разделе [как: изменение значения задержки для компонента ToolTip в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span><span class="sxs-lookup"><span data-stu-id="cae33-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae33-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cae33-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolTip>  
 [<span data-ttu-id="cae33-115">Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="cae33-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="cae33-116">Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cae33-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
