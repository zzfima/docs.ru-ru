---
title: Практическое руководство. Соединение нескольких элементов управления ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: d9cacddecdf3859a0fca4038481eeab417e22e6a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592381"
---
# <a name="how-to-join-toolstrippanels"></a>Практическое руководство. Соединение нескольких элементов управления ToolStripPanel
Элементы управления <xref:System.Windows.Forms.ToolStrip> можно подключать к <xref:System.Windows.Forms.ToolStripPanel> во время выполнения, благодаря чему обеспечивается гибкость приложений с интерфейсом MDI.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как подключить элементы управления <xref:System.Windows.Forms.ToolStrip> к <xref:System.Windows.Forms.ToolStripPanel>.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [Практическое руководство. Руководство.](how-to-use-toolstrippanels-for-mdi.md)
