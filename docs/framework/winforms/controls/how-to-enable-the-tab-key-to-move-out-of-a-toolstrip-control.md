---
title: Как выполнить С помощью клавиши для перемещения выход из элемента управления ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: a98c8a54389daa898c877a08f8cc2cae46a11da9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663093"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Как выполнить С помощью клавиши для перемещения выход из элемента управления ToolStrip
Используйте следующую процедуру, чтобы пользователь мог нажать клавишу TAB для перемещения из <xref:System.Windows.Forms.ToolStrip> к следующему элементу управления в последовательности табуляции.  
  
 <xref:System.Windows.Forms.ToolStrip> Принимает первое нажатие клавиши TAB и ключи стрелку, выберите элементы в <xref:System.Windows.Forms.ToolStrip>. При нажатии клавиши TAB во второй раз, он направляет пользователя к следующему элементу управления в последовательности табуляции.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Чтобы пользователь мог нажать клавишу TAB для перемещения от элемента управления ToolStrip к следующему элементу управления  
  
-   Задайте <xref:System.Windows.Forms.ToolStrip.TabStop%2A> свойство <xref:System.Windows.Forms.ToolStrip> для `true`.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
