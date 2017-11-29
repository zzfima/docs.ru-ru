---
title: "Практическое руководство. Закрепление элементов управления в формах Windows Forms."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4897a195dcafb8264bbab619f1a46118a829f44e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Практическое руководство. Закрепление элементов управления в формах Windows Forms.
Можно закрепить элементы управления по границам формы или их заполнения контейнера элемента управления (форму или контейнерный элемент управления). Например, проводник закрепляет его <xref:System.Windows.Forms.TreeView> в левой части окна элемента управления и его <xref:System.Windows.Forms.ListView> элемента управления в правой части окна. Используйте <xref:System.Windows.Forms.Control.Dock%2A> свойство для всех видимых элементов управления Windows Forms для определения режима закрепления.  
  
> [!NOTE]
>  Элементы управления закрепляются в обратном z порядке.  
  
 <xref:System.Windows.Forms.Control.Dock%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство. Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Чтобы закрепить элемент управления  
  
1.  Выберите элемент управления, который требуется закрепить.  
  
2.  В окне «Свойства» щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойство.  
  
     Откроется редактор, показывающий набор полей, соответствующих краям и центру формы.  
  
3.  Нажмите кнопку, которая представляет края формы, в которой вы хотите закрепить элемент управления. Чтобы заполнить содержимое элемента управления в форму или контейнерный элемент управления, щелкните поле center. Нажмите кнопку **(нет)** для запрещения закрепления.  
  
     Элемент управления изменяется автоматически в соответствии с границами закрепленной позиции.  
  
    > [!NOTE]
    >  Наследуемые элементы управления должны быть `Protected` могли быть закреплено. Чтобы изменить уровень доступа элемента управления, установите его **модификатор** в окне свойств.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
