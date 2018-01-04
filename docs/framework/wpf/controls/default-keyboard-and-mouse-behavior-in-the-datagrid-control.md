---
title: "Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28cb1b02e67d076f9190e2d8e36b72c20cc5c4e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Поведение мыши и клавиатуры по умолчанию в элементе управления DataGrid
В этом разделе описывается, как пользователи могут взаимодействовать с <xref:System.Windows.Controls.DataGrid> управления с помощью клавиатуры и мыши.  
  
 Типичные варианты взаимодействия машин с <xref:System.Windows.Controls.DataGrid> включают навигации, выбора и изменения. Выбор поведение определяется параметром <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> и <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> свойства. Значения по умолчанию, которые вызывают неполадки, описанные в этом разделе, <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> и <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>. Изменение этих значений может привести к поведение, которое отличается от описанной. Если ячейка находится в режиме редактирования, редактирования элемента управления может переопределить поведение на стандартной клавиатуре <xref:System.Windows.Controls.DataGrid>.  
  
## <a name="default-keyboard-behavior"></a>Стандартное поведение клавиатуры  
 В следующей таблице перечислены сочетания по умолчанию <xref:System.Windows.Controls.DataGrid>.  
  
|Клавиши или сочетания клавиш|Описание:|  
|----------------------------|-----------------|  
|СТРЕЛКА ВНИЗ|Перемещение фокуса к ячейке, расположенной непосредственно под текущей ячейкой. Если фокус находится в последней строке, нажав клавишу со стрелкой вниз ничего не делает.|  
|СТРЕЛКА ВВЕРХ|Перемещает фокус в ячейку непосредственно над текущей ячейки. Если фокус находится в первой строке, нажав клавишу со стрелкой вверх ничего не делает.|  
|СТРЕЛКА ВЛЕВО|Переход к предыдущей ячейке в строке. Если фокус находится в первой ячейке в строке, используйте клавиши Стрелка влево ничего не делает.|  
|СТРЕЛКА ВПРАВО|Перемещение фокуса к следующей ячейке в строке. Если фокус находится в последней ячейке в строке, нажав клавишу со стрелкой вправо ничего не делает.|  
|ГЛАВНАЯ|Переход к первой ячейке в текущей строке.|  
|END|Передает фокус последней ячейке в текущей строке.|  
|PAGE DOWN|Если строки не группируются, прокручивает элемент управления вниз на число строк, отображаемых полностью. Передает фокус последней полностью отображаемой строки без изменения столбцов.<br /><br /> Если строки группируются, фокус перемещается в последней строке <xref:System.Windows.Controls.DataGrid> без изменения столбцов.|  
|PAGE UP|Если строки не группируются, прокручивает элемент управления вверх на число строк, отображаемых полностью. Перемещение фокуса на первую строку отображается без изменения столбцов.<br /><br /> Если строки группируются, фокус перемещается в первую строку в <xref:System.Windows.Controls.DataGrid> без изменения столбцов.|  
|TAB|Перемещение фокуса к следующей ячейке в текущей строке. Если фокус находится в последней ячейке строки, фокус перемещается к первой ячейке в следующей строке. Если фокус находится в последней ячейке в элементе управления, фокус перемещается к следующему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если текущая ячейка находится в режиме редактирования и нажатия клавиши TAB фокус причины для перемещения в текущей строке, любые изменения, внесенные в строку, до изменения фокуса.|  
|SHIFT+TAB|Перемещение фокуса к предыдущей ячейке в текущей строке. Если фокус находится в первой ячейке строки, фокус перемещается в последнюю ячейку в предыдущей строке. Если фокус находится в первой ячейке в элементе управления, фокус перемещается к предыдущему элементу управления в последовательности табуляции родительского контейнера.<br /><br /> Если текущая ячейка находится в режиме редактирования и нажатия клавиши TAB фокус причины для перемещения в текущей строке, любые изменения, внесенные в строку, до изменения фокуса.|  
|CTRL+СТРЕЛКА ВНИЗ|Перемещает фокус до последней ячейки в текущем столбце.|  
|CTRL + СТРЕЛКА ВВЕРХ|Переход к первой ячейке текущего столбца.|  
|CTRL + СТРЕЛКА ВПРАВО|Передает фокус последней ячейке в текущей строке.|  
|CTRL+СТРЕЛКА ВЛЕВО|Переход к первой ячейке в текущей строке.|  
|CTRL + HOME|Переход к первой ячейке в элементе управления.|  
|CTRL + END|Перемещение фокуса в последнюю ячейку в элементе управления.|  
|CTRL+PAGE DOWN|То же, как PAGE DOWN.|  
|CTRL+PAGE UP|То же, как PAGE UP.|  
|F2|Если <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> свойство `false` и <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> свойство `false` для текущего столбца переводит текущую ячейку в режим редактирования ячейки.|  
|ВВОД|Фиксирует все изменения в текущей ячейке и строку и фокус перемещается к ячейке, расположенной непосредственно под текущей ячейкой. Если фокус находится в последней строке, изменения сохраняются без перемещения фокуса.|  
|ESC|Если элемент управления находится в режиме редактирования, отменяет изменение и отменяет изменения, внесенные в элемент управления. Если базовый источник данных реализует <xref:System.ComponentModel.IEditableObject>, еще раз нажмите клавишу ESC отменяет режим редактирования для всей строки.|  
|СТИРАНИЕ НАЗАД|Удаление знака до курсора, при редактировании ячейки.|  
|DELETE|Удаление знака после курсора, при редактировании ячейки.|  
|CTRL+ВВОД|Фиксирует все изменения в текущей ячейке без перемещения фокуса.|  
|CTRL+A|Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> равно <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, выбирает все строки в <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="selection-keys"></a>Выбор ключей  
 Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> свойству <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, поведение не изменяется, но навигацию с помощью клавиатуры, удерживая нажатой клавишу SHIFT (включая сочетание клавиш CTRL + SHIFT) будет изменен выбор нескольких строк. Перед началом навигации элемента управления помечает текущую строку как строку привязки. При переходе, удерживая нажатой клавишу SHIFT, выделение включает все строки между строки привязки и текущей строки.  
  
 Следующие разделы выбора изменять выбранный для нескольких строк.  
  
