---
title: Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: f01a9acb3a566be40d65fb075c8487d4e9cb6e73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623645"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a>Практическое руководство. Отслеживание наведения указателя мыши на элемент ToolStripItem
Используйте следующую процедуру, чтобы определить, когда указатель мыши находится над <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a>Чтобы определить, когда указатель наведен на элемент ToolStripItem  
  
- Используйте <xref:System.Windows.Forms.ToolStripItem.Selected%2A> свойства для элементов, в котором <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> является `true`.  
  
     Это избавит вас от необходимости синхронизации <xref:System.Windows.Forms.ToolStripItem.MouseEnter> и <xref:System.Windows.Forms.ToolStripItem.MouseLeave> события.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
