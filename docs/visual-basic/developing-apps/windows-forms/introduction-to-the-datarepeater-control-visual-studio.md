---
title: "Общие сведения об элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater"
  - "DataRepeater, общие сведения"
  - "повторяющиеся данные"
ms.assetid: 78a52a1d-65f0-4ecb-97ff-53bc114300c5
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Общие сведения об элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Элемент управления пакетов Visual Basic Power Packs <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> является прокручиваемым контейнером для элементов управления, отображающих повторяющиеся данные, например строки таблицы базы данных.  Если требуется дополнительный контроль над размещением данных, этот элемент можно использовать в качестве альтернативы элемента управления <xref:System.Windows.Forms.DataGridView>.  "Дублирование" <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> группы связанных элементов управления путем создания нескольких экземпляров в области прокрутки.  Это позволяет пользователям видеть несколько записей в одно и то же время.  
  
## Общие сведения  
 На этапе разработки элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> состоит из двух подразделов.  Внешний подраздел является *окном просмотра*, в котором просматриваемые данные будут отражены во время выполнения.  Внутренний \(верхний\) подраздел, называемый *шаблон элемента*, в котором располагаются элементы управления, которые будут изображены во время выполнения; обычно один элемент управления соответствует одному полю в источнике данных.  Свойства и элементы управления в шаблоне элемента включены в свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.  
  
 Во время выполнения, <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> копируется в виртуальный объект <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>, который используется для отображения данных при просмотре каждой записи.  Можно настроить отображение индивидуальных записей в событии <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, например, выделение поля на основе содержащегося в нем значении.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Наиболее общее использование элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> — отображение данных из таблицы базы данных или других связанных источников данных.  В дополнение к объектам данных [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)], элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> можно привязать к любому классу \(включая массивы\), который реализует интерфейс <xref:System.Collections.IList>, любому классу, который реализует интерфейс <xref:System.ComponentModel.IListSource>, любому классу, который реализует интерфейс <xref:System.ComponentModel.IBindingList> или любому классу, который реализует интерфейс <xref:System.ComponentModel.IBindingListView>.  
  
### Привязка данных  
 Обычно, привязка данных выполняется при помощи перетаскивания полей из окна **Источники данных** в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Дополнительные сведения см. в разделе [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
 При работе с большими объемами данных можно задать для свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> значение `True`, чтобы отобразить подмножество доступных данных.  Виртуальный режим требует реализации кэша данных, из которого заполняется <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, следует также контролировать все взаимодействия с кэшем данным во время выполнения.  Дополнительные сведения см. в разделе [Виртуальные режим в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 Можно также отобразить несвязанные элементы управления в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Например, можно отобразить рисунок, который повторяется на каждом элементе.  Дополнительные сведения см. в разделе [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
### События  
 Наиболее важными для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> являются <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> событие, возникающее при появлении нового элемента в области просмотра и событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged>, возникающее при выделении элемента.  Можно использовать событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> для изменения внешнего вида элемента.  Например, можно выделить отрицательные значения.  Используйте событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndexChanged> для обращения к значениям элементов управления при выделении элементов.  
  
 Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> предоставляет все стандартные события элементов управления в редакторе кода.  Однако, некоторые события не следует использовать.  События клавиатуры и мыши, такие как `KeyDown`, `Click` и `MouseDown` не будут возникать во время выполнения, так как элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> никогда не фокусируется сам на себе.  
  
 Элемент <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> не предоставляет события на этапе разработки, так как он создается только во время выполнения.  Если необходимо обрабатывать события клавиатуры и мыши, можно добавить элемент управления <xref:System.Windows.Forms.Panel> в шаблон <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> на этапе разработки и затем обрабатывать события для <xref:System.Windows.Forms.Panel>.  Дополнительные сведения см. в разделе [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md).  
  
### Настройки  
 Есть много способов настроить поведение и внешний вид элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, как на этапе разработки, так и в процессе выполнения.  Можно настроить свойства для изменения цветов, скрытия или изменения заголовков элементов, изменения ориентации с вертикальной на горизонтальную и многое другое.  Дополнительные сведения см. в разделах [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md), [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) и [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md).  
  
 Обратите внимание, что некоторые свойства применяются к самому элементу управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, тогда как другие свойства применяются только к <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.  Убедитесь, что используется правильный подраздел выбранного элемента управления перед настройкой свойств.  Дополнительные сведения см. в разделе [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md).  
  
 Другие настройки включают контроль за возможностью добавления или удаления записей, добавление возможностей поиска и отображают связанные данные в основном и подробном представлениях.  Дополнительные сведения см. в разделах [Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md), [Практическое руководство. Поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) и [Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md).  
  
## См. также  
 [Элемент управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)