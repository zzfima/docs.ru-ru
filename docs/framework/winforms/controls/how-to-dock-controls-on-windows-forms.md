---
title: Закрепление элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745519"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Как закреплять элементы управления на Windows Forms

Можно закреплять элементы управления на краях формы или заполнять их контейнером элемента управления (формой или контейнерным элементом управления). Например, проводник закрепляет свой <xref:System.Windows.Forms.TreeView> элемент управления в левой части окна, а элемент управления <xref:System.Windows.Forms.ListView> — в правой части окна. Используйте свойство <xref:System.Windows.Forms.Control.Dock%2A> для всех видимых Windows Forms элементов управления, чтобы определить режим закрепления.

> [!NOTE]
> Элементы управления закрепляются в обратном z-порядке.

Свойство <xref:System.Windows.Forms.Control.Dock%2A> взаимодействует со свойством <xref:System.Windows.Forms.Control.AutoSize%2A>. Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).

## <a name="to-dock-a-control"></a>Закрепление элемента управления

1. В Visual Studio выберите элемент управления, который необходимо закрепить.

2. В окне **Свойства** щелкните стрелку справа от свойства <xref:System.Windows.Forms.Control.Dock%2A>.

   Отобразится редактор, показывающий ряд прямоугольников, представляющих края и центр формы.

3. Нажмите кнопку, представляющую границу формы, в которой необходимо закрепить элемент управления. Чтобы заполнить содержимое формы элемента управления или элемента управления контейнера, щелкните центральную рамку. Щелкните **(нет)** , чтобы отключить закрепление.

   Размер элемента управления автоматически изменяется в соответствии с границами закрепленной границы.

   > [!NOTE]
   > Наследуемые элементы управления должны быть `Protected`, чтобы их можно было закрепить. Чтобы изменить уровень доступа элемента управления, установите его свойство **Modifiers** в окне **свойства** .

## <a name="see-also"></a>См. также:

- [Элементы управления Windows Forms](index.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
- [Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Привязка элементов управления в формах Windows Forms](how-to-anchor-controls-on-windows-forms.md)
