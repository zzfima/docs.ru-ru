---
title: Форматирование данных в элементе управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 5966f16238999655d6072c1127e5bf16aefde5e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969187"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Форматирование данных в элементе управления DataGridView в Windows Forms
<xref:System.Windows.Forms.DataGridView> Элемент управления обеспечивает автоматическое преобразование между значениями ячеек и типами данных, отображаемыми в родительских столбцах. Столбцы текстового поля, например, отображают строковые представления значений даты, времени, чисел и перечислений, а также преобразуют пользовательские строковые значения в типы, необходимые для хранилища данных.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Форматирование с помощью класса Датагридвиевцеллстиле  
 Элемент управления обеспечивает базовое форматирование данных значений ячеек <xref:System.Windows.Forms.DataGridViewCellStyle> с помощью класса. <xref:System.Windows.Forms.DataGridView> <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> Свойство можно использовать для форматирования значений даты, времени, числа и перечисления для текущего языка и региональных параметров по умолчанию с помощью описателей формата, описанных в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md). Можно также отформатировать эти значения для конкретных языков и <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> региональных параметров с помощью свойства. Указанный формат используется как для вывода данных, так и для анализа данных, вводимых пользователем в указанном формате.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> Класс предоставляет дополнительные свойства форматирования для переноса слов, выравнивания текста и пользовательского представления значений базы данных null. Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных в элементе управления](how-to-format-data-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.  
  
## <a name="formatting-with-the-cellformatting-event"></a>Форматирование с помощью события CellFormatting  
 Если основное форматирование не соответствует вашим потребностям, можно указать пользовательское форматирование данных в обработчике <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> события. Объект <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> , переданный в обработчик, <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> имеет свойство, изначально содержащее значение ячейки. Обычно это значение автоматически преобразуется в тип вывода. Чтобы самостоятельно преобразовать значение, задайте <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> для свойства значение типа, отображаемое в поле Тип.  
  
> [!NOTE]
> Если для ячейки действует строка форматирования, она переопределяет изменение <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> значения свойства, за исключением случая, когда <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> свойству `true`задано значение.  
  
 Событие также полезно, если необходимо задать <xref:System.Windows.Forms.DataGridViewCellStyle> свойства для отдельных ячеек на основе их значений. <xref:System.Windows.Forms.DataGridView.CellFormatting> Дополнительные сведения см. в разделе [Практическое руководство. Настройка форматирования данных в элементе управления](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.  
  
 Если синтаксический анализ по умолчанию определяемых пользователем значений не соответствует вашим потребностям, можно обработать <xref:System.Windows.Forms.DataGridView.CellParsing> событие <xref:System.Windows.Forms.DataGridView> элемента управления, чтобы обеспечить пользовательский синтаксический анализ.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Отображение данных с помощью элемента управления DataGridView в Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Форматирование данных в элементе управления Windows Forms DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Настройка форматирования данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
