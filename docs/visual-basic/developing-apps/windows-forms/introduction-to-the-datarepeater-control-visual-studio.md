---
title: "Общие сведения об элементе управления DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- repeating data
- DataRepeater, overview
- DataRepeater
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 699876cc568b22114e5ed8741c2fd0c053a137af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="introduction-to-the-datarepeater-control-visual-studio"></a>Общие сведения об элементе управления DataRepeater (Visual Studio)
Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> из Visual Basic Power Pack является прокручиваемым контейнером для элементов управления, отображающих повторяющиеся данные, например строки в таблице базы данных. Его можно использовать в качестве альтернативы элементу управления <xref:System.Windows.Forms.DataGridView> , если требуется больший контроль над макетом данных. <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> «Повторяет» группу связанных элементов управления путем создания нескольких экземпляров в области прокрутки. Это позволяет пользователям просматривать несколько записей одновременно.  
  
## <a name="overview"></a>Обзор  
 Во время разработки <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления состоит из двух разделов. Внешний подраздел является *просмотра*, где просматриваемые данные будут отображаться во время выполнения. Внутренний (верхний) подраздел, называемый *шаблона элемента*, в котором располагаются элементы управления, которые будут повторены во время выполнения, обычно один элемент управления для каждого поля в источнике данных. Свойства и элементы управления в шаблоне элемента, инкапсулированы в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> свойство.  
  
 Во время выполнения <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> копируется в виртуальный <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> объект, используемый для отображения данных, при каждой записи в области просмотра. Можно настроить внешний вид отдельных записей в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> события, например, выделение поля на основе значения, которые она содержит. Дополнительные сведения см. в разделе [как: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Чаще всего используют для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — элемент управления для отображения данных из таблицы базы данных или других связанных источников данных. В дополнение к [!INCLUDE[vstecado](~/includes/vstecado-md.md)] объектов данных <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления можно привязать к любой класс, реализующий <xref:System.Collections.IList> интерфейс (включая массивы), любой класс, реализующий <xref:System.ComponentModel.IListSource> интерфейс любой класс, реализующий <xref:System.ComponentModel.IBindingList> интерфейс или любой класс, реализующий <xref:System.ComponentModel.IBindingListView> интерфейса.  
  
### <a name="data-binding"></a>Привязка данных  
 Как правило, привязка данных перетаскиванием поля из **источники данных** окна на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Дополнительные сведения см. в разделе [как: отображение привязки данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 При работе с большими объемами данных, можно задать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> свойства `True` для отображения подмножества доступных данных. Виртуальный режим требует реализации кэша данных, из которой <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> заполнен, и необходимо контролировать все взаимодействия с кэшем данных во время выполнения. Дополнительные сведения см. в разделе [виртуальный режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Можно также отобразить несвязанных элементов управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> элемента управления. Например можно отобразить изображение, которое повторяется для каждого элемента. Дополнительные сведения см. в разделе [как: отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### <a name="events"></a>События  
 Наиболее важными для <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие, возникающее при появлении нового элемента в представлении и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> событие, которое возникает, когда элемент выбран. Можно использовать <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событий для изменения внешнего вида элемента. Например можно выделить отрицательные значения. Используйте <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> событий для доступа к значений элементов управления, когда элемент выбран.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Элемент управления предоставляет все события стандартный элемент управления в редакторе кода. Тем не менее некоторые события не можно использовать. События клавиатуры и мыши например `KeyDown`, `Click`, и `MouseDown` не будет вызываться во время выполнения, так как <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> никогда не в сам элемент управления имеет фокус.  
  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> Не предоставляет события во время разработки, так как он создается только во время выполнения. Если вы хотите обрабатывать события клавиатуры и мыши, можно добавить <xref:System.Windows.Forms.Panel> управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> во время разработки и затем обрабатывать события для <xref:System.Windows.Forms.Panel>. Дополнительные сведения см. в разделе [Устранение неполадок управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### <a name="customizations"></a>Настройки  
 Существует много способов настройки внешнего вида и поведения <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> управления во время выполнения и во время разработки. Свойства могут задаваться для изменения цветов, скрытия или изменения заголовков элементов, изменить ориентацию с вертикальной на горизонтальную и многое другое. Дополнительные сведения см. в разделе [как: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [как: отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md), и [как: изменение макета Элемент управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Обратите внимание, что некоторые свойства применяются к <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> самого элемента управления в то время как другие относятся только к <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>. Убедитесь, что имеется правильный раздел выбранного перед заданием свойств элемента управления. Дополнительные сведения см. в разделе [как: изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Другие настройки включают контроль возможность добавления или удаления записей, добавление возможностей поиска и отображения связанных данных в формате главных и подчиненных. Дополнительные сведения см. в разделе [как: отключение добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [как: поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md), и [как: создание Главная и подчиненная формы с помощью двух Элементы управления DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)  
 [Пошаговое руководство. Отображение данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)  
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
