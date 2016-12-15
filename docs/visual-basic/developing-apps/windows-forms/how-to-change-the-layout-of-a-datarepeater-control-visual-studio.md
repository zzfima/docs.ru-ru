---
title: "Практическое руководство. Изменение структуры элемента управления DataRepeater (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, изменение стиля макета"
  - "DataRepeater, изменение ориентации"
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Изменение структуры элемента управления DataRepeater (Visual Studio)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> можно отобразить либо вертикально \(элементы прокручиваются вертикально\), либо горизонтально \(элементы прокручиваются горизонтально\).  Можно изменить ориентацию на этапе разработки или во время выполнения, изменив свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>.  Если свойство <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> изменяется во время выполнения, можно также изменить размеры <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и расположение дочерних элементов управления.  
  
> [!NOTE]
>  При перемещении элементов управления на <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> во время выполнения, потребуется вызвать методы <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> в начале и в конце блока кода, отвечающего за перемещение элементов управления.  
  
### Чтобы изменить макет во время выполнения  
  
1.  В конструкторе Windows Forms выберите элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
    > [!NOTE]
    >  Необходимо выделить внешнюю границу элемента управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, нажав на нижнюю область этого элемента управления, а не на верхнюю область <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>.  
  
2.  В окне "Свойства" присвойте свойству <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> значение либо <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>, либо <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles>.  
  
### Чтобы изменить структуру во время выполнения  
  
1.  Добавьте следующий код в обработчик событий кнопки `Click`:  
  
     [!code-cs[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  В большинстве случаев, нужно будет добавить код, похожий на тот, который приведен в подразделе "Пример" для уменьшения размеров <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> и переупорядочения управляющих элементов для соответствия новой ориентации.  
  
## Пример  
 В следующем примере показан ответ на событие <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> в обработчике событий.  Для этого примера необходим элемент управления <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> с именем `DataRepeater1`, который находится в форме, и <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> содержит два элемента управления <xref:System.Windows.Forms.TextBox> с именами `TextBox1` и `TextBox2`.  
  
 [!code-cs[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## См. также  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>   
 [Общие сведения об элементе управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Устранение неполадок при использовании элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [Практическое руководство. Изменение внешнего вида элемента управления DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)