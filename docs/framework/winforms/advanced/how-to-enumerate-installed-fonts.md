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
ms.openlocfilehash: 9f31880cbfb42c03122fc7d2730b9ca89db49226
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524443"
---
# <a name="how-to-enumerate-installed-fonts"></a>Практическое руководство. Перебор установленных шрифтов
<xref:System.Drawing.Text.InstalledFontCollection> Класс наследует от <xref:System.Drawing.Text.FontCollection> абстрактного базового класса. Можно использовать <xref:System.Drawing.Text.InstalledFontCollection> объектов для перечисления шрифтов, установленных на компьютере. <xref:System.Drawing.Text.FontCollection.Families%2A> Свойство <xref:System.Drawing.Text.InstalledFontCollection> объект представляет собой массив <xref:System.Drawing.FontFamily> объектов.  
  
## <a name="example"></a>Пример  
 Приведенный ниже список имен семейств шрифтов, установленных на компьютере. Этот код извлекает <xref:System.Drawing.FontFamily.Name%2A> каждого экземпляра <xref:System.Drawing.FontFamily> объект в массиве, возвращенном <xref:System.Drawing.Text.FontCollection.Families%2A> свойство. По мере извлечения имен семейств шрифтов объединяются в формы, разделенный запятыми список. Затем <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса рисует список разделенных запятыми, в прямоугольнике.  
  
 Если вы выполните этот пример кода, выходные данные будут, как показано на следующем рисунке.  
  
 ![Установленные шрифты](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>. Кроме того, необходимо импортировать <xref:System.Drawing.Text> пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
