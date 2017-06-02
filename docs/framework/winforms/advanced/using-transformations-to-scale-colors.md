---
title: "Масштабирование цветов с применением преобразований | Microsoft Docs"
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
  - "цвета, масштабирование"
  - "преобразования, для масштабирования цветов"
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Масштабирование цветов с применением преобразований
Масштабирующее преобразование умножает один или несколько из четырех компонентов цвета на некоторое число.  Элементы матрицы цветов, соответствующие масштабированию, приводятся в следующей таблице.  
  
|Масштабируемый компонент|Элемент матрицы|  
|------------------------------|---------------------|  
|Красный|\[0\]\[0\]|  
|Зеленый|\[1\]\[1\]|  
|Синий|\[2\]\[2\]|  
|Альфа|\[3\]\[3\]|  
  
## Масштабирование одного цвета  
 В следующем примере создается объект <xref:System.Drawing.Image> на основе файла ColorBars2.bmp.  Затем код масштабирует синий компонент каждого пикселя в изображении с коэффициентом масштабирования, равным 2.  Исходное изображение отображается вместе с преобразованным изображением.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 На следующем рисунке показаны как исходное изображение \(слева\), так и масштабированное изображение \(справа\).  
  
 ![Масштабировать цвета](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 В следующей таблице приводятся цветовые векторы четырех полос до и после масштабирования.  Обратите внимание, что синий компонент цвета четвертой полосы изменился с 0,8 на 0,6.  Это связано с тем, интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] сохраняет только дробную часть результата.  Например, \(2\)\(0,8\) \= 1,6, а дробная часть числа 1,6 равна 0,6.  Сохранение только дробной части гарантирует, что результат всегда попадает в интервал \[0, 1\].  
  
|До преобразования|Масштабированный цвет|  
|-----------------------|---------------------------|  
|\(0.4, 0.4, 0.4, 1\)|\(0.4, 0.4, 0.8, 1\)|  
|\(0.4, 0.2, 0.2, 1\)|\(0.4, 0.2, 0.4, 1\)|  
|\(0.2, 0.4, 0.2, 1\)|\(0.2, 0.4, 0.4, 1\)|  
|\(0.4, 0.4, 0.8, 1\)|\(0.4, 0.4, 0.6, 1\)|  
  
## Масштабирование нескольких цветов  
 В следующем примере создается объект <xref:System.Drawing.Image> на основе файла ColorBars2.bmp.  Затем код масштабирует красный, зеленый и синий компоненты цвета каждого пикселя изображения.  Красные компоненты уменьшаются на 25%, зеленые компоненты — на 35%, а синие — на 50%.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 На следующем рисунке показаны как исходное изображение \(слева\), так и масштабированное изображение \(справа\).  
  
 ![Масштабировать цвета](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 В следующей таблице приводятся цветовые векторы четырех полос до и после масштабирования.  
  
|До преобразования|Масштабированный цвет|  
|-----------------------|---------------------------|  
|\(0.6, 0.6, 0.6, 1\)|\(0.45, 0.39, 0.3, 1\)|  
|\(0, 1, 1, 1\)|\(0, 0.65, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(0.75, 0.65, 0, 1\)|  
|\(1, 0, 1, 1\)|\(0.75, 0, 0.5, 1\)|  
  
## См. также  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Перекрашивание изображений](../../../../docs/framework/winforms/advanced/recoloring-images.md)