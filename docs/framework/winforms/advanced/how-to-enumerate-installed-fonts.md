---
title: Практическое руководство. Перебор установленных шрифтов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: e56f06d6f7a762a1ef1ff85fa30751ea64f9f14b
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653747"
---
# <a name="how-to-enumerate-installed-fonts"></a>Практическое руководство. Перебор установленных шрифтов
<xref:System.Drawing.Text.InstalledFontCollection> Класс наследует от <xref:System.Drawing.Text.FontCollection> абстрактного базового класса. Можно использовать <xref:System.Drawing.Text.InstalledFontCollection> объект для перечисления шрифтов, установленных на компьютере. <xref:System.Drawing.Text.FontCollection.Families%2A> Свойство <xref:System.Drawing.Text.InstalledFontCollection> объект представляет собой массив <xref:System.Drawing.FontFamily> объектов.  
  
## <a name="example"></a>Пример  
 Приведенный ниже список имен семейств шрифтов, установленных на компьютере. Код получает <xref:System.Drawing.FontFamily.Name%2A> свойства каждого <xref:System.Drawing.FontFamily> объекта в массиве, возвращенном <xref:System.Drawing.Text.FontCollection.Families%2A> свойство. По мере извлечения имен семейств, они объединяются в форме, разделенный запятыми список. Затем <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класс создает список с разделителями запятыми в прямоугольнике.  
  
 Если запустить пример кода, выходные данные будут, как показано на следующем рисунке:  
  
 ![Снимок экрана, показывающий гарнитуры.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>. Кроме того, следует импортировать <xref:System.Drawing.Text> пространства имен.  
  
## <a name="see-also"></a>См. также
- [Работами со шрифтами и текстом](using-fonts-and-text.md)
