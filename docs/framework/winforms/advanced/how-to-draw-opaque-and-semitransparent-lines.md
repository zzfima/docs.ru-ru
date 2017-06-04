---
title: "Практическое руководство. Рисование непрозрачных и полупрозрачных линий | Microsoft Docs"
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
  - "альфа-смешение, рисование линий"
  - "рисование, линии"
  - "линии, рисование с альфа-смешением"
  - "прозрачность, линии"
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Рисование непрозрачных и полупрозрачных линий
При рисовании линии необходимо передать методу <xref:System.Drawing.Graphics.DrawLine%2A> класса <xref:System.Drawing.Graphics> объект <xref:System.Drawing.Pen>.  Одним из параметров конструктора <xref:System.Drawing.Pen.%23ctor%2A> является объект <xref:System.Drawing.Color>.  Чтобы нарисовать непрозрачную линию, установите альфа\-компонент цвета равным 255.  Чтобы нарисовать полупрозрачную линию, установите значение альфа\-компонента в диапазоне от 1 до 254.  
  
 При рисовании полупрозрачной линии на некотором фоне цвет линии смешивается с цветами фона.  Альфа\-компонент определяет результат смешивания цветов линии и фона. При близких к нулю значениях альфа цвета фона выделяются в большей степени, а при значениях альфа, близких к 255, в большей степени выделяется цвет линии.  
  
## Пример  
 В примере ниже рисуется растровое изображение, а затем рисуются три линии, использующие растровое изображение в качестве фона.  Цвет первой линии имеет альфа\-компонент, равный 255, поэтому она является непрозрачной.  Для второй и третьей линий используется альфа\-компонент, равный 128, поэтому они являются полупрозрачными и сквозь них можно видеть фоновое изображение.  Оператор, устанавливающий значение свойства <xref:System.Drawing.Graphics.CompositingQuality%2A>, указывает, что смешивание цветов для третьей линии должно совмещаться с гамма\-коррекцией.  
  
 На рисунке ниже показан результат выполнения кода.  
  
 ![Непрозрачный и частично прозрачный](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Альфа\-смешение цвета для линий и заливок](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Практическое руководство. Установка степени прозрачности фона элемента управления](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)   
 [Практическое руководство. Рисование непрозрачными и полупрозрачными кистями](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)