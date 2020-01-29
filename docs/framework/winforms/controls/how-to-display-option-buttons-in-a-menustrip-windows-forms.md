---
title: Практическое руководство. Отображение переключателей в элементе управления MenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735522"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="95e31-102">Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="95e31-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="95e31-103">Переключатели, также называемые переключателями, аналогичны флажкам, за исключением того, что пользователи могут выбирать только один из них за раз.</span><span class="sxs-lookup"><span data-stu-id="95e31-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="95e31-104">Несмотря на то, что по умолчанию класс <xref:System.Windows.Forms.ToolStripMenuItem> не обеспечивает поведение переключателя, класс предоставляет поведение флажка, которое можно настроить для реализации поведения переключателей для пунктов меню в элементе управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="95e31-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="95e31-105">Если свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> элемента меню `true`, пользователи могут щелкнуть элемент, чтобы включить или отключить отображение галочки.</span><span class="sxs-lookup"><span data-stu-id="95e31-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="95e31-106">Свойство <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> указывает текущее состояние элемента.</span><span class="sxs-lookup"><span data-stu-id="95e31-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="95e31-107">Чтобы реализовать базовое поведение переключателя, необходимо убедиться, что при выборе элемента свойству <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> для ранее выбранного элемента задается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="95e31-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="95e31-108">В следующих процедурах описывается реализация этой и дополнительной функциональности в классе, который наследует класс <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="95e31-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="95e31-109">Класс `ToolStripRadioButtonMenuItem` переопределяет элементы, такие как <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, чтобы обеспечить поведение выбора и внешний вид переключателей.</span><span class="sxs-lookup"><span data-stu-id="95e31-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="95e31-110">Кроме того, этот класс переопределяет свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>, чтобы параметры в подменю были отключены, если не выбран родительский элемент.</span><span class="sxs-lookup"><span data-stu-id="95e31-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="95e31-111">Реализация поведения при выборе переключателя</span><span class="sxs-lookup"><span data-stu-id="95e31-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="95e31-112">Инициализируйте свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>, чтобы `true`, чтобы включить выбор элементов.</span><span class="sxs-lookup"><span data-stu-id="95e31-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="95e31-113">Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>, чтобы очистить выбор ранее выбранного элемента при выборе нового элемента.</span><span class="sxs-lookup"><span data-stu-id="95e31-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="95e31-114">Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A>, чтобы убедиться, что щелчок элемента, который уже был выбран, не очистит выбор.</span><span class="sxs-lookup"><span data-stu-id="95e31-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="95e31-115">Изменение внешнего вида элементов переключателя</span><span class="sxs-lookup"><span data-stu-id="95e31-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="95e31-116">Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, чтобы заменить флажок по умолчанию на переключатель с помощью класса <xref:System.Windows.Forms.RadioButtonRenderer>.</span><span class="sxs-lookup"><span data-stu-id="95e31-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="95e31-117">Переопределите методы <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>и <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> для отслеживания состояния мыши и убедитесь, что метод <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> рисует правильное состояние переключателя.</span><span class="sxs-lookup"><span data-stu-id="95e31-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="95e31-118">Отключение параметров в подменю, если родительский элемент не выбран</span><span class="sxs-lookup"><span data-stu-id="95e31-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="95e31-119">Переопределите свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>, чтобы элемент был отключен, если у него есть родительский элемент с <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> значением `true` и <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> значением `false`.</span><span class="sxs-lookup"><span data-stu-id="95e31-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="95e31-120">Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>, чтобы подписаться на событие <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="95e31-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="95e31-121">В обработчике для события <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента делает недействительным элемент для обновления отображения с новым включенным состоянием.</span><span class="sxs-lookup"><span data-stu-id="95e31-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="95e31-122">Пример</span><span class="sxs-lookup"><span data-stu-id="95e31-122">Example</span></span>

<span data-ttu-id="95e31-123">В следующем примере кода представлен полный `ToolStripRadioButtonMenuItem` класс, класс <xref:System.Windows.Forms.Form> и класс `Program`, демонстрирующие поведение переключателя.</span><span class="sxs-lookup"><span data-stu-id="95e31-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="95e31-124">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="95e31-124">Compiling the Code</span></span>

<span data-ttu-id="95e31-125">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="95e31-125">This example requires:</span></span>

- <span data-ttu-id="95e31-126">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="95e31-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="95e31-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="95e31-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="95e31-128">Элемент управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="95e31-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="95e31-129">Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="95e31-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
