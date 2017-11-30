---
title: "Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50d29de04b4e221105bb02e58de01344f13af69f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="3c1d1-102">Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c1d1-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="3c1d1-103">Windows Forms <xref:System.Windows.Forms.GroupBox> элементы управления используются для группировки других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="3c1d1-104">Существует три причины для группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="3c1d1-105">Чтобы создать визуальную группировку связанных элементов форм для упрощения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="3c1d1-106">Создание программной группировки (переключатели, например).</span><span class="sxs-lookup"><span data-stu-id="3c1d1-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="3c1d1-107">Перемещение элементов управления как единое целое, во время разработки.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="3c1d1-108">Чтобы создать группу элементов управления</span><span class="sxs-lookup"><span data-stu-id="3c1d1-108">To create a group of controls</span></span>  
  
1.  <span data-ttu-id="3c1d1-109">Рисование <xref:System.Windows.Forms.GroupBox> элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="3c1d1-110">Добавьте другие элементы управления в поле группы, рисования каждого элемента внутри группы.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="3c1d1-111">При наличии существующих элементов управления, которые надо включить в группу, можно выбрать все элементы управления, вырезать их в буфер обмена, выберите <xref:System.Windows.Forms.GroupBox> управления, а затем вставьте их в группу.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="3c1d1-112">Также можно перетащить их в группу.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-112">You can also drag them into the group box.</span></span>  
  
3.  <span data-ttu-id="3c1d1-113">Задать <xref:System.Windows.Forms.GroupBox.Text%2A> свойства поля группы, соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="3c1d1-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1d1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3c1d1-114">See Also</span></span>  
 <xref:System.Windows.Forms.GroupBox>  
 [<span data-ttu-id="3c1d1-115">Элемент управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="3c1d1-115">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)
