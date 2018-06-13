---
title: Практическое руководство. Определение z-порядка закрепленных элементов управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], specifying z-order
- z-order
ms.assetid: 8b595429-ba9f-46af-9c55-3d5cc53f7fff
ms.openlocfilehash: 48b7338568de17e941e1e464b9ff906a4bc93c3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532113"
---
# <a name="how-to-define-z-ordering-of-docked-toolstrip-controls"></a>Практическое руководство. Определение z-порядка закрепленных элементов управления ToolStrip
Чтобы правильно расположить закрепленный элемент управления <xref:System.Windows.Forms.ToolStrip>, следует правильно выбрать положение этого элемента управления в z-порядке формы.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как разместить элемент управления <xref:System.Windows.Forms.ToolStrip> и закрепленный элемент управления <xref:System.Windows.Forms.MenuStrip> путем указания z-порядка.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#21)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#21)]  
  
 z-порядок определяется порядком, в котором элементы управления <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.MenuStrip>  
  
 добавляются в коллекцию <xref:System.Windows.Forms.Control.Controls%2A> формы.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#23)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#23)]  
  
 Измените очередность вызовов метода <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> на обратную и посмотрите, как это отразится на макете.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также построить этот пример, в Visual Studio, вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.ControlCollection.Add%2A>  
 <xref:System.Windows.Forms.Control.Controls%2A>  
 <xref:System.Windows.Forms.Control.Dock%2A>  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
