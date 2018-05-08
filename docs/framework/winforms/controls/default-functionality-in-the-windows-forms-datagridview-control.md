---
title: Стандартная функциональность элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: a475d8bce388860c88571fbf638d206bfe01223d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Стандартная функциональность элемента управления DataGridView в Windows Forms
Windows Forms <xref:System.Windows.Forms.DataGridView> управления предоставляет пользователям широкую функциональность по умолчанию.  
  
## <a name="default-functionality"></a>Функциональные возможности по умолчанию  
 По умолчанию <xref:System.Windows.Forms.DataGridView> управления:  
  
-   Автоматически отображает заголовки столбцов и заголовки строк, которые остаются видимыми при прокрутке таблицы по вертикали.  
  
-   Содержит заголовок строки с указателем выбора для текущей строки.  
  
-   Содержит прямоугольник выделения в первой ячейке.  
  
-   Есть столбцы, которые могут быть изменены автоматически при двойном щелчке разделителей столбцов.  
  
-   Автоматическая поддержка визуальных стилей в Windows XP и семейства Windows Server 2003 при <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод вызывается из приложения `Main` метод.  
  
 Кроме того, содержимое <xref:System.Windows.Forms.DataGridView> управления могут редактироваться по умолчанию:  
  
-   Если пользователь дважды щелкает или нажимает клавишу F2 в ячейке, элемент управления автоматически переводит ячейку в режим редактирования и обновляет содержимое ячейки при вводе.  
  
-   Если пользователь выполняет прокрутку к концу сетки, пользователь увидит наличии строка для добавления новых записей. Когда пользователь нажимает эту строку, добавляется новая строка <xref:System.Windows.Forms.DataGridView> управления со значениями по умолчанию. При нажатии клавиши ESC новая строка удаляется.  
  
-   При нажатии кнопки в заголовке строки выбирается целой строки.  
  
 При привязке <xref:System.Windows.Forms.DataGridView> управления к источнику данных, установив его <xref:System.Windows.Forms.DataGridView.DataSource%2A> свойства:  
  
-   Автоматически использует имена столбцов источника данных в виде текста заголовка столбца.  
  
-   Заполняется содержимым источника данных. <xref:System.Windows.Forms.DataGridView> столбцы создаются автоматически для каждого столбца в источнике данных.  
  
-   Создает строку для каждой видимой строки в таблице.  
  
-   Автоматически сортирует строки на основе базовых данных при щелчке заголовка столбца.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
