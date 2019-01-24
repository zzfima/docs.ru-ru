---
title: Как выполнить Закрепление элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: f4a9d3bcf7f9db1634da2b2f06177c05061af28e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733549"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Как выполнить Закрепление элементов управления в формах Windows Forms
Вы можете закрепление элементов управления по границам формы или заполнить ими контейнера элемента управления (форму или контейнерный элемент управления). Например, Windows Explorer закрепляет его <xref:System.Windows.Forms.TreeView> элемента управления в левой части окна и его <xref:System.Windows.Forms.ListView> элемента управления в правой части окна. Используйте <xref:System.Windows.Forms.Control.Dock%2A> свойство для всех видимых элементов управления Windows Forms для определения режима закрепления.  
  
> [!NOTE]
>  Элементы управления закрепляются в обратном z порядке.  
  
 <xref:System.Windows.Forms.Control.Dock%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство. Дополнительные сведения см. в разделе [Общие](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Чтобы закрепить элемент управления  
  
1.  Выберите элемент управления, который требуется закрепить.  
  
2.  В окне «Свойства» щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойство.  
  
     Отображается редактор, показывающий набор полей, соответствующих краям и центру формы.  
  
3.  Нажмите кнопку, представляющий границы формы, в которой вы хотите закрепить элемент управления. Чтобы заполнить содержимое формы элемента управления или контейнерный элемент управления, щелкните поле center. Нажмите кнопку **(нет)** для запрещения закрепления.  
  
     Элемент управления изменяется автоматически в соответствии с границами закрепленной позиции.  
  
    > [!NOTE]
    >  Наследуемые элементы управления должны быть `Protected` могла быть закреплено. Чтобы изменить уровень доступа для элемента управления, установите его **модификатор** свойства в окне «Свойства».  
  
## <a name="see-also"></a>См. также
- [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)
- [Упорядочение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Свойство AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
- [Практическое руководство. Привязка элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
