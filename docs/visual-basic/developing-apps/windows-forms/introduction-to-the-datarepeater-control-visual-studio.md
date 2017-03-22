---
title: "Общие сведения об элементе управления DataRepeater (Visual Studio) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 86078426494caabefc6bbfb036037007e830e1cb
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Общие сведения об элементе управления DataRepeater (Visual Studio)
Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления является прокручиваемым контейнером для элементов управления, отображающих повторяющиеся данные, например, строки в таблице базы данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Он может использоваться в качестве альтернативы <xref:System.Windows.Forms.DataGridView>управления, если требуется больший контроль над макет данных.</xref:System.Windows.Forms.DataGridView> <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>«Повторяет» группу связанных элементов управления путем создания нескольких экземпляров в области прокрутки.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Это позволяет пользователям видеть несколько записей одновременно.  
  
## <a name="overview"></a>Обзор  
 Во время разработки <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления состоит из двух разделов.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Внешний подраздел является *просмотра*, где просматриваемые данные будут отражены во время выполнения. Внутренний (верхний) подраздел, называемый *шаблона элемента*, в котором располагаются элементы управления, которые будут изображены во время выполнения, обычно один элемент управления для каждого поля в источнике данных. Свойства и элементы управления в шаблоне элемента инкапсулированы в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>свойство.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>  
  
 Во время выполнения <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>копируется в виртуальный <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>объект, используемый для отображения данных при каждой записи в области просмотра.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Можно настроить отображение индивидуальных записей в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>события, например, выделение поля на основе значения, которые она содержит.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Дополнительные сведения см. в разделе [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Наиболее часто используется для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>— элемент управления для отображения данных из таблицы базы данных или других связанных источников данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> В дополнение к [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] объектов данных <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления можно привязать к любой класс, реализующий <xref:System.Collections.IList>интерфейс (включая массивы), любой класс, реализующий <xref:System.ComponentModel.IListSource>интерфейс любой класс, реализующий <xref:System.ComponentModel.IBindingList>интерфейса или любой класс, реализующий <xref:System.ComponentModel.IBindingListView>интерфейса.</xref:System.ComponentModel.IBindingListView> </xref:System.ComponentModel.IBindingList> </xref:System.ComponentModel.IListSource> </xref:System.Collections.IList> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
### <a name="data-binding"></a>Привязка данных  
 Как правило, привязка данных выполняется путем перетаскивания полей из **источников данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Дополнительные сведения см. в разделе [Практическое руководство: отображение привязки данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 При работе с большими объемами данных, можно задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>Свойства `True` для отображения подмножества доступных данных.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> Виртуальный режим требует реализации кэша данных, из которого <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>заполнен, и необходимо контролировать все взаимодействия с кэшем данных во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Свободные элементы управления можно также отображать на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Например можно отобразить изображение, которое повторяется для каждого элемента. Дополнительные сведения см. в разделе [Практическое руководство: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>События  
 Наиболее важными для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>событие, возникающее при появлении нового элемента в представлении и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>событие, которое возникает, когда элемент выбран.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Можно использовать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>событий для изменения внешнего вида элемента.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Например можно выделить отрицательные значения. Используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>событий для доступа к значениям элементов управления, при выборе элемента.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Элемент управления предоставляет все события стандартный элемент управления в редакторе кода.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Тем не менее некоторые события не будет использовать. События клавиатуры и мыши например `KeyDown`, `Click`, и `MouseDown` не будет вызываться во время выполнения, поскольку <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>никогда не в сам элемент управления имеет фокус.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>Не предоставляет события во время разработки, так как он создается только во время выполнения.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Если требуется обрабатывать события клавиатуры и мыши, можно добавить <xref:System.Windows.Forms.Panel>управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>во время разработки и затем обрабатывать события для <xref:System.Windows.Forms.Panel>.</xref:System.Windows.Forms.Panel> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:System.Windows.Forms.Panel> Дополнительные сведения см. в разделе [Устранение неполадок управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Настройки  
 Существует много способов настройки внешнего вида и поведения <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>управления во время выполнения и во время разработки.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Свойства могут задаваться для изменения цветов, скрытия или изменения заголовков элементов, изменение ориентации с вертикальной на горизонтальную и многое другое. Дополнительные сведения см. в разделе [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [как: отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), и [как: изменение макета элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Обратите внимание, что некоторые свойства применяются для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>самого элемента управления в то время как другие относятся только к <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Убедитесь, что у вас есть правильный раздел выбранного перед заданием свойств элемента управления. Дополнительные сведения см. в разделе [Практическое руководство: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Другие настройки включают контроль за возможностью добавления и удаления записей, добавление возможностей поиска и отображение связанных данных в основном и подробном представлениях. Дополнительные сведения см. в разделе [как: отключение добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [как: поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), и [как: создание Главная и подчиненная формы с помощью двух элементов управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Пошаговое руководство: Отображение данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
