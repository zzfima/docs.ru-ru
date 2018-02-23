---
title: "Сортировка данных в элементе управления Windows Forms DataGridView"
ms.date: 02/13/2018
ms.prod: .net-framework
ms.technology:
- dotnet-winforms
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ab4ec958a4275ed805ed33ee3eff9ab67fde3dc
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2018
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Сортировка данных в элементе управления Windows Forms DataGridView

По умолчанию пользователи могут сортировать данные в <xref:System.Windows.Forms.DataGridView> управления, щелкнув заголовок столбца текстового поля (или нажмите клавишу F3, при получении фокуса ввода ячейке текстового поля на .NET Framework 4.7.2 и более поздних версиях). Вы можете изменить <xref:System.Windows.Forms.DataGridViewColumn.SortMode> определенных столбцов, чтобы пользователи могли сортировать по другим типам столбцов, когда имеет смысл для этого свойства. Данные можно также сортировать программным путем, по любому столбцу или нескольким столбцам.

## <a name="in-this-section"></a>Содержание раздела

[Установка режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
Описание параметров сортировки данных в элементе управления.

[Практическое руководство. Определение режимов сортировки для столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
Описывает, как разрешить пользователям сортировать по столбцам, которые не сортируются по умолчанию.

[Практическое руководство. Настройка сортировки данных элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
Описывается порядок сортировки данных программным образом и настройки сортировки с помощью <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> событий либо путем реализации <xref:System.Collections.IComparer> интерфейса.

## <a name="reference"></a>Ссылка

<xref:System.Windows.Forms.DataGridView>  
Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.DataGridView>.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
Содержит справочную документацию по <xref:System.Windows.Forms.DataGridView.Sort%2A> метод.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> свойство.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
Содержит справочную документацию по <xref:System.Windows.Forms.DataGridViewColumnSortMode> перечисления.

## <a name="see-also"></a>См. также

[Элемент управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
[Типы столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  