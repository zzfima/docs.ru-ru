---
title: Практическое руководство. Скрытие элемента управления во время выполнения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], making invisible at run time
- invisible controls
- user controls [Windows Forms], invisible
- custom controls [Windows Forms], invisible
- run time [Windows Forms], making controls invisible
ms.assetid: 69eb2e72-32f5-4f79-a157-c2c5f60c1628
ms.openlocfilehash: 52ea2336bac1ec483cb86e24114090a1b3725038
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708981"
---
# <a name="how-to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="a24eb-102">Практическое руководство. Скрытие элемента управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a24eb-102">How to: Make Your Control Invisible at Run Time</span></span>
<span data-ttu-id="a24eb-103">Бывают случаи, когда может потребоваться создать пользовательский элемент управления, который остается невидимым во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a24eb-103">There are times when you might want to create a user control that is invisible at run time.</span></span> <span data-ttu-id="a24eb-104">Например элемент управления, который является будильника может быть невидимым, за исключением случаев, когда будильника.</span><span class="sxs-lookup"><span data-stu-id="a24eb-104">For example, a control that is an alarm clock might be invisible except when the alarm was sounding.</span></span> <span data-ttu-id="a24eb-105">Это легко реализуется, задав <xref:System.Windows.Forms.Control.Visible%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a24eb-105">This is easily accomplished by setting the <xref:System.Windows.Forms.Control.Visible%2A> property.</span></span> <span data-ttu-id="a24eb-106">Если <xref:System.Windows.Forms.Control.Visible%2A> свойство `true`, элемент управления отображается в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="a24eb-106">If the <xref:System.Windows.Forms.Control.Visible%2A> property is `true`, your control will appear as normal.</span></span> <span data-ttu-id="a24eb-107">Если `false`, элемент управления будет скрыт.</span><span class="sxs-lookup"><span data-stu-id="a24eb-107">If `false`, your control will be hidden.</span></span> <span data-ttu-id="a24eb-108">Несмотря на то, что код в элемент управления может выполняться будучи невидимым, вы не сможете взаимодействовать с элементом управления в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="a24eb-108">Although code in your control may still run while invisible, you will not be able to interact with the control through the user interface.</span></span> <span data-ttu-id="a24eb-109">Если вы хотите создать невидимому элементу управления, который реагирует на пользовательский ввод (например, щелчки мышью), следует создать прозрачный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a24eb-109">If you want to create an invisible control that still responds to user input (for example, mouse clicks), you should create a transparent control.</span></span> <span data-ttu-id="a24eb-110">Дополнительные сведения см. в разделе [предоставления элемента управления прозрачный фон](how-to-give-your-control-a-transparent-background.md).</span><span class="sxs-lookup"><span data-stu-id="a24eb-110">For more information, see [Giving Your Control a Transparent Background](how-to-give-your-control-a-transparent-background.md).</span></span>  
  
### <a name="to-make-your-control-invisible-at-run-time"></a><span data-ttu-id="a24eb-111">Чтобы скрыть элемент управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="a24eb-111">To make your control invisible at run time</span></span>  
  
1.  <span data-ttu-id="a24eb-112">Задайте для свойства <xref:System.Windows.Forms.Control.Visible%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="a24eb-112">Set the <xref:System.Windows.Forms.Control.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    ' To set the Visible property from within your object's own code.  
    Me.Visible = False  
    ' To set the Visible property from another object.  
    myControl1.Visible = False  
    ```  
  
    ```csharp  
    // To set the Visible property from within your object's own code.  
    this.Visible = false;  
    // To set the Visible property from another object.  
    myControl1.Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a24eb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a24eb-113">See also</span></span>
- <xref:System.Windows.Forms.Control.Visible%2A>
- [<span data-ttu-id="a24eb-114">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a24eb-114">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="a24eb-115">Практическое руководство. Установка степени прозрачности фона элемента управления</span><span class="sxs-lookup"><span data-stu-id="a24eb-115">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)
