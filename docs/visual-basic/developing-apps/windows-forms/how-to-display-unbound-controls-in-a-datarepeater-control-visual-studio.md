---
title: Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
ms.openlocfilehash: 698e518a4ed10ed6cf14ccafc6833b1acf8752db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater (Visual Studio)
Помимо связанные элементы управления, вы можете добавить другие элементы управления для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
> [!NOTE]
>  Также необходимо иметь по крайней мере один связанный элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> или ничего не будет отображаться во время выполнения.  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a>Добавление несвязанных элементов управления DataRepeater  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.  
  
     Можно также изменить размер и расположение элемента управления, изменив **размер** и **позиции** свойств в окне «Свойства».  
  
3.  Добавьте по крайней мере один элемент управления с привязкой к данным в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе [как: отображение привязки данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Перетащите элемент управления с **элементов** область шаблона элемента из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
     Обратите внимание, что элемент управления имеет двух прямоугольников. Внутренняя область — *шаблона элемента*; элементы управления, добавленные в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время выполнения. Внешняя область является *просмотра*, где будут отображены элементы; элементы управления, добавленные к этой области будет отображаться во время выполнения.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
