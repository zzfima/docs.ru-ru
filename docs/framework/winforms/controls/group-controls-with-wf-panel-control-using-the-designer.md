---
title: Группирование элементов управления Panel с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745650"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a><span data-ttu-id="9b8a9-102">Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9b8a9-102">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>
<span data-ttu-id="9b8a9-103">Windows Forms элементы управления <xref:System.Windows.Forms.Panel> используются для группирования других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to group other controls.</span></span> <span data-ttu-id="9b8a9-104">Существует три причины для группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-104">There are three reasons to group controls.</span></span> <span data-ttu-id="9b8a9-105">Одна из них — визуальное группирование связанных элементов формы для простого пользовательского интерфейса; другой — программное группирование, например, переключатели. Последний — перемещение элементов управления как единицы во время разработки.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-105">One is visual grouping of related form elements for a clear user interface; another is programmatic grouping, of radio buttons for example; the last is for moving the controls as a unit at design time.</span></span>

## <a name="to-create-a-group-of-controls"></a><span data-ttu-id="9b8a9-106">Создание группы элементов управления</span><span class="sxs-lookup"><span data-stu-id="9b8a9-106">To create a group of controls</span></span>

1. <span data-ttu-id="9b8a9-107">Перетащите элемент управления <xref:System.Windows.Forms.Panel> с вкладки **Windows Forms** панели элементов на форму.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-107">Drag a <xref:System.Windows.Forms.Panel> control from the **Windows Forms** tab of the Toolbox onto a form.</span></span>

2. <span data-ttu-id="9b8a9-108">Добавьте на панель другие элементы управления, рисуя их внутри панели.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-108">Add other controls to the panel, drawing each inside the panel.</span></span>

     <span data-ttu-id="9b8a9-109">Если у вас есть элементы управления, которые необходимо заключить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.Panel> и вставить их на панель.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-109">If you have existing controls that you want to enclose in a panel, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.Panel> control, and then paste them into the panel.</span></span> <span data-ttu-id="9b8a9-110">Их также можно перетащить на панель.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-110">You can also drag them into the panel.</span></span>

3. <span data-ttu-id="9b8a9-111">Используемых Если вы хотите добавить на панель границу, задайте ее свойство <xref:System.Windows.Forms.BorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-111">(Optional) If you want to add a border to a panel, set its <xref:System.Windows.Forms.BorderStyle> property.</span></span> <span data-ttu-id="9b8a9-112">Существует три варианта: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>и <xref:System.Windows.Forms.BorderStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="9b8a9-112">There are three choices: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, and <xref:System.Windows.Forms.BorderStyle.None>.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b8a9-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9b8a9-113">See also</span></span>

- [<span data-ttu-id="9b8a9-114">Элемент управления Panel</span><span class="sxs-lookup"><span data-stu-id="9b8a9-114">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="9b8a9-115">Общие сведения об элементе управления Panel</span><span class="sxs-lookup"><span data-stu-id="9b8a9-115">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="9b8a9-116">Практическое руководство. Установка фона панели</span><span class="sxs-lookup"><span data-stu-id="9b8a9-116">How to: Set the Background of a Panel</span></span>](how-to-set-the-background-of-a-windows-forms-panel.md)
