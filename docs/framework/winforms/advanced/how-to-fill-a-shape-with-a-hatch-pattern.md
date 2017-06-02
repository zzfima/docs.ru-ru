---
title: "Практическое руководство. Штриховая заливка фигуры | Microsoft Docs"
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
  - "кисти, использование штриховых кистей"
  - "шаблоны, добавление к фигурам"
  - "фигуры, заливка узорами"
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Штриховая заливка фигуры
Шаблон штриховки содержит два цвета: один из них является фоновым, а другой используется для линий, формирующих шаблон на этом фоне.  Для штриховой заливки замкнутой фигуры используется объект <xref:System.Drawing.Drawing2D.HatchBrush>.  В следующем примере демонстрируется штриховая заливка эллипса.  
  
## Пример  
 Конструктор <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> принимает три параметра: стиль штриховки, цвет штриховой линии и цвет фона.  Параметр, определяющий стиль штриховки, может принимать любое значение из перечисления <xref:System.Drawing.Drawing2D.HatchStyle>.  В перечислении <xref:System.Drawing.Drawing2D.HatchStyle> более пятидесяти элементов, некоторые из них приводятся в следующем списке:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
 Эллипс после заливки представлен на следующем рисунке.  
  
 ![Шаблон штриховки](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)