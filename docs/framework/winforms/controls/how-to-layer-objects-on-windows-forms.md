---
title: Создание слоев объектов
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736338"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="24dff-102">Как выполнять слои объектов на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24dff-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="24dff-103">При создании сложного пользовательского интерфейса или работе с формой многодокументного интерфейса (MDI) часто требуется послойировать как элементы управления, так и дочерние формы, чтобы создать более сложные пользовательские интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="24dff-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="24dff-104">Чтобы перемещать и контролировать элементы управления и окна в контексте группы, вы управляете их *z-порядком*.</span><span class="sxs-lookup"><span data-stu-id="24dff-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="24dff-105">Z-порядок — это визуальное расположение элементов управления на форме вдоль оси z формы (глубина).</span><span class="sxs-lookup"><span data-stu-id="24dff-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="24dff-106">Окно, расположенное в верхней части z-порядка, перекрывает все остальные окна.</span><span class="sxs-lookup"><span data-stu-id="24dff-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="24dff-107">Все остальные окна перекрываются в нижней части z-порядка.</span><span class="sxs-lookup"><span data-stu-id="24dff-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="24dff-108">Для элементов управления "слой" во время разработки</span><span class="sxs-lookup"><span data-stu-id="24dff-108">To layer controls at design time</span></span>

1. <span data-ttu-id="24dff-109">В Visual Studio выберите элемент управления, который необходимо прослойировать.</span><span class="sxs-lookup"><span data-stu-id="24dff-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="24dff-110">В меню **Формат** выберите пункт **порядок**, а затем выберите команду **переместить на передний план** или **переместить на заднюю**.</span><span class="sxs-lookup"><span data-stu-id="24dff-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="24dff-111">Программное управление слоями</span><span class="sxs-lookup"><span data-stu-id="24dff-111">To layer controls programmatically</span></span>

<span data-ttu-id="24dff-112">Используйте методы <xref:System.Windows.Forms.Control.BringToFront%2A> и <xref:System.Windows.Forms.Control.SendToBack%2A>, чтобы управлять z-порядком элементов управления.</span><span class="sxs-lookup"><span data-stu-id="24dff-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="24dff-113">Например, если элемент управления <xref:System.Windows.Forms.TextBox>, `txtFirstName`, находится под другим элементом управления и требуется его поверх, используйте следующий код:</span><span class="sxs-lookup"><span data-stu-id="24dff-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="24dff-114">Windows Forms поддерживает *Включение элементов управления*.</span><span class="sxs-lookup"><span data-stu-id="24dff-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="24dff-115">Включение элемента управления включает в себя размещение нескольких элементов управления внутри содержащего их элемента управления, например число элементов управления <xref:System.Windows.Forms.RadioButton> в элементе управления <xref:System.Windows.Forms.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="24dff-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="24dff-116">Затем можно послойировать элементы управления внутри содержащего его элемента управления.</span><span class="sxs-lookup"><span data-stu-id="24dff-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="24dff-117">Перемещение поля группы также приводит к перемещению элементов управления, так как они находятся внутри него.</span><span class="sxs-lookup"><span data-stu-id="24dff-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="24dff-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="24dff-118">See also</span></span>

- [<span data-ttu-id="24dff-119">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24dff-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="24dff-120">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24dff-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="24dff-121">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24dff-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="24dff-122">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="24dff-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
