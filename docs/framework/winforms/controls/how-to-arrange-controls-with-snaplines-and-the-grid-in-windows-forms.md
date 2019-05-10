---
title: Практическое руководство. Упорядочение элементов управления с помощью линий привязки и сетки в формах Windows Forms
ms.date: 03/30/2017
f1_keywords:
- GridSize
helpviewer_keywords:
- snap to grid [Windows Forms], Windows Forms Designer
- Windows Forms, grid options in designer
- controls [Windows Forms], aligning
ms.assetid: bb54bce5-880f-4a36-af68-8cf92058dc1c
ms.openlocfilehash: 87da92d4396921de1a5ee50de33c2a2a43475739
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211797"
---
# <a name="how-to-arrange-controls-with-snaplines-and-the-grid-in-windows-forms"></a><span data-ttu-id="6f751-102">Практическое руководство. Упорядочение элементов управления с помощью линий привязки и сетки в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-102">How to: Arrange Controls with Snaplines and the Grid in Windows Forms</span></span>

<span data-ttu-id="6f751-103">Используя возможности макета элемента Visual Studio, можно точно указать расположение элементов управления в форме.</span><span class="sxs-lookup"><span data-stu-id="6f751-103">Using the layout features of Visual Studio, you can precisely direct where controls are placed on a form.</span></span> <span data-ttu-id="6f751-104">Элементы управления добавить в форму или переместить в форме автоматически выравниваются в строки и столбцы сетки в конструкторе Windows Forms, или можно выравнивать элементы управления с помощью линий привязки.</span><span class="sxs-lookup"><span data-stu-id="6f751-104">Controls added to a form or moved on a form can be automatically aligned to the rows and columns of the Windows Forms Designer's grid, or you can align controls by using the snaplines feature.</span></span>

## <a name="snap-all-controls-to-the-grid"></a><span data-ttu-id="6f751-105">Привязать все элементы управления к сетке</span><span class="sxs-lookup"><span data-stu-id="6f751-105">Snap all controls to the grid</span></span>

<span data-ttu-id="6f751-106">Выберите **SnapToGrid** режим макета в конструкторе Windows Forms **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="6f751-106">Select the **SnapToGrid** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>

<span data-ttu-id="6f751-107">Дополнительные сведения см. в разделе [Общие, конструктор Windows Forms, диалоговое окно параметров](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6f751-107">For more information, see [General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100)).</span></span> <span data-ttu-id="6f751-108">Все элементы управления теперь выравниваются по точкам сетки.</span><span class="sxs-lookup"><span data-stu-id="6f751-108">All controls now align themselves along the points on the grid.</span></span>

<span data-ttu-id="6f751-109">Отдельные элементы управления в сетку можно привязывать, блокировки их на месте.</span><span class="sxs-lookup"><span data-stu-id="6f751-109">You can snap individual controls to the grid by locking them in place.</span></span> <span data-ttu-id="6f751-110">Тем не менее хотя они заблокированы, их нельзя переместить или изменить размер.</span><span class="sxs-lookup"><span data-stu-id="6f751-110">However, while they are locked, they cannot be moved or resized.</span></span> <span data-ttu-id="6f751-111">Дополнительные сведения о блокировке элементов управления, см. в разделе [как: Блокирование элементов управления в Windows Forms](how-to-lock-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6f751-111">For more information about locking controls, see [How to: Lock Controls to Windows Forms](how-to-lock-controls-to-windows-forms.md).</span></span>

## <a name="align-controls-using-snaplines"></a><span data-ttu-id="6f751-112">Выравнивание элементов управления с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="6f751-112">Align controls using snaplines</span></span>

<span data-ttu-id="6f751-113">Выберите **линии привязки** режим макета в конструкторе Windows Forms **параметры** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="6f751-113">Select the **SnapLines** layout mode in the Windows Forms Designer **Options** dialog box.</span></span>

<span data-ttu-id="6f751-114">Дополнительные сведения см. в разделе [Пошаговое руководство: Упорядочение элементов управления в Windows Forms с помощью линий привязки](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span><span class="sxs-lookup"><span data-stu-id="6f751-114">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span> <span data-ttu-id="6f751-115">Теперь можно использовать линии привязки для выравнивания и упорядочения элементов управления в форме.</span><span class="sxs-lookup"><span data-stu-id="6f751-115">You can now use snaplines to align and arrange controls on your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f751-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f751-116">See also</span></span>

- <span data-ttu-id="6f751-117">[Страница "Общие", конструктор Windows Forms, диалоговое окно "Параметры](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6f751-117">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- [<span data-ttu-id="6f751-118">Пошаговое руководство: Упорядочение элементов управления в формах Windows Forms, с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="6f751-118">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="6f751-119">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="6f751-120">Практическое руководство. Добавление элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="6f751-121">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="6f751-122">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="6f751-123">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="6f751-124">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f751-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
