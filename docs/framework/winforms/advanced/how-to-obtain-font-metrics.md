---
title: "Практическое руководство. Получение метрик шрифтов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "метрики шрифтов, получение"
  - "шрифты, получение метрик"
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Получение метрик шрифтов
Класс <xref:System.Drawing.FontFamily> предоставляет следующие методы для получения различных метрик для некоторой комбинации "семейство шрифтов — начертание".  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A>\(FontStyle\)  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A>\(FontStyle\)  
  
 Численные значения, возвращаемые этими методами, приводятся в специальных единицах, применяемых при разработке шрифта, поэтому они не зависят от размера и единиц измерения конкретного объекта <xref:System.Drawing.Font>.  
  
 Различные метрики шрифтов показаны на следующем рисунке.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")  
  
## Пример  
 В следующем примере отображаются метрики обычного начертания шрифтов семейства Arial.  Кодом также создается объект <xref:System.Drawing.Font> \(на основе семейства шрифтов Arial\) с размером в 16 пикселей и отображаются метрики \(в пикселях\) для этого объекта <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан результат выполнения примера кода.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")  
  
 Обратите внимание на две первые строки текста из приведенного выше рисунка.  Объект <xref:System.Drawing.Font> возвращает в качестве размера 16, а объект <xref:System.Drawing.FontFamily> возвращает размер максимального пробела, равный 2048.  Указанные два числа \(16 и 2048\) являются основой для преобразования между единицами измерения, применяемыми при разработке шрифта, и единицами измерения объекта <xref:System.Drawing.Font> \(в данном случае это пиксели\).  
  
 Например, можно преобразовать проектные единицы измерения верхнего выносного элемента в пиксели следующим образом.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")  
  
 Приведенный выше код располагает текст по вертикали, устанавливая значение члена <xref:System.Drawing.PointF.Y%2A> объекта <xref:System.Drawing.PointF>.  Координата y увеличивается на значение `font.Height` для каждой новой строки текста.  Свойство <xref:System.Drawing.Font.Height%2A> объекта <xref:System.Drawing.Font> возвращает межстрочный интервал \(в пикселях\) для рассматриваемого объекта <xref:System.Drawing.Font>.  В данном примере возвращаемое значение <xref:System.Drawing.Font.Height%2A> равно 19.  Обратите внимание, что оно равно численному значению \(округленному до большего целого\), получаемому при преобразовании метрики межстрочного интервала в пиксели.  
  
 Обратите также внимание, что размер максимального пробела \(называемый также эм\-размером\) не равен сумме размеров верхнего и нижнего выносных элементов.  Сумма размеров верхнего и нижнего выносных элементов называется высотой клетки.  Размер максимального пробела вычисляется как разность между высотой клетки и внутренним интерлиньяжем.  Сумма высоты клетки и внешнего интерлиньяжа равна междустрочному интервалу.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)