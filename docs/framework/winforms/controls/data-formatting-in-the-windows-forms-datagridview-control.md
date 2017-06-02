---
title: "Форматирование данных в элементе управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "данные [Windows Forms], форматирование в таблице"
  - "таблицы данных, форматирование данных"
  - "DataGridView - элемент управления [Windows Forms], форматирование данных"
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Форматирование данных в элементе управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает автоматическое преобразование между значениями ячеек и типами данных, которые отображаются в родительских столбцах.  Например, в столбцах текстовых полей отображаются строковые представления значений даты, времени, чисел и перечисления, а введенные пользователем строковые значения преобразуются в типы, необходимые для хранилища данных.  
  
## Форматирование с использованием класса DataGridViewCellStyle  
 Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает базовое форматирование данных для значений ячеек через класс <xref:System.Windows.Forms.DataGridViewCellStyle>.  Свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> можно использовать для форматирования значений даты, времени, чисел и перечисления в соответствии с выбранными региональными параметрами по умолчанию, используя спецификаторы форматы, которые описаны в [Типы форматирования](../../../../docs/standard/base-types/formatting-types.md).  Также эти значения можно отформатировать в соответствии с определенными региональными параметрами, используя свойство <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>.  Указанный формат используется как для отображения данных, так и для синтаксического анализа данных, которые пользователь вводит в указанном формате.  
  
 Класс <xref:System.Windows.Forms.DataGridViewCellStyle> предоставляет дополнительные свойства форматирования для переноса слов и выравнивания текста и настройки отображения пустых значений базы данных.  Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## Форматирование с использованием события CellFormatting  
 Если базовое форматирование не соответствует требованиям, можно предоставить пользовательское форматирование данных в обработчике событий <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  Событие <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>, передаваемое обработчику, содержит свойство <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>, которое изначально содержит значение ячейки.  Обычно это значение автоматически преобразуется к типу отображения.  Чтобы вручную преобразовать это значение, присвойте свойству <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> значение типа отображения.  
  
> [!NOTE]
>  Если для ячейки действует строка формата, она переопределяет пользовательское изменение значения свойства <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>, за исключением случая, когда свойству <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> присвоено значение `true`.  
  
 Событие <xref:System.Windows.Forms.DataGridView.CellFormatting> также используется в тех случаях, когда требуется указать значения для свойств <xref:System.Windows.Forms.DataGridViewCellStyle> отдельных ячеек, основываясь на их значениях.  Дополнительные сведения содержатся в разделе [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Если анализ по умолчанию или указанные пользователем значения не соответствуют требованиям, можно обработать событие <xref:System.Windows.Forms.DataGridView.CellParsing> элемента управления <xref:System.Windows.Forms.DataGridView> для предоставления пользовательского анализа.  
  
## См. также  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)