---
title: Форматирование данных в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: ae1947cf7c3825553837fa5f1ee288114988d28f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527778"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Форматирование данных в элементе управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Управления обеспечивает автоматическое преобразование между значениями ячеек и типы данных, которые отображаются в родительских столбцах. Например, столбцах текстовых полей отображаются строковые представления значений даты, времени, числа и значения перечисления и введенные пользователем строковые значения преобразуются в типы, необходимые в хранилище данных.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Форматирование с классом DataGridViewCellStyle  
 <xref:System.Windows.Forms.DataGridView> Управления обеспечивает базовое форматирование данных для значений ячеек через <xref:System.Windows.Forms.DataGridViewCellStyle> класса. Можно использовать <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> свойств для форматирования даты, времени, числа и перечисление значений для текущего языка и региональных параметров по умолчанию, с помощью описателей формата, описанные в [типы форматирования](../../../../docs/standard/base-types/formatting-types.md). Также можно отформатировать эти значения для определенных языков и региональных параметров с помощью <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> свойство. Указанный формат используется для отображения данных и для синтаксического анализа данных, вводимых пользователем в указанном формате.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> Класс предоставляет дополнительные свойства форматирования для переноса слов, выравнивание текста и настройки отображения пустых значений базы данных. Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Форматирование с событием CellFormatting  
 Если базовое форматирование не удовлетворяет вашим требованиям, можно предоставить пользовательское форматирование данных в обработчик <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> событий. <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> Передается обработчику имеет <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> свойство, которое изначально содержит значение ячейки. Как правило это значение автоматически преобразуется в тип отображения. Для преобразования значения самостоятельно, задайте <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> значение части типа отображения.  
  
> [!NOTE]
>  Если строка формата действует для ячейки, оно переопределяет изменения в <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> значение свойства, если не задать <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> свойства `true`.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> Событий также полезен, если вы хотите задать <xref:System.Windows.Forms.DataGridViewCellStyle> свойства для отдельных ячеек на основе их значений. Дополнительные сведения см. в разделе [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Если анализ указанные пользователем значения по умолчанию не удовлетворяет вашим требованиям, можно обработать <xref:System.Windows.Forms.DataGridView.CellParsing> событие <xref:System.Windows.Forms.DataGridView> элемента управления для предоставления пользовательского анализа.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Отображение данных с помощью элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
