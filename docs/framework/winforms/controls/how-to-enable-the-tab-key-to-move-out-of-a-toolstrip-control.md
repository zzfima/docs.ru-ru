---
title: Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: 7fee9f685b9a9b402cbfe9c265669f7905434986
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609841"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Практическое руководство. Выход из элемента управления ToolStrip с помощью клавиши TAB
Используйте следующую процедуру, чтобы пользователь мог нажать клавишу TAB для перемещения из <xref:System.Windows.Forms.ToolStrip> к следующему элементу управления в последовательности табуляции.  
  
 <xref:System.Windows.Forms.ToolStrip> Принимает первое нажатие клавиши TAB и ключи стрелку, выберите элементы в <xref:System.Windows.Forms.ToolStrip>. При нажатии клавиши TAB во второй раз, он направляет пользователя к следующему элементу управления в последовательности табуляции.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Чтобы пользователь мог нажать клавишу TAB для перемещения от элемента управления ToolStrip к следующему элементу управления  
  
- Задайте <xref:System.Windows.Forms.ToolStrip.TabStop%2A> свойство <xref:System.Windows.Forms.ToolStrip> для `true`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