-   SHIFT + СТРЕЛКА ВНИЗ  
  
-   SHIFT + СТРЕЛКА ВВЕРХ  
  
-   SHIFT + PAGE DOWN  
  
-   SHIFT + PAGE UP  
  
-   CTRL+SHIFT+СТРЕЛКА ВНИЗ  
  
-   CTRL+SHIFT+СТРЕЛКА ВВЕРХ  
  
-   CTRL + SHIFT + HOME  
  
-   CTRL + SHIFT + END  
  
## <a name="default-mouse-behavior"></a>По умолчанию поведение мыши  
 В следующей таблице перечислены мыши по умолчанию <xref:System.Windows.Controls.DataGrid>.  
  
|Действие мыши|Описание:|  
|------------------|-----------------|  
|Нажмите кнопку невыбранные строки|Делает выбранной строки, текущая строка и выбранная ячейка текущей ячейки.|  
|Нажмите кнопку текущей ячейки|Переводит текущую ячейку в режим редактирования.|  
|Перетащите ячейки заголовка столбца|Если <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> свойство `true` и <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> свойство `true` для текущего столбца перемещает столбец, чтобы его можно перетащить в новое место.|  
|Перетаскивать разделитель заголовка столбца|Если <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> свойство `true` и <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> свойство `true` для текущего столбца изменяет размер столбца.|  
|Дважды щелкните файл разделителя заголовков столбцов|Если <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> свойство `true` и <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> свойство `true` для текущего столбца автоматически изменяет размер столбца с помощью <xref:System.Windows.Controls.DataGridLength.Auto%2A> режим изменения размеров.|  
|Щелкните ячейку заголовка столбца|Если <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> свойство `true` и <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> свойство `true` для текущего столбца, сортировка столбца.<br /><br /> Щелкнув заголовок столбца, который уже был отсортирован будет изменить направление сортировки этого столбца.<br /><br /> Нажав клавишу SHIFT, пока щелкнув нескольким заголовкам столбцов будет сортировать по нескольким столбцам в порядке щелкнули.|  
|CTRL + щелчок строки|Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> равно <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, изменяет несмежных выбора нескольких строк.<br /><br /> Если строка выбрана, отменяет выбор строки.|  
|SHIFT, щелкните строку|Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> равно <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, изменяет связанному выделению нескольких строк.|  
|Щелкните заголовок группы строк|Разворачивает или сворачивает группу.|  
|Нажмите кнопку "выбрать все" в верхнем левом углу<xref:System.Windows.Controls.DataGrid>|Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> равно <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, выбирает все строки в <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="mouse-selection"></a>Выделение мышью  
 Если <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> свойству <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, щелкнув строку, удерживая нажатой клавишу CTRL или SHIFT изменит выбор нескольких строк.  
  
 При нажатии кнопки строки, удерживая нажатой клавишу CTRL, строка изменится состояние выделения их текущее состояние выделения, сохраняя все остальные строки. Это необходимо для выбора несмежных строк.  
  
 При нажатой клавишей SHIFT, щелкните строку, выделение включает все строки между текущей строки и строки привязки, находящейся в позиции текущей строки до нажмите кнопку. Последующие нажатия кнопки, нажатой клавишей SHIFT изменение текущей строки, но не строки привязки. Для этого выберите диапазон смежных строк.  
  
 Чтобы выбрать несмежные диапазоны смежных строк можно объединить CTRL + SHIFT. Чтобы сделать это, выберите первый диапазон с помощью клавиши SHIFT + щелчок как описано выше. После выбора первого диапазона строк используйте сочетание клавиш CTRL + выберите первую строку в следующего диапазона и нажмите кнопку в последней строке следующего диапазона при нажатой клавиши CTRL + SHIFT.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
