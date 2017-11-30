---
title: "Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f2d1492148a4b00a4b96844f546a4dc968eef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="890ea-102">Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="890ea-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="890ea-103">Переключатели, также известные как переключатели, похожи на флажки, за исключением того, пользователи могут выбрать только один раз.</span><span class="sxs-lookup"><span data-stu-id="890ea-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="890ea-104">Несмотря на то что по умолчанию <xref:System.Windows.Forms.ToolStripMenuItem> класс не предоставляет функциональность переключателей, класс предоставляет поведение флажков, которые можно настроить для реализации поведения переключателей для пунктов меню в <xref:System.Windows.Forms.MenuStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="890ea-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="890ea-105">Когда <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойство пункта меню `true`, пользователям можно щелкнуть элемент, чтобы показать или скрыть метку.</span><span class="sxs-lookup"><span data-stu-id="890ea-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="890ea-106"><xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Свойство указывает текущее состояние элемента.</span><span class="sxs-lookup"><span data-stu-id="890ea-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="890ea-107">Для реализации поведения основные переключатель, вы должны убедиться, что при выборе элемента <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свойство ранее выбранного элемента в `false`.</span><span class="sxs-lookup"><span data-stu-id="890ea-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="890ea-108">Следующие процедуры описывают, как это реализовать и дополнительные функциональные возможности в наследуемом классе <xref:System.Windows.Forms.ToolStripMenuItem> класса.</span><span class="sxs-lookup"><span data-stu-id="890ea-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="890ea-109">`ToolStripRadioButtonMenuItem` Класс переопределяет элементы, такие как <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> для предоставления выбора поведение и внешний вид кнопки.</span><span class="sxs-lookup"><span data-stu-id="890ea-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="890ea-110">Кроме того, этот класс переопределяет <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство, параметры, в подменю отключены, если не выбран родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="890ea-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="890ea-111">Для реализации поведения выбора переключателей</span><span class="sxs-lookup"><span data-stu-id="890ea-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="890ea-112">Инициализация <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойства `true` Включение выбора элемента.</span><span class="sxs-lookup"><span data-stu-id="890ea-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="890ea-113">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> метод, чтобы удалить выбор ранее выбранного элемента, если элемент выбран.</span><span class="sxs-lookup"><span data-stu-id="890ea-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="890ea-114">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> метод, чтобы при щелчке элемента, который уже был выбран не будет снять выделение.</span><span class="sxs-lookup"><span data-stu-id="890ea-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="890ea-115">Чтобы изменить внешний вид элементов переключателей</span><span class="sxs-lookup"><span data-stu-id="890ea-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="890ea-116">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> метод, чтобы заменить флажок по умолчанию с помощью переключателя <xref:System.Windows.Forms.RadioButtonRenderer> класса.</span><span class="sxs-lookup"><span data-stu-id="890ea-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="890ea-117">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, и <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> методы для отслеживания состояния мыши и убедитесь, что <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> метод закрашивает состояния правильный переключателя.</span><span class="sxs-lookup"><span data-stu-id="890ea-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="890ea-118">Отключение пунктов подменю, если не выбран родительский элемент</span><span class="sxs-lookup"><span data-stu-id="890ea-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="890ea-119">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства, чтобы элемент остается недоступной, если он имеет родительский элемент с обоими <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> значение `true` и <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="890ea-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="890ea-120">Переопределить <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> метод подписаться на <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> событие родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="890ea-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="890ea-121">В обработчике родительского элемента <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> события, сделайте элемент для обновления экрана с новым состоянием включено.</span><span class="sxs-lookup"><span data-stu-id="890ea-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="890ea-122">Пример</span><span class="sxs-lookup"><span data-stu-id="890ea-122">Example</span></span>  
 <span data-ttu-id="890ea-123">В следующем примере кода предоставляет полное `ToolStripRadioButtonMenuItem` класса и <xref:System.Windows.Forms.Form> класса и `Program` для демонстрации поведения переключателей.</span><span class="sxs-lookup"><span data-stu-id="890ea-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="890ea-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="890ea-124">Compiling the Code</span></span>  
 <span data-ttu-id="890ea-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="890ea-125">This example requires:</span></span>  
  
-   <span data-ttu-id="890ea-126">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="890ea-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890ea-127">См. также</span><span class="sxs-lookup"><span data-stu-id="890ea-127">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [<span data-ttu-id="890ea-128">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="890ea-128">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [<span data-ttu-id="890ea-129">Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="890ea-129">How to: Implement a Custom ToolStripRenderer</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
