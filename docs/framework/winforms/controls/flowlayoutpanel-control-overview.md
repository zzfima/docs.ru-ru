---
title: Общие сведения об элементе управления FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 73767114da1c04222fb8ceaf812153421c4597aa
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185196"
---
# <a name="flowlayoutpanel-control-overview"></a>Общие сведения об элементе управления FlowLayoutPanel
Элемент управления <xref:System.Windows.Forms.FlowLayoutPanel> упорядочивает содержимое в горизонтальном или вертикальном направлении. Его содержимое может переноситься из одной строки или столбца в следующую строку или столбец. Кроме того, вместо переноса содержимое может обрезаться.  
  
 Чтобы определить направление содержимого, задайте свойство <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. Содержимое элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> размещается правильно при использовании направления справа налево. С помощью свойства <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> можно указать, должно ли содержимое элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> переноситься или обрезаться.  
  
 Если свойству <xref:System.Windows.Forms.Control.AutoSize%2A> присвоено значение `true`, размер элемента управления <xref:System.Windows.Forms.FlowLayoutPanel> автоматически изменяется в соответствии с содержимым. Он также предоставляет **FlowBreak** свойство к его дочерним элементам управления. Если свойству FlowBreak присвоено значение `true` , элементы управления внутри элемента <xref:System.Windows.Forms.FlowLayoutPanel> перестают размещаться в текущем направлении и переносятся на следующую строку или в следующий столбец.  
  
 Любой элемент управления Windows Forms, включая другие экземпляры <xref:System.Windows.Forms.FlowLayoutPanel>, может быть дочерним относительно элемента <xref:System.Windows.Forms.FlowLayoutPanel>. Это позволяет создавать сложные макеты, которые изменяются в соответствии с размерами формы во время выполнения.  
  
 Также см. в разделе [Пошаговое руководство: упорядочение элементов управления в Windows Forms с помощью элемента FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [Элемент управления FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
