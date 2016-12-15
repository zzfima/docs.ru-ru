---
title: "Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, устранение неполадок"
ms.assetid: c0ab9469-eced-4f52-aa18-4bd8dd4f1a9a
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Устранение неполадок при использовании элемента управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В данном разделе перечислены типичные проблемы, которые могут произойти при работе с элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
## Не происходят события клавиатуры и мыши для элемента управления DataRepeater  
 Некоторые события элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> такие, как события клавиатуры и мыши, не вызываются.  Это предусмотрено разработчиками.  Сам управляющий элемент <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> является контейнером для объектов <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> и к нему нельзя обратиться во время выполнения.  Элемент <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> не предоставляет события на этапе разработки.  Следовательно, щелчок по элементу или нажатие клавиши не вызовет события, если элемент находится в фокусе.  
  
 Исключение происходит, если свойство <xref:System.Windows.Forms.Control.Padding%2A> имеет большее значение, чем это позволено границами элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  В этом случае щелчок на предоставленном поле вызывает события мыши.  
  
 Чтобы устранить эту проблему, добавьте элемент управления <xref:System.Windows.Forms.Panel> в область <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> и затем добавьте остальные элементы управления в <xref:System.Windows.Forms.Panel>.  Можно добавить код в обработчик события элемента управления <xref:System.Windows.Forms.Panel> для событий мыши и клавиатуры.  
  
## Элемент управления DataRepeater частично скрыт навигатором привязки  
 При первоначальном добавлении элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> на форму и последующего добавления элементов управления с привязкой к данным из окна **Источники данных**, элемент управления <xref:System.Windows.Forms.BindingNavigator> может происходить над элементом управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Это известное ограничение окна **Источники данных** и оно согласуется с поведением остальных элементов управления, таких как элемент управления <xref:System.Windows.Forms.DataGridView>.  
  
 Можно также на этапе разработки поместить <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ниже, чем элемент управления <xref:System.Windows.Forms.BindingNavigator> или добавить код аналогичный следующему коду в обработчик событий `Load`.  
  
```vb#  
DataRepeater1.Top = ProductsBindingNavigator.Height  
```  
  
```c#  
dataRepeater1.Top = productsBindingNavigator.Height;  
```  
  
## Элементы управления отображаются некорректно во время выполнения  
 Некоторые элементы управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> могут отображаться во время выполнения не так, как ожидалось.  Процесс, использующийся для копирования элементов управления из <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> в <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> не может всегда определять свойства всех элементов управления.  Например, если добавить несвязанный элемент управления <xref:System.Windows.Forms.ListBox> в элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> на этапе разработки и заполнить его коллекцию <xref:System.Windows.Forms.ListBox.Items%2A> списком строк, <xref:System.Windows.Forms.ListBox> будет пустым все время выполнения.  Это происходит из\-за того, что в процессе клонирования нельзя учесть свойство <xref:System.Windows.Forms.ListBox.Items%2A>.  
  
 Такие проблемы как эта можно устранить, восстановив потерянные свойства в событии <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>, которое возникает после того, как клонирование по умолчанию завершено.  В следующем примере показано восстановление коллекции <xref:System.Windows.Forms.ListBox.Items%2A> элемента управления <xref:System.Windows.Forms.ListBox> в обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemCloned>.  
  
 [!code-cs[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/troubleshooting-the-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterItemCloned#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/troubleshooting-the-datarepeater-control-visual-studio_1.vb)]  
  
## Потерян символ выделения заголовка элемента  
 При изменении свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> заголовка элемента в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, выбор некоторых цветов может вызвать исчезновение символа выделения.  Изменение свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> также может вызвать потерю символа выделения.  
  
 Цвет и размер символа выделения нельзя изменять.  
  
-   Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> имеет значение <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будет отображаться.  
  
-   Если свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> присвоено значение <xref:System.Drawing.Color.Black%2A>, то символ выделения не будет виден при выделении элемента управления, и в режиме редактирования не будет виден символ карандаша.  
  
-   Если значение свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> меньше 11, значки индикатора не отображаются в заголовке элемента.  
  
 Можно предоставить свои собственные заголовок элемента и символ выделения, используя элемент управления <xref:System.Windows.Forms.PictureBox> и управляя свойством <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в событии <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
## См. также  
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Запрещение возможности добавления и удаления элементов DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)   
 [Практическое руководство. Поиск данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Создание главного и подчиненного представлений данных с использованием двух элементов управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)