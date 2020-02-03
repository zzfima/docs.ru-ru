---
title: Установка фона панели с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 8bdefba433632f7ba02f549a549c52c7aa56c2d7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731921"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="0e73c-102">Как задать фон панели Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="0e73c-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="0e73c-103">Элемент управления Windows Forms <xref:System.Windows.Forms.Panel> может отображать как цвет фона, так и фоновое изображение.</span><span class="sxs-lookup"><span data-stu-id="0e73c-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="0e73c-104">Свойство <xref:System.Windows.Forms.Control.BackColor%2A> задает цвет фона для элементов управления, содержащихся на панели, таких как метки и переключатели.</span><span class="sxs-lookup"><span data-stu-id="0e73c-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="0e73c-105">Если свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> не задано, выбор <xref:System.Windows.Forms.Control.BackColor%2A> будет заполнять все панели.</span><span class="sxs-lookup"><span data-stu-id="0e73c-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="0e73c-106">Если задано свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A>, изображение будет отображаться позади элементов управления, содержащихся на панели.</span><span class="sxs-lookup"><span data-stu-id="0e73c-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="0e73c-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="0e73c-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="0e73c-108">Сведения о том, как настроить такой проект в Visual Studio, см. в разделе [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0e73c-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="0e73c-109">Задайте фон в конструктор Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e73c-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="0e73c-110">Откройте проект в Visual Studio и выберите элемент управления <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="0e73c-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="0e73c-111">В окне **Свойства** нажмите кнопку со стрелкой рядом со свойством <xref:System.Windows.Forms.Control.BackColor%2A>, чтобы отобразить окно с тремя вкладками.</span><span class="sxs-lookup"><span data-stu-id="0e73c-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="0e73c-112">Выберите вкладку **Пользовательская** , чтобы отобразить палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="0e73c-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="0e73c-113">Перейдите на вкладку **веб** или **система** , чтобы отобразить список предопределенных имен цветов, а затем выберите цвет.</span><span class="sxs-lookup"><span data-stu-id="0e73c-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="0e73c-114">В окне **Свойства** нажмите кнопку со стрелкой рядом со свойством <xref:System.Windows.Forms.Control.BackgroundImage%2A>.</span><span class="sxs-lookup"><span data-stu-id="0e73c-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="0e73c-115">В диалоговом окне **Открыть** выберите файл, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="0e73c-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e73c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e73c-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="0e73c-117">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="0e73c-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="0e73c-118">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="0e73c-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="0e73c-119">Практическое руководство. Группирование элементов управления с элементом управления Panel в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="0e73c-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
