---
title: "Практическое руководство. Установка позиций табуляции для выводимого текста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2acc46a9a3fa2c84138cd9a168113f88ab08e4a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Практическое руководство. Установка позиций табуляции для выводимого текста
Можно установить позиции табуляции для текста путем вызова <xref:System.Drawing.StringFormat.SetTabStops%2A> метод <xref:System.Drawing.StringFormat> объекта и затем передачу, <xref:System.Drawing.StringFormat> объект <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> Поддерживает добавление позиции табуляции для отображаемого текста, несмотря на то, что вы можете развернуть существующую вкладку прекратит использование выполняет <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> флаг.  
  
## <a name="example"></a>Пример  
 В следующем примере задается табуляции в 150, 250 и 350. Затем код отображает список имен и результатов теста с вкладками.  
  
 Ниже показан текст с вкладками.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Приведенный ниже код передает два параметра <xref:System.Drawing.StringFormat.SetTabStops%2A> метод. Второй аргумент — массив, содержащий смещения позиций табуляции. Первый аргумент, переданный <xref:System.Drawing.StringFormat.SetTabStops%2A> является 0, означающее, что первое смещение в массиве отсчитывается от позиции 0, левого края ограничивающего прямоугольника.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Предыдущий пример кода предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
