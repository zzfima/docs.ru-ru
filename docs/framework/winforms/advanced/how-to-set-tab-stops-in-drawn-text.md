---
title: Практическое руководство. Установка позиций табуляции для выводимого текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 76431d34504b40a299200693735a0a989127d683
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832311"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Практическое руководство. Установка позиций табуляции для выводимого текста
Позиции табуляции для текста можно задать путем вызова <xref:System.Drawing.StringFormat.SetTabStops%2A> метод <xref:System.Drawing.StringFormat> объекта и неудачами, <xref:System.Drawing.StringFormat> объект <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Делает, поддерживают добавление позиций табуляции для отображаемого текста, несмотря на то, что вы можете развернуть существующую вкладку перестает использовать <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> флаг.  
  
## <a name="example"></a>Пример  
 В следующем примере позициями табуляции в 150, 250 и 350. Затем код отображает список имен и результатов теста с вкладками.  
  
 На следующем рисунке показано текста:  
  
 ![Снимок экрана, показывающий список с вкладками имена и баллы.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Следующий код передаются два аргумента <xref:System.Drawing.StringFormat.SetTabStops%2A> метод. Вторым аргументом является массив, содержащий смещения позиций табуляции. Первый аргумент, переданный <xref:System.Drawing.StringFormat.SetTabStops%2A> равно 0, это означает, что первое смещение в массиве измеряется начиная с позиции 0, левого края ограничивающего прямоугольника.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также
- [Работами со шрифтами и текстом](using-fonts-and-text.md)
- [Практическое руководство. Рисование текста с использованием GDI](how-to-draw-text-with-gdi.md)
