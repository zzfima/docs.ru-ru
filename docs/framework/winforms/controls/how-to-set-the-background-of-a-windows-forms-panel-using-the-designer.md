---
title: Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211633"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="d262e-102">Практическое руководство. Меняем цвет фона панели формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d262e-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="d262e-103">Windows Forms <xref:System.Windows.Forms.Panel> может отображать элемент управления цветом фона и фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="d262e-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="d262e-104"><xref:System.Windows.Forms.Control.BackColor%2A> Свойство задает цвет фона для элементов управления, содержащихся в панели, например, метки и переключатели.</span><span class="sxs-lookup"><span data-stu-id="d262e-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="d262e-105">Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> выбора будет заполнить все панели.</span><span class="sxs-lookup"><span data-stu-id="d262e-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="d262e-106">Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство задано, элементы управления, содержащихся на панели отображается изображение.</span><span class="sxs-lookup"><span data-stu-id="d262e-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="d262e-107">Следующая процедура требуется **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.Panel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d262e-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="d262e-108">Сведения о настройке такого проекта в Visual Studio, см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d262e-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="d262e-109">Задать фон в конструкторе Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d262e-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="d262e-110">Откройте проект в Visual Studio и выберите <xref:System.Windows.Forms.Panel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d262e-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="d262e-111">В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackColor%2A> свойство для отображения окна с тремя вкладками.</span><span class="sxs-lookup"><span data-stu-id="d262e-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="d262e-112">Выберите **Custom** вкладку, чтобы отобразить палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="d262e-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="d262e-113">Выберите **Web** или **системы** вкладку для отображения списка предопределенных имен цветов, а затем выберите цвет.</span><span class="sxs-lookup"><span data-stu-id="d262e-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="d262e-114">В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="d262e-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="d262e-115">В **откройте** диалоговом окне выберите файл, который вы хотите отобразить.</span><span class="sxs-lookup"><span data-stu-id="d262e-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="d262e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d262e-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="d262e-117">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="d262e-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="d262e-118">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="d262e-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="d262e-119">Практическое руководство. Группа элементов управления с помощью панели управления Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d262e-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
