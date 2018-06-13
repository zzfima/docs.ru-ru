---
title: Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: 3686656cc113245514bdb3237bdb24c4c665409f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538146"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Программное изменение размера ячеек элемента управления DataGridView в соответствии с размером отображаемых данных в Windows Forms
С помощью методов элемента управления <xref:System.Windows.Forms.DataGridView> можно изменять размеры строк, столбцов и заголовков, с тем чтобы значения отображались полностью без усечения. Эти методы можно использовать для изменения размеров элементов <xref:System.Windows.Forms.DataGridView> в любое удобное время. Кроме того, элемент управления можно настроить на автоматическое изменение размеров при изменении содержимого. Однако такой подход может быть неэффективным при работе с большими наборами данных или их частом изменении. Дополнительные сведения см. в разделе [параметры изменения размера в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 Как правило, программное изменение размеров элементов <xref:System.Windows.Forms.DataGridView> в соответствии с содержимым требуется только при загрузке данных из источника данных или при изменении значений пользователем. Это позволяет оптимизировать производительность, а также предоставить пользователям возможность изменять размеры строк и столбцов вручную с помощью мыши.  
  
 В примере кода ниже показаны возможности, доступные для программного изменения размеров.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также построить этот пример, в Visual Studio, вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [Изменение размера столбцов и строк элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [Изменение размеров управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Автоматическое изменение размера ячеек при изменении содержимого в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)
