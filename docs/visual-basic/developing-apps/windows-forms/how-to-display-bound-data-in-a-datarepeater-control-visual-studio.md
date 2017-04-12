---
title: "Практическое руководство: отображение связанных данных в элементе управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9bf8f2f5fcc4dfa2b29e368a4e26bf112e08149e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater (Visual Studio)
Наиболее распространенное использование <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>является элемент управления для отображения связанных данных из базы данных или другого источника данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Помимо связанные элементы управления, можно добавить другие элементы управления, такие как статическая метка или изображение, которое повторяется для каждого элемента в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Дополнительные сведения см. в разделе [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Можно также привязать к источнику данных во время выполнения, задав <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Свойства `True` и источника данных в назначение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>свойство.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> В этом случае необходимо управлять всеми аспектами взаимодействия с источником данных. Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Чтобы создать DataRepeater с привязкой к данным  
  
1.  Перетащите <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления из **Visual Basic PowerPacks** вкладке **элементов** форму или контейнерный элемент управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Перетащите маркеры изменения размера и положения размер и положение этого элемента управления.  
  
     Обратите внимание, что элемент управления имеет двух прямоугольников. Верхняя область — *шаблона элемента*; элементы управления, добавляемые в шаблон будет повторяться в каждом элементе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>элемента управления во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Нижняя область является *просмотра*, в котором будут отображены элементы.  
  
     Можно также изменить размер и расположение элемента управления или шаблон элемента, изменив **размер** и **позиции** свойства в окне «Свойства».  
  
3.  В меню **Данные** выберите команду **Показать источники данных**.  
  
    > [!NOTE]
    >  Если **источников данных** окно пусто, добавьте в источник данных. Дополнительные сведения см. в разделе [добавить новые источники данных](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  В **источников данных** окно, выберите узел верхнего уровня для таблицы, которая содержит данные, которые необходимо выполнить привязку.  
  
5.  Измените тип удаления таблицы `Details` , щелкнув `Details` в раскрывающемся списке узла таблицы.  
  
6.  Выберите узел таблицы и перетащите его в область шаблона элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Можно указать, какие типы элементов управления отображаются для каждого поля. Дополнительные сведения см. в разделе [задать элемент управления, создаваемый при перетаскивании из окна источников данных](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство: создание Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
