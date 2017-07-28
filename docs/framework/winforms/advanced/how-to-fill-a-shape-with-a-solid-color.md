---
title: "Практическое руководство. Заливка фигуры сплошным цветом | Microsoft Docs"
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
  - "цвета, добавление к фигурам"
  - "фигуры, заполнение"
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Заливка фигуры сплошным цветом
Чтобы залить фигуру сплошным цветом, создайте объект <xref:System.Drawing.SolidBrush> и передайте его в качестве параметра одному из методов заливки класса <xref:System.Drawing.Graphics>.  В следующем примере демонстрируется заливка эллипса сплошным красным цветом.  
  
## Пример  
 В приведенном выше коде конструктор <xref:System.Drawing.SolidBrush.%23ctor%2A> получает в качестве своего единственного параметра объект <xref:System.Drawing.Color>.  Значения, используемые методом <xref:System.Drawing.Color.FromArgb%2A>, соответствуют альфа\-, красному, зеленому и синему компонентам цвета.  Каждое из указанных значений должно лежать в диапазоне от 0 до 255.  Первое число 255 указывает, что цвет является абсолютно непрозрачным, а второе число 255 соответствует наибольшей интенсивности красного компонента.  Два нуля показывают, что зеленый и синий компоненты оба имеют нулевую интенсивность.  
  
 Четыре числа \(0, 0, 100, 60\), передаваемые методу <xref:System.Drawing.Graphics.FillEllipse%2A>, определяют положение и размер прямоугольника, ограничивающего рисуемый эллипс.  Верхний левый угол прямоугольника располагается в точке \(0, 0\), ширина прямоугольника равна 100, а высота — 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)