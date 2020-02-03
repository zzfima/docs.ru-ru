---
title: Функциональные возможности по умолчанию в элементе управления DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746135"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Стандартная функциональность элемента управления DataGridView в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.DataGridView> предоставляет пользователям значительный объем функциональных возможностей по умолчанию.  
  
## <a name="default-functionality"></a>Функциональные возможности по умолчанию  
 По умолчанию элемент управления <xref:System.Windows.Forms.DataGridView>:  
  
- Автоматически отображает заголовки столбцов и заголовки строк, которые остаются видимыми при вертикальной прокрутке таблицы.  
  
- Содержит заголовок строки, который содержит индикатор выбора для текущей строки.  
  
- Содержит прямоугольник выделения в первой ячейке.  
  
- Содержит столбцы, размер которых может изменяться автоматически, когда пользователь дважды щелкает разделители столбцов.  
  
- Автоматически поддерживает стили оформления для Windows XP и семейства Windows Server 2003, когда метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> вызывается из метода `Main` приложения.  
  
 Кроме того, содержимое элемента управления <xref:System.Windows.Forms.DataGridView> может быть изменено по умолчанию:  
  
- Если пользователь дважды щелкнет или нажмет клавишу F2 в ячейке, элемент управления автоматически поместит ячейку в режим редактирования и обновит содержимое ячейки как пользовательские типы.  
  
- Если пользователь прокручивается до конца сетки, пользователь увидит строку для добавления новых записей. Когда пользователь щелкает эту строку, в элемент управления <xref:System.Windows.Forms.DataGridView> добавляется новая строка со значениями по умолчанию. Когда пользователь нажимает клавишу ESC, эта новая строка исчезает.  
  
- Если пользователь щелкает заголовок строки, выбирается вся строка.  
  
 При привязке <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных путем установки его свойства <xref:System.Windows.Forms.DataGridView.DataSource%2A> элемент управления:  
  
- Автоматически использует имена столбцов источника данных в качестве текста заголовков столбцов.  
  
- Заполняется содержимым источника данных. <xref:System.Windows.Forms.DataGridView> столбцы создаются автоматически для каждого столбца в источнике данных.  
  
- Создает строку для каждой видимой строки в таблице.  
  
- Автоматически сортирует строки на основе базовых данных, когда пользователь щелкает заголовок столбца.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- [Элемент управления DataGridView](datagridview-control-windows-forms.md)
