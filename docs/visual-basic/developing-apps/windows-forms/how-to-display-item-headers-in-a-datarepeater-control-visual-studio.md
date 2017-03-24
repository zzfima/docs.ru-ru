---
title: "Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, заголовки элементов"
  - "DataRepeater, индикаторы выделения"
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Пошаговое руководство. Отображение заголовков элементов в элементе управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Заголовок элемента в элементе управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> предоставляет визуальный индикатор при выборе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> имеет значение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> \(значение по умолчанию\), заголовок элемента отображается слева от каждого элемента.  Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> имеет значение <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>, заголовок элемента отображается сверху от каждого элемента.  
  
 При первоначальном выборе заголовок элемента отображается в цвете, определенном свойством <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>, также отображается белый значок со стрелкой.  
  
> [!NOTE]
>  Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> имеет значение <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будет отображаться.  
  
 Когда поле <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> находится в фокусе, цвет заголовка элемента изменяет цвет фона на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и цвет значка со стрелкой на черный.  Если данные изменены, в заголовке элемента отображается символ карандаша.  
  
 Ширина по умолчанию \(или высота, если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> установлено равным <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>\) заголовка элемента равна 15 пикселям.  Можно изменить ширину, используя свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>.  
  
> [!NOTE]
>  Если значение свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> меньше 11, значки индикатора не отображаются в заголовке элемента.  
  
 Можно скрыть заголовок элемента, установив значение свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> равным **False**.  Когда <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> установлено равным **False**, индикатором того, что элемент выделен, является пунктирная линия по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  Можно предоставить свой собственный индикатор выделения, управляя свойством <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> в событии <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### Изменение внешнего вида заголовков элементов  
  
1.  В конструкторе Windows Forms выберите нижнюю область управляющего элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Следует выбрать нижнюю область элемента управления.  При выборе области шаблона элемента в окне "Свойства" появится другой набор свойств.  
  
2.  В окне "Свойства" используйте свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> для изменения цвета текста в данном заголовке элемента.  
  
    > [!NOTE]
    >  Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> имеет значение <xref:System.Drawing.Color.White%2A>, при первоначальном выборе элемента символ выделения не будет отображаться.  
  
3.  Используйте свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> для изменения ширины \(или высоты\) заголовков элементов.  
  
    > [!NOTE]
    >  Если значение свойства <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> меньше 11, значки индикатора не отображаются в заголовке элемента.  
  
### Чтобы скрыть заголовки элементов  
  
1.  В конструкторе Windows Forms выберите нижнюю область управляющего элемента <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Следует выбрать нижнюю область элемента управления.  При выборе области шаблона элемента в окне "Свойства" появится другой набор свойств.  
  
2.  В окне "Свойства" присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> значение **False**.  
  
     Когда выбран элемент<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, единственным индикатором этого является пунктирная линия по периметру <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение структуры элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)