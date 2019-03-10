---
title: Практическое руководство. Многоуровневое расположение объектов в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: ea97e26d31d2cdda353b6ada554cac27c5b56c62
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719108"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="a6961-102">Практическое руководство. Многоуровневое расположение объектов в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="a6961-103">При создании сложного пользовательского интерфейса, или работать с формой многодокументного интерфейса (MDI), часто требуется слоя элементы управления и дочерние формы для создания более сложных интерфейсов пользователя (UI).</span><span class="sxs-lookup"><span data-stu-id="a6961-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="a6961-104">Чтобы переместить и хранить список элементов управления и окон в контексте группы, управлять z порядком.</span><span class="sxs-lookup"><span data-stu-id="a6961-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="a6961-105">*Z-порядок* является видимое расположение элементов управления на форме вдоль оси z формы (глубина).</span><span class="sxs-lookup"><span data-stu-id="a6961-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="a6961-106">Окно, в верхней части z порядок перекрывает все остальные окна.</span><span class="sxs-lookup"><span data-stu-id="a6961-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="a6961-107">Все остальные окна перекрывают окно в нижней части z порядка.</span><span class="sxs-lookup"><span data-stu-id="a6961-107">All other windows overlap the window at the bottom of the z-order.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6961-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="a6961-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a6961-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="a6961-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a6961-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a6961-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="a6961-111">Чтобы расположить элементы управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="a6961-111">To layer controls at design time</span></span>  
  
1.  <span data-ttu-id="a6961-112">Выберите элемент управления, который вы хотите слоев.</span><span class="sxs-lookup"><span data-stu-id="a6961-112">Select a control that you want to layer.</span></span>  
  
2.  <span data-ttu-id="a6961-113">На **формат** последовательно выберите пункты **порядок**, а затем нажмите кнопку **на передний** или **на задний**.</span><span class="sxs-lookup"><span data-stu-id="a6961-113">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>  
  
### <a name="to-layer-controls-programmatically"></a><span data-ttu-id="a6961-114">Чтобы расположить элементы управления программными средствами</span><span class="sxs-lookup"><span data-stu-id="a6961-114">To layer controls programmatically</span></span>  
  
-   <span data-ttu-id="a6961-115">Используйте <xref:System.Windows.Forms.Control.BringToFront%2A> и <xref:System.Windows.Forms.Control.SendToBack%2A> методы для управления z порядок элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a6961-115">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>  
  
     <span data-ttu-id="a6961-116">Например если <xref:System.Windows.Forms.TextBox> элемента управления, `txtFirstName`, находится под другим элементом управления и необходимо переместить его вверх, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="a6961-116">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="a6961-117">Windows Forms поддерживает *вложении элементов управления*.</span><span class="sxs-lookup"><span data-stu-id="a6961-117">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="a6961-118">Включение элементов управления заключается в размещении нескольких элементов управления внутри элемента управления, такие как ряд <xref:System.Windows.Forms.RadioButton> внутри элементов управления <xref:System.Windows.Forms.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6961-118">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="a6961-119">Можно размещать элементы управления внутри содержащего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6961-119">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="a6961-120">Перемещение группы перемещает элементы управления, так как они содержатся внутри него.</span><span class="sxs-lookup"><span data-stu-id="a6961-120">Moving the group box moves the controls as well, because they are contained inside it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6961-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a6961-121">See also</span></span>
- [<span data-ttu-id="a6961-122">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="a6961-123">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-123">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="a6961-124">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-124">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="a6961-125">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-125">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="a6961-126">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a6961-126">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
