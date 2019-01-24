---
title: Как выполнить Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: a20e1ba83d1963bc3d4c135817767ee02fcbdeda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730793"
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Как выполнить Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
В дополнение к связанные элементы управления, может потребоваться добавить другие элементы управления для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
> [!NOTE]
>  Также необходимо иметь по крайней мере одним привязанным элементом управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> или ничего не будет отображаться во время выполнения.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Добавление несвязанных элементов управления DataRepeater  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.  
  
     Можно также изменить размер и положение этого элемента управления, изменив **размер** и **позиции** свойства в окне «Свойства».  
  
3.  Добавить по крайней мере один элемент управления с привязкой к данным в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе [Как Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Перетащите элемент управления с **элементов** область элемента шаблона <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
     Обратите внимание на то, что элемент управления имеет двух прямоугольников. Внутренняя область — *шаблон элемента*; элементы управления, добавленные в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время выполнения. Внешняя область является *просмотра*, где будут отображены элементы; элементы управления, добавленные в этот регион будет отображаться во время выполнения.  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Практическое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Создать форму «основной/подробности» с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
