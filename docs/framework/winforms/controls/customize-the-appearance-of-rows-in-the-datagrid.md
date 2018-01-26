---
title: "Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f14b6edb9a3176327e65bb41839b1abd943a438c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>Практическое руководство. Настройка внешнего вида строк элемента управления DataGridView в Windows Forms
Внешним видом строк <xref:System.Windows.Forms.DataGridView> можно управлять при помощи одного или обоих событий <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> и <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Эти события спроектированы таким образом, что вы можете отобразить только необходимое, позволяя отрисовать остальное элементу управления <xref:System.Windows.Forms.DataGridView>. Например, для рисования пользовательского фона можно обрабатывать событие <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> и дать возможность отдельным ячейкам нарисовать собственное содержимое переднего плана. Кроме того, можно дать возможность ячейкам отрисовать себя и добавить настраиваемый основной цвет в обработчике событий <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Также можно отключить прорисовку ячеек и самостоятельно нарисовать все в обработчике событий <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.  
  
 В следующем примере кода реализованы обработчики для обоих событий, чтобы обеспечить выбор градиентного фона и настраиваемого основного цвета для нескольких столбцов.  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [Построение из командной строки с помощью файла csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>  
 [Настройка элементов управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [Архитектура элементов управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)
