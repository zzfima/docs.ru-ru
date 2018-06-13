---
title: Как изменить типа курсора
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 26fc2584381307612c40b615f169902089d9d1f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543397"
---
# <a name="how-to-change-the-cursor-type"></a>Как изменить типа курсора
В этом примере показано, как изменить <xref:System.Windows.Input.Cursor> указателя мыши для отдельного элемента и приложения.  
  
 В этом примере состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл и файл с выделенным кодом.  
  
## <a name="example"></a>Пример  
 Создается пользовательский интерфейс, который состоит из <xref:System.Windows.Controls.ComboBox> для выбора нужного <xref:System.Windows.Input.Cursor>, пару <xref:System.Windows.Controls.RadioButton> объектов, чтобы определить изменение курсора применяется только к одному элементу или применяется ко всему приложению и <xref:System.Windows.Controls.Border> который является элементом, применяемый к нового курсора.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 Следующий код создает <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> обработчик событий, который вызывается при изменении типа курсора в <xref:System.Windows.Controls.ComboBox>.  Оператор switch выполняется фильтрация по имени курсора и наборы <xref:System.Windows.FrameworkElement.Cursor%2A> свойство <xref:System.Windows.Controls.Border> с именем *DisplayArea*.  
  
 Если изменение курсора задано значение «Все приложение», <xref:System.Windows.Input.Mouse.OverrideCursor%2A> свойству <xref:System.Windows.FrameworkElement.Cursor%2A> свойства <xref:System.Windows.Controls.Border> элемента управления.  Это заставляет курсор изменяться для всего приложения.  
  
 [!code-csharp[cursors#ChangeCursorsSample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)
