---
title: Практическое руководство. Добавление в форму элемента управления ToolStripContainer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 7e9b12505c0e80cdafe56967321f46d41305b799
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524684"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>Практическое руководство. Добавление в форму элемента управления ToolStripContainer
В форму Windows Forms можно программно добавить контейнер <xref:System.Windows.Forms.ToolStripContainer> и заполнить его элементами управления.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить <xref:System.Windows.Forms.ToolStripContainer> и <xref:System.Windows.Forms.ToolStrip> в форму Windows Forms, добавить элементы в <xref:System.Windows.Forms.ToolStrip> и как добавить <xref:System.Windows.Forms.ToolStrip> к <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> из <xref:System.Windows.Forms.ToolStripContainer>.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера кода требуются:  
  
-   ссылки на сборки System.Drawing, System.Windows.Forms и System.Xml.  
  
 Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также построить этот пример, в Visual Studio, вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)) или [Диалоговое окно задач ToolStripContainer](http://msdn.microsoft.com/library/ms233647\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [Элемент управления ToolStripContainer](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
