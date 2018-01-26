---
title: "Общие сведения об элементе управления FlowLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7eafe31bec86a969a12661c9f5629b2d55e3e3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="flowlayoutpanel-control-overview"></a>Общие сведения об элементе управления FlowLayoutPanel
Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает содержимое в горизонтальном или вертикальном направлении. Его содержимое может переноситься из одной строки или столбца в следующую строку или столбец. Кроме того, вместо переноса содержимое может обрезаться.  
  
 Чтобы определить направление содержимого, задайте свойство <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. Содержимое элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> размещается правильно при использовании направления справа налево. С помощью свойства <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> можно указать, должно ли содержимое элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> переноситься или обрезаться.  
  
 Если свойству <xref:System.Windows.Forms.Control.AutoSize%2A> присвоено значение `true`, размер элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> автоматически изменяется в соответствии с содержимым. Он также предоставляет **FlowBreak** свойство к его дочерним элементам управления. Если свойству FlowBreak присвоено значение `true` , элементы управления внутри элемента <xref:System.Windows.Forms.FlowLayoutPanel> перестают размещаться в текущем направлении и переносятся на следующую строку или в следующий столбец.  
  
 Любой элемент управления Windows Forms, включая другие экземпляры <xref:System.Windows.Forms.FlowLayoutPanel>, может быть дочерним относительно элемента <xref:System.Windows.Forms.FlowLayoutPanel>. Это позволяет создавать сложные макеты, которые изменяются в соответствии с размерами формы во время выполнения.  
  
 См. также [Пошаговое руководство: упорядочение элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Элемент управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
