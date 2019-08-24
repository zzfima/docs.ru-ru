---
title: Практическое руководство. Изменение размера элементов управления в формах Windows Forms
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7e659bf02ea079afc10561e1d83f7ab7cef29a2e
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987057"
---
# <a name="how-to-resize-controls-on-windows-forms"></a><span data-ttu-id="7f1c7-102">Практическое руководство. Изменить размер элементов управления на Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f1c7-102">How to: Resize controls on Windows Forms</span></span>

<span data-ttu-id="7f1c7-103">Можно изменить размер отдельных элементов управления, а также изменить размер различных элементов управления, например <xref:System.Windows.Forms.Button> элементов управления и. <xref:System.Windows.Forms.GroupBox></span><span class="sxs-lookup"><span data-stu-id="7f1c7-103">You can resize individual controls, and you can resize multiple controls of the same or different kind, such as <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.GroupBox> controls.</span></span>

## <a name="to-resize-a-control"></a><span data-ttu-id="7f1c7-104">Изменение размера элемента управления</span><span class="sxs-lookup"><span data-stu-id="7f1c7-104">To resize a control</span></span>

<span data-ttu-id="7f1c7-105">В Visual Studio выберите элемент управления, размер которого нужно изменить, и перетащите один из восьми маркеров изменения размера.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-105">In Visual Studio, select the control to be resized and drag one of the eight sizing handles.</span></span>

> [!NOTE]
> <span data-ttu-id="7f1c7-106">Выберите элемент управления и нажмите клавиши **со стрелками** , удерживая нажатой клавишу **SHIFT** , чтобы изменить размер элемента управления на один пиксель за раз.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-106">Select the control and press the **arrow** keys while holding down the **Shift** key to resize the control one pixel at a time.</span></span> <span data-ttu-id="7f1c7-107">Нажмите клавишу **стрелка вниз** или клавишу **со стрелкой вправо** , удерживая нажатыми клавиши **SHIFT** и **CTRL** , чтобы изменить размер элемента управления с большим шагом.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-107">Press the **down arrow** or **right arrow** keys while holding down the **Shift** and **Ctrl** keys to resize the control in large increments.</span></span>

## <a name="to-resize-multiple-controls-on-a-form"></a><span data-ttu-id="7f1c7-108">Изменение размера нескольких элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="7f1c7-108">To resize multiple controls on a form</span></span>

1. <span data-ttu-id="7f1c7-109">В Visual Studio удерживайте нажатой клавишу **CTRL** или **SHIFT** и выберите элементы управления, размер которых необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-109">In Visual Studio, hold down the **Ctrl** or **Shift** key and select the controls you want to resize.</span></span> <span data-ttu-id="7f1c7-110">Размер первого выбранного элемента управления используется для других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-110">The size of the first control you select is used for the other controls.</span></span>

2. <span data-ttu-id="7f1c7-111">В меню **Формат** выберите пункт **сделать тот же размер**и выберите один из четырех параметров.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-111">On the **Format** menu, choose **Make Same Size**, and select one of the four options.</span></span> <span data-ttu-id="7f1c7-112">Первые три команды изменяют размеры элементов управления в соответствии с первым выбранным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7f1c7-112">The first three commands change the dimensions of the controls to match the first-selected control.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f1c7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7f1c7-113">See also</span></span>

- [<span data-ttu-id="7f1c7-114">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f1c7-114">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="7f1c7-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f1c7-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="7f1c7-116">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f1c7-116">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="7f1c7-117">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f1c7-117">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="7f1c7-118">[Практическое руководство. Изменение размера Windows Forms с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7f1c7-118">[How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span></span>
