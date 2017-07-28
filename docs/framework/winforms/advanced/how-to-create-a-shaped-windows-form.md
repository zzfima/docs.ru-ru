---
title: "Практическое руководство. Создание фигурной формы Windows Forms | Microsoft Docs"
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
  - "формы, изменение формы"
  - "формы, циклические"
  - "формы, пользовательские фигуры"
  - "формы, непрямоугольные"
  - "формы, скругленные"
  - "фигурные формы"
  - "Windows Forms, циклические"
  - "Windows Forms, пользовательские фигуры"
  - "Windows Forms, непрямоугольная форма"
  - "Windows Forms, скругленные"
  - "Windows Forms, фигурные"
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание фигурной формы Windows Forms
Пример создает форму в виде эллипса, размеры которого можно изменять.  
  
## Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространства имен <xref:System.Windows.Forms> и <xref:System.Drawing>.  
  
 Этот пример переопределяет метод <xref:System.Windows.Forms.Control.OnPaint%2A>, чтобы изменить фигуру формы.  Чтобы использовать этот код, следует скопировать объявление метода, а также код рисования внутри метода.  
  
## См. также  
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Region>   
 <xref:System.Drawing>   
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>   
 <xref:System.Windows.Forms.Control.Region%2A>   
 [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)