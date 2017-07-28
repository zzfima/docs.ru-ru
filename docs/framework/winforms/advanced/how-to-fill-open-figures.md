---
title: "Практическое руководство. Заливка открытых фигур | Microsoft Docs"
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
  - "фигуры, заполнение"
  - "открытые фигуры, заполнение"
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Заливка открытых фигур
Для заливки контура необходимо передать объект <xref:System.Drawing.Drawing2D.GraphicsPath> методу <xref:System.Drawing.Graphics.FillPath%2A>.  Метод <xref:System.Drawing.Graphics.FillPath%2A> осуществляет заливку контура в соответствии с режимом заливки \(альтернативным режимом или режимом заполнения\), установленным для этого контура.  Если контур содержит незамкнутые фигуры, то заливка происходит так, как если бы фигуры были замкнутыми.  Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] замыкает фигуру с помощью прямой линии, соединяющей начальную и конечную точки.  
  
## Пример  
 В следующем примере создается контур, содержащий одну открытую фигуру \(дугу\) и одну замкнутую фигуру \(эллипс\).  Метод <xref:System.Drawing.Graphics.FillPath%2A> производит заливку пути в соответствии с режимом заливки, принятым по умолчанию, т. е. <xref:System.Drawing.Drawing2D.FillMode>.  
  
 На следующем рисунке показан результат выполнения примера кода.  Следует обратить внимание, что контур заполняется \(в соответствии с <xref:System.Drawing.Drawing2D.FillMode>\) так, как будто открытая фигура замкнута с помощью прямого отрезка, соединяющего ее конечную и начальную точки.  
  
 ![Путь для открытия файла](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [Контуры в GDI\+](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)