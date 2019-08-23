---
title: Практическое руководство. Закрепление элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963629"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Практическое руководство. Закрепление элементов управления в формах Windows Forms
Можно закреплять элементы управления на краях формы или заполнять их контейнером элемента управления (формой или контейнерным элементом управления). Например, проводник закрепляет свой <xref:System.Windows.Forms.TreeView> элемент управления в левой части окна, а его <xref:System.Windows.Forms.ListView> элемент управления — в правой части окна. <xref:System.Windows.Forms.Control.Dock%2A> Используйте свойство для всех видимых Windows Forms элементов управления, чтобы определить режим закрепления.  
  
> [!NOTE]
> Элементы управления закрепляются в обратном z-порядке.  
  
 Свойство взаимодействует со <xref:System.Windows.Forms.Control.AutoSize%2A>свойством. <xref:System.Windows.Forms.Control.Dock%2A> Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Закрепление элемента управления  
  
1. Выберите элемент управления, который требуется закрепить.  
  
2. В окно свойств щелкните стрелку справа от <xref:System.Windows.Forms.Control.Dock%2A> свойства.  
  
     Отобразится редактор, показывающий ряд прямоугольников, представляющих края и центр формы.  
  
3. Нажмите кнопку, представляющую границу формы, в которой необходимо закрепить элемент управления. Чтобы заполнить содержимое формы элемента управления или элемента управления контейнера, щелкните центральную рамку. Щелкните **(нет)** , чтобы отключить закрепление.  
  
     Размер элемента управления автоматически изменяется в соответствии с границами закрепленной границы.  
  
    > [!NOTE]
    > Наследуемые элементы `Protected` управления должны быть закрепленными. Чтобы изменить уровень доступа элемента управления, установите его свойство **Modifiers** в окно свойств.  
  
## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Упорядочение элементов управления в формах Windows Forms](arranging-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Привязка элементов управления к Windows Forms](how-to-anchor-controls-on-windows-forms.md)
