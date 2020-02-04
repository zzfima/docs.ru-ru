---
title: Форматирование данных в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: a041bcc5e1b65afb3123f1f42e0f1b5a479b5764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743984"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Форматирование данных в элементе управления DataGridView в Windows Forms
Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает автоматическое преобразование между значениями ячеек и типами данных, отображаемыми в родительских столбцах. Столбцы текстового поля, например, отображают строковые представления значений даты, времени, чисел и перечислений, а также преобразуют пользовательские строковые значения в типы, необходимые для хранилища данных.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Форматирование с помощью класса Датагридвиевцеллстиле  
 Элемент управления <xref:System.Windows.Forms.DataGridView> обеспечивает базовое форматирование данных значений ячеек с помощью класса <xref:System.Windows.Forms.DataGridViewCellStyle>. Свойство <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> можно использовать для форматирования значений даты, времени, числа и перечисления для текущего языка и региональных параметров по умолчанию с помощью описателей формата, описанных в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md). Можно также отформатировать эти значения для конкретных языков и региональных параметров с помощью свойства <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>. Указанный формат используется как для вывода данных, так и для анализа данных, вводимых пользователем в указанном формате.  
  
 Класс <xref:System.Windows.Forms.DataGridViewCellStyle> предоставляет дополнительные свойства форматирования для переноса слов, выравнивания текста и пользовательского представления значений NULL базы данных. Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Форматирование с помощью события CellFormatting  
 Если основное форматирование не соответствует вашим потребностям, можно задать пользовательское форматирование данных в обработчике для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>, переданный в обработчик, имеет свойство <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>, которое изначально содержит значение ячейки. Обычно это значение автоматически преобразуется в тип вывода. Чтобы самостоятельно преобразовать значение, задайте для свойства <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> значение типа отображаемого значения.  
  
> [!NOTE]
> Если для ячейки действует строка формата, она переопределяет изменение значения свойства <xref:System.Windows.Forms.ConvertEventArgs.Value%2A>, если для свойства <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> не задано значение `true`.  
  
 Событие <xref:System.Windows.Forms.DataGridView.CellFormatting> также полезно, если требуется задать свойства <xref:System.Windows.Forms.DataGridViewCellStyle> для отдельных ячеек на основе их значений. Дополнительные сведения см. в разделе [инструкции. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Если синтаксический анализ по умолчанию определяемых пользователем значений не соответствует вашим потребностям, можно обработать событие <xref:System.Windows.Forms.DataGridView.CellParsing> элемента управления <xref:System.Windows.Forms.DataGridView>, чтобы обеспечить пользовательский синтаксический анализ.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
