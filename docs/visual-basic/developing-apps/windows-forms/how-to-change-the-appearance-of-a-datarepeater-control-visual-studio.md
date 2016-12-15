---
title: "Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, изменение внешнего вида во время выполнения"
  - "DataRepeater, настройка"
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Изменение внешнего вида элемента управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Внешний вид элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> можно изменить во время разработки путем настройки свойств или во время выполнения при помощи обработки события <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>.  
  
 Свойства, установленные во время разработки при выборе подраздела шаблонов элементов управляющего элемента, будут повторены для каждого элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> во время выполнения.  Связанные с внешним видом свойства элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> будут видны во время выполнения только в том случае, если часть контейнера останется открытой \(например, если свойство <xref:System.Windows.Forms.Control.Padding%2A> устанавливает максимальное значение\).  
  
 Во время выполнения свойства, связанные с отображением, можно установить в зависимости от ситуации.  Например, в приложении по планированию можно изменить цвет фона элемента для предупреждения пользователей о просроченных элементах.  В обработчике событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>, если значение свойства задается в условном операторе, например, `If…Then`, необходимо также использовать предложение `Else`, чтобы указать вид элемента, если условие не будет выполнено.  
  
### Чтобы изменить внешний вид во время разработки  
  
1.  В конструкторе Windows Forms выберите вверху область шаблона элемента для управляющего элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
2.  В окне "Свойства" выберите свойство и измените его значение.  Общие свойства, влияющие на внешний вид, включая <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A> и <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### Чтобы изменить внешний вид во время выполнения  
  
1.  В редакторе кода в раскрывающемся списке "Событие" выберите **DrawItem**.  
  
2.  В обработчик событий <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> добавьте код, чтобы установить свойства:  
  
     [!code-cs[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## Пример  
 Некоторые стандартные настройки для элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> включают возможности отображения строк различными цветами и изменения цвета поля на основе условия.  Выполнение этих настроек показано в следующем примере.  Пример предполагает наличие элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, привязанного к таблице "Продукты" в базе данных Northwind  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-cs[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Обратите внимание, что для всех этих настроек следует предоставить код, чтобы установить свойства в зависимости от значения условия.  Если условие `Else` не указано, во время выполнения могут возникнуть непредсказуемые результаты.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение связанных данных в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение несвязанных элементов управления в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)