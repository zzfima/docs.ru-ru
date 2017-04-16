---
title: "Практическое руководство. Установка цвета фона для пера | Microsoft Docs"
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
  - "цветные перья"
  - "перья, установка цвета"
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Установка цвета фона для пера
В этом примере для уже созданного объекта <xref:System.Drawing.Pen> задается цвет.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Объект <xref:System.Drawing.Pen> с именем `myPen`.  
  
## Отказоустойчивость  
 После завершения использования объектов, которые потребляют ресурсы системы, например объектов <xref:System.Drawing.Pen>, необходимо вызвать для этих объектов метод <xref:System.Drawing.Pen.Dispose%2A>.  
  
## См. также  
 <xref:System.Drawing.Pen>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Практическое руководство. Создание пера](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Рисование линий и фигур с помощью пера](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Перья, линии и прямоугольники в GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)