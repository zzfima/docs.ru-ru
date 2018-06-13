---
title: Практическое руководство. Использование класса отрисовки элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: e5b82c3317d2d162fbd5a182166a9e0061fd770e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534109"
---
# <a name="how-to-use-a-control-rendering-class"></a>Практическое руководство. Использование класса отрисовки элемента управления
В этом примере демонстрируется использование <xref:System.Windows.Forms.ComboBoxRenderer> класса для отображения стрелку раскрывающегося списка поля со списком поле элемента управления. Пример состоит из <xref:System.Windows.Forms.Control.OnPaint%2A> метод простого пользовательского элемента управления. <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Свойство используется для определения, включены ли визуальные стили в клиентской области окна приложения. Если визуальные стили включены, то <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> метода сделает стрелку раскрывающегося списка с применением визуальных стилей; в противном случае <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> метода сделает стрелку раскрывающегося списка в классическом стиле Windows.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Пользовательский элемент управления на основе <xref:System.Windows.Forms.Control> класса.  
  
-   Объект <xref:System.Windows.Forms.Form> , на котором размещается пользовательский элемент управления.  
  
-   Ссылки на <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, и <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
