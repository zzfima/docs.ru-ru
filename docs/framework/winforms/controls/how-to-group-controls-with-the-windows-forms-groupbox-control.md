---
title: Группирование элементов управления с помощью элемента управления GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: bb7476c410d2802b5d32cc9842a778f290765e32
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736648"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="84e75-102">Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="84e75-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="84e75-103">Windows Forms элементы управления <xref:System.Windows.Forms.GroupBox> используются для группирования других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="84e75-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="84e75-104">Существуют три причины группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="84e75-104">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="84e75-105">Для создания визуального группирования связанных элементов формы для простого пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="84e75-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="84e75-106">Для создания программного группирования (например, для переключателей).</span><span class="sxs-lookup"><span data-stu-id="84e75-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="84e75-107">Для перемещения элементов управления как единицы во время разработки.</span><span class="sxs-lookup"><span data-stu-id="84e75-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="84e75-108">Создание группы элементов управления</span><span class="sxs-lookup"><span data-stu-id="84e75-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="84e75-109">Нарисуйте элемент управления <xref:System.Windows.Forms.GroupBox> в форме.</span><span class="sxs-lookup"><span data-stu-id="84e75-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="84e75-110">Добавьте в поле группы другие элементы управления, нарисовав их внутри поля группы.</span><span class="sxs-lookup"><span data-stu-id="84e75-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="84e75-111">Если имеются существующие элементы управления, которые необходимо заключить в поле группы, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать элемент управления <xref:System.Windows.Forms.GroupBox> и вставить их в поле Группа.</span><span class="sxs-lookup"><span data-stu-id="84e75-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="84e75-112">Их также можно перетащить в поле Группа.</span><span class="sxs-lookup"><span data-stu-id="84e75-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="84e75-113">Задайте для свойства <xref:System.Windows.Forms.GroupBox.Text%2A> поля группы соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="84e75-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e75-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84e75-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="84e75-115">Элемент управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="84e75-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
