---
title: Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: b96fb33a0dcf80a86d1fcb6e219e5f35b1f7351c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589871"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
Чаще всего используют <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — элемент управления для отображения связанных данных из базы данных или другого источника данных.  
  
 Помимо связанные элементы управления, вы можете добавить другие элементы управления, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе [как: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Можно также привязать к источнику данных во время выполнения, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойства `True` и назначения для источника данных <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> свойство. В этом случае необходимо управлять всеми аспектами взаимодействия с источником данных. Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Чтобы создать DataRepeater с привязкой к данным  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.  
  
     Обратите внимание, что элемент управления имеет двух прямоугольников. Верхняя область — *шаблона элемента*; элементы управления, добавленные в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время выполнения. Нижняя область является *просмотра*, в котором будут отображены элементы.  
  
     Можно также изменить размер и расположение элемента управления или шаблон элемента, изменив **размер** и **позиции** свойств в окне «Свойства».  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источники данных** окно пусто, добавьте в источник данных. Дополнительные сведения см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источники данных** окно, выберите узел верхнего уровня для таблицы, которая содержит данные, которые необходимо выполнить привязку.  
  
5.  Измените тип удаления таблицы `Details` , щелкнув `Details` в раскрывающемся списке в узле таблицы.  
  
6.  Выберите узел таблицы и перетащите его в область шаблона элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
     Можно указать, какие типы элементов управления отображаются для каждого поля. Дополнительные сведения см. в разделе [задать элемент управления, создаваемого при перетаскивании из окна источников данных](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Как: создать Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
