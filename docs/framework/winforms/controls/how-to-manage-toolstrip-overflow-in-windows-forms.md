---
title: Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736143"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="c8bc6-102">Практическое руководство. Управление областью переполнения в элементе управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c8bc6-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="c8bc6-103">Если все элементы элемента управления <xref:System.Windows.Forms.ToolStrip> не помещаются в выделенном пространстве, можно включить функцию переполнения на <xref:System.Windows.Forms.ToolStrip> и определить поведение переполнения конкретных <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="c8bc6-104">При добавлении <xref:System.Windows.Forms.ToolStripItem>s, требующих больше пространства, чем выделено <xref:System.Windows.Forms.ToolStrip> с учетом текущего размера формы, <xref:System.Windows.Forms.ToolStripOverflowButton> автоматически появляется на <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="c8bc6-105">Появится <xref:System.Windows.Forms.ToolStripOverflowButton>, а элементы с поддержкой переполнения будут перемещены в раскрывающееся меню переполнения.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="c8bc6-106">Это позволяет настраивать и определять приоритеты, определяющие правильную настройку <xref:System.Windows.Forms.ToolStrip> элементов на различные размеры форм.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="c8bc6-107">Можно также изменить внешний вид элементов, попадающие в переполнение, с помощью свойств <xref:System.Windows.Forms.ToolStripItem.Placement%2A> и <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> события.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="c8bc6-108">При увеличении формы во время разработки или во время выполнения на главном <xref:System.Windows.Forms.ToolStrip> может отображаться больше <xref:System.Windows.Forms.ToolStripItem>, а <xref:System.Windows.Forms.ToolStripOverflowButton> может даже исчезнуть до тех пор, пока не будет уменьшен размер формы.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="c8bc6-109">Включение переполнения для элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c8bc6-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="c8bc6-110">Убедитесь, что для свойства <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> не задано значение `false` для <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="c8bc6-111">Значение по умолчанию — `True`.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-111">The default is `True`.</span></span>

     <span data-ttu-id="c8bc6-112">Если <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> имеет `True` (значение по умолчанию), <xref:System.Windows.Forms.ToolStripItem> передается в раскрывающееся меню переполнения, если содержимое <xref:System.Windows.Forms.ToolStripItem> превышает ширину горизонтального <xref:System.Windows.Forms.ToolStrip> или высоты вертикального <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="c8bc6-113">Указание поведения определенного элемента ToolStripItem в случае переполнения</span><span class="sxs-lookup"><span data-stu-id="c8bc6-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="c8bc6-114">Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> <xref:System.Windows.Forms.ToolStripItem> нужное значение.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="c8bc6-115">Возможные варианты: `Always`, `Never`и `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="c8bc6-116">Значение по умолчанию — `AsNeeded`.</span><span class="sxs-lookup"><span data-stu-id="c8bc6-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="c8bc6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="c8bc6-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="c8bc6-118">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c8bc6-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="c8bc6-119">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c8bc6-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="c8bc6-120">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c8bc6-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
