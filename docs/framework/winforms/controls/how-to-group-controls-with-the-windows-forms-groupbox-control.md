---
title: Практическое руководство. Группа элементов управления с помощью элемента управления GroupBox в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: 14c832251a76eaff21611c88179c4d2ffa7ab738
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708560"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="6d63e-102">Практическое руководство. Группа элементов управления с помощью элемента управления GroupBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6d63e-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="6d63e-103">Windows Forms <xref:System.Windows.Forms.GroupBox> элементы управления используются для группировки других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6d63e-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="6d63e-104">Существуют три причины для группировки элементов управления:</span><span class="sxs-lookup"><span data-stu-id="6d63e-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="6d63e-105">Чтобы создать визуальную группировку элементов связанных форм для упрощения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6d63e-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="6d63e-106">Чтобы создать программный группирование (переключателей, например).</span><span class="sxs-lookup"><span data-stu-id="6d63e-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="6d63e-107">Перемещение элементов управления как единое целое во время разработки.</span><span class="sxs-lookup"><span data-stu-id="6d63e-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="6d63e-108">Чтобы создать группу элементов управления</span><span class="sxs-lookup"><span data-stu-id="6d63e-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="6d63e-109">Рисование <xref:System.Windows.Forms.GroupBox> управления на форме.</span><span class="sxs-lookup"><span data-stu-id="6d63e-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="6d63e-110">Добавьте другие элементы управления «группы», рисования каждого элемента внутри поля группы.</span><span class="sxs-lookup"><span data-stu-id="6d63e-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="6d63e-111">Если у вас есть существующие элементы управления, которые вы хотите включить в группу, можно выбрать все элементы управления, вырезать их в буфер обмена, выберите <xref:System.Windows.Forms.GroupBox> управления, а затем вставьте их в группу.</span><span class="sxs-lookup"><span data-stu-id="6d63e-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="6d63e-112">Также можно перетащить их в группу.</span><span class="sxs-lookup"><span data-stu-id="6d63e-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="6d63e-113">Задайте <xref:System.Windows.Forms.GroupBox.Text%2A> свойство поля группы, соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="6d63e-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d63e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6d63e-114">See also</span></span>
- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="6d63e-115">Элемент управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="6d63e-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
