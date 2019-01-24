---
title: Как выполнить Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
ms.openlocfilehash: dbcd814edb78c54ce5629a1a8761142674fe6135
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684623"
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Как выполнить Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
Наиболее распространенное использование <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемент управления является отображение связанных данных из базы данных или другого источника данных.  
  
 В дополнение к связанные элементы управления, вы можете добавить другие элементы управления, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе [Как Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Можно также привязать к источнику данных во время выполнения, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойства `True` и указав источник данных для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> свойство. В этом случае необходимо будет управлять всеми аспектами взаимодействия с источником данных. Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Чтобы создать DataRepeater привязкой к данным  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления из **Visual Basic PowerPacks** вкладке **элементов** в форму или контейнерный элемент управления.  
  
2.  Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.  
  
     Обратите внимание на то, что элемент управления имеет двух прямоугольников. Верхняя область — *шаблон элемента*; элементы управления, добавленные в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления во время выполнения. Нижняя область является *просмотра*, где отображаются элементы.  
  
     Можно также изменить размер и расположение элемента управления или шаблон элемента, изменив **размер** и **позиции** свойства в окне «Свойства».  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источников данных** окно пуст, добавьте в источник данных. Дополнительные сведения см. в разделе [Добавление новых источников данных](/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источников данных** окно, выберите узел верхнего уровня для таблицы, которая содержит данные, которые вы хотите выполнить привязку.  
  
5.  Измените тип удаления таблицы `Details` , щелкнув `Details` в раскрывающемся списке в узле таблицы.  
  
6.  Выберите узел таблицы и перетащите его в область шаблона элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления.  
  
     Можно указать, какие типы элементов управления отображаются для каждого поля. Дополнительные сведения см. в разделе [задать для элемента управления создается при перетаскивании из окна источников данных](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>См. также
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Практическое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Практическое руководство. Создать форму «основной/подробности» с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)
- [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
