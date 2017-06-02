---
title: "Общие сведения об элементе управления TrackBar (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TrackBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления "Ползунок", сведения об элементах управления "Ползунок""
  - "ползунки, сведения о ползунках"
  - "TrackBar - элемент управления [Windows Forms], сведения об элементе управления TrackBar"
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Общие сведения об элементе управления TrackBar (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.TrackBar> \(известный также как элемент управления "Ползунок"\) используется для просмотра сведений большого объема или для визуальной настройки числовых параметров.  Элемент управления <xref:System.Windows.Forms.TrackBar> состоит из двух частей: ползунка и делений.  Ползунок служит средством настройки компонента.  Его положение соответствует свойству <xref:System.Windows.Forms.TrackBar.Value%2A>.  Деления представляют собой визуальные отметки, расположенные через равные интервалы.  Ползунок перемещается по шагам, задаваемым разработчиком; его можно расположить по вертикали или по горизонтали.  Ползунок можно использовать, например, для управления частотой мерцания курсора или скоростью мыши в системе.  
  
## Ключевые свойства  
 Ключевыми свойствами элемента управления <xref:System.Windows.Forms.TrackBar> являются <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A> и <xref:System.Windows.Forms.TrackBar.Maximum%2A>.  <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> определяет интервалы между делениями.  <xref:System.Windows.Forms.TrackBar.Minimum%2A> и <xref:System.Windows.Forms.TrackBar.Maximum%2A> являются наименьшим и наибольшим значениями, которые можно представить в области ползунка.  
  
 Два других важных свойства это <xref:System.Windows.Forms.TrackBar.SmallChange%2A> и <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.  Значением свойства <xref:System.Windows.Forms.TrackBar.SmallChange%2A> является число делений, на которое перемещается ползунок при нажатии клавиши со стрелкой ВЛЕВО или ВПРАВО.  Значением свойства <xref:System.Windows.Forms.TrackBar.LargeChange%2A> является число делений, на которое перемещается бегунок при нажатии клавиши PAGE UP или PAGE DOWN или при щелчке кнопкой мыши по шкале ползунка справа или слева от него.  
  
## См. также  
 <xref:System.Windows.Forms.TrackBar>   
 [Элемент управления TrackBar](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)