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
ms.openlocfilehash: 8821f6170b8ba588e3197ef54eab14c2719a6cc3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947821"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Практическое руководство. Установка позиций табуляции для выводимого текста
Можно задать позиции табуляции для текста, вызвав <xref:System.Drawing.StringFormat.SetTabStops%2A> метод <xref:System.Drawing.StringFormat> объекта и <xref:System.Drawing.Graphics.DrawString%2A> передав этот <xref:System.Drawing.StringFormat> объект методу <xref:System.Drawing.Graphics> класса.  
  
> [!NOTE]
> Не поддерживает добавление табуляции к рисуемому тексту, хотя существующие позиции табуляции можно развернуть <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> с помощью флага. <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>  
  
## <a name="example"></a>Пример  
 В следующем примере задаются позиции табуляции в 150, 250 и 350. Затем в коде отображается список имен и оценок теста с вкладками.  
  
 На следующем рисунке показан текст с вкладками:  
  
 ![Снимок экрана, на котором показан список имен и оценок с вкладками.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Следующий код передает <xref:System.Drawing.StringFormat.SetTabStops%2A> методу два аргумента. Вторым аргументом является массив, содержащий смещения табуляции. Первый аргумент, передаваемый <xref:System.Drawing.StringFormat.SetTabStops%2A> в, равен 0, что означает, что первое смещение в массиве измеряется от позиции 0, левого края ограничивающего прямоугольника.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Предыдущий пример предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, <xref:System.Windows.Forms.PaintEventHandler>что является параметром.  
  
## <a name="see-also"></a>См. также

- [Работами со шрифтами и текстом](using-fonts-and-text.md)
- [Практическое руководство. Рисование текста с помощью GDI](how-to-draw-text-with-gdi.md)
