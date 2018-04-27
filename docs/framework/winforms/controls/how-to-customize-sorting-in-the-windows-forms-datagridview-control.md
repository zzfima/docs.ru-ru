---
title: Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e35e340b786e078b5b1264d3f321ff952d52b439
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает автоматическую сортировку, но в определенных ситуациях может потребоваться настроить операции сортировки. Например, с помощью программной сортировки можно создать альтернативный пользовательский интерфейс. Кроме того, можно обработать событие <xref:System.Windows.Forms.DataGridView.SortCompare> или вызвать перегрузку `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> для обеспечения большей гибкости сортировки, например для сортировки нескольких столбцов.  
  
 В приведенных ниже примерах кода демонстрируются эти три подхода к пользовательской сортировке. Дополнительные сведения см. в разделе [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="programmatic-sorting"></a>Программная сортировка  
 В примере кода ниже демонстрируется программная сортировка с использованием свойств <xref:System.Windows.Forms.DataGridView.SortOrder%2A> и <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> для определения направления сортировки и свойства <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> для ручной установки глифа сортировки. Перегрузка `Sort(DataGridViewColumn,ListSortDirection)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A> используется для сортировки данных только в одном столбце.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a>Пользовательская сортировка с помощью события SortCompare  
 В примере кода ниже демонстрируется пользовательская сортировка с использованием обработчика событий <xref:System.Windows.Forms.DataGridView.SortCompare>. Выбранный столбец <xref:System.Windows.Forms.DataGridViewColumn> сортируется, а при обнаружении в нем повторяющихся значений столбец ID используется для определения конечного порядка.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a>Пользовательская сортировка с помощью интерфейса IComparer  
 В примере кода ниже демонстрируется пользовательская сортировка с помощью перегрузки `Sort(IComparer)` метода <xref:System.Windows.Forms.DataGridView.Sort%2A>, которая принимает реализацию интерфейса <xref:System.Collections.IComparer> для выполнения сортировки по нескольким столбцам.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этих примеров требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о построении этих примеров из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Сортировка данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)
