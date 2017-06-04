---
title: "Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ячейки, изменение цветов в элементе управления DataGridView [Windows Forms]"
  - "цвета, изменение в элементе управления DataGridView [Windows Forms]"
  - "данные [Windows Forms], форматирование данных в элементе управления DataGridView"
  - "таблицы данных, форматирование данных"
  - "DataGridView - элемент управления [Windows Forms], настройка ячеек"
  - "DataGridView - элемент управления [Windows Forms], стили ячеек"
  - "DataGridView - элемент управления [Windows Forms], изменение цветов ячеек"
  - "DataGridView - элемент управления [Windows Forms], форматирование данных"
  - "DataGridView - элемент управления [Windows Forms], подстановка значений ячеек для отображения"
  - "Windows Forms, изменение цветов ячеек DataGridView"
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms
В следующем примере кода показано, как реализовать обработчик для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>, которое изменяет способ отображения ячеек в зависимости от их столбцов и значений.  
  
 Ячейки в столбце `Balance`, которые содержат отрицательные числа, имеют красный фон.  Также можно отформатировать эти ячейки в денежном формате для отображения отрицательных значений в круглых скобках.  Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
 В ячейках столбца `Priority` отображаются изображения вместо соответствующих текстовых значений.  Свойство <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> объекта <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> используется для получения значения текстовой ячейки и задания соответствующего значения отображаемого изображения.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
-   Изображения <xref:System.Drawing.Bitmap> с именами `highPri.bmp`, `mediumPri.bmp` и `lowPri.bmp` находятся в том же каталоге, что и исполняемый файл.  
  
 Дополнительные сведения о построении этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] см. в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Данный пример можно также построить в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] путем вставки кода в новый проект.  См. также [Практическое руководство. Компиляция и выполнение скомпилированного примера кода Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Drawing.Bitmap>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Форматирование данных в элементе управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)