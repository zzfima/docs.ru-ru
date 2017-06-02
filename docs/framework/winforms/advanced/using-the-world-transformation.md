---
title: "Использование объемного преобразования | Microsoft Docs"
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
  - "графика, мировое преобразование"
  - "мировое преобразование, примеры"
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Использование объемного преобразования
Объемное преобразование является свойством класса <xref:System.Drawing.Graphics>.  Числа, определяющие объемное преобразование, хранятся в объекте <xref:System.Drawing.Drawing2D.Matrix>, представляющем собой матрицу размером 3×3.  Классы <xref:System.Drawing.Drawing2D.Matrix> и <xref:System.Drawing.Graphics> содержат различные методы для установки элементов матрицы объемного преобразования.  
  
## Различные типы преобразований  
 В следующем примере код создает прямоугольник 50×50 и помещает его в точку начала координат \(0, 0\).  Начало координат располагается в верхнем левом углу клиентской области.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 В следующем коде к прямоугольнику применяется масштабирование; коэффициент для оси x равен 1,75, а для оси y — 0,5.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Результатом преобразования является прямоугольник, который длиннее исходного по оси x и короче его по оси y.  
  
 Чтобы вместо масштабирования прямоугольника осуществить его поворот, используйте следующий код:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Чтобы преобразовать прямоугольник, можно использовать следующий код:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## См. также  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [Системы координат и преобразования](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [Использование преобразований в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)