---
title: "Общие сведения об элементе управления TrackBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a>Общие сведения об элементе управления TrackBar (Windows Forms)
Windows Forms <xref:System.Windows.Forms.TrackBar> управления (иногда называют также элемент управления «ползунок») используется для просмотра данные большого объема или для визуальной настройки числовых параметров. <xref:System.Windows.Forms.TrackBar> Управления состоит из двух частей: ползунка и делений. Бегунка входит в состав, которое может быть настроено. Его положение соответствует <xref:System.Windows.Forms.TrackBar.Value%2A> свойство. Деления — это визуальные индикаторы, расположенные через равные промежутки времени. Ползунок перемещается с шагом, которые могут быть выровнены по горизонтали или вертикали. Например можно использовать для управления мерцания курсора скорость или мыши скорости для системы полосы прокрутки.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевые свойства <xref:System.Windows.Forms.TrackBar> управления <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, и <xref:System.Windows.Forms.TrackBar.Maximum%2A>. <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>является меткой импульсов. <xref:System.Windows.Forms.TrackBar.Minimum%2A>и <xref:System.Windows.Forms.TrackBar.Maximum%2A> являются наименьшим и наибольшим значениями, которые могут быть представлены на полосе ползунка.  
  
 Два важных свойства: <xref:System.Windows.Forms.TrackBar.SmallChange%2A> и <xref:System.Windows.Forms.TrackBar.LargeChange%2A>. Значение <xref:System.Windows.Forms.TrackBar.SmallChange%2A> свойство — количество позиций, перемещается в ответ на нажатии клавиши влево или вправо. Значение <xref:System.Windows.Forms.TrackBar.LargeChange%2A> свойство — количество позиций бегунка переходит в ответ на нажатии клавиши PAGE UP или PAGE DOWN или в ответ на мыши, нажимает на полосе слева от бегунка.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TrackBar>  
 [Элемент управления TrackBar](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
