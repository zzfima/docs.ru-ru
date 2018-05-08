---
title: Практическое руководство. Отображение элементов с использованием визуальных стилей
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 284fca2d3f2b8f47b60e4d9c639df4a6bd43c701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-render-a-visual-style-element"></a>Практическое руководство. Отображение элементов с использованием визуальных стилей
<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Пространство имен предоставляет <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> элементы (UI), поддерживаемый визуальные стили интерфейса объекты, представляющие пользователя Windows. В этом разделе демонстрируется использование <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> класса для подготовки к просмотру <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> , представляющий **Выход** и **завершение работы** кнопок, меню «Пуск».  
  
### <a name="to-render-a-visual-style-element"></a>Для подготовки к просмотру элемента визуального стиля  
  
1.  Создание <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> и настройте его на элемент, который требуется нарисовать. Обратите внимание на использование <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> свойство и <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> метод; <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> конструктор вызовет исключение, если визуальные стили отключены или элемент не определен.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2.  Вызовите <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> способ визуализации элемента, который <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> в данный момент представляет.  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Пользовательский элемент управления на основе <xref:System.Windows.Forms.Control> класса.  
  
-   Объект <xref:System.Windows.Forms.Form> , на котором размещается пользовательский элемент управления.  
  
-   Ссылки на <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, и <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
