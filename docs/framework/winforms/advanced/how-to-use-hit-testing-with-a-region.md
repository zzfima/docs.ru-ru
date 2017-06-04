---
title: "Практическое руководство. Проверка нахождения указателя мыши в заданной области | Microsoft Docs"
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
  - "проверка нажатия, использование областей"
  - "области, проверка нажатия"
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Проверка нахождения указателя мыши в заданной области
Целью проверки попадания является определение того, находится ли указатель над данным объектом, например значком или кнопкой.  
  
## Пример  
 В следующем примере создается область в форме креста, являющаяся объединением двух прямоугольников.  Предполагается, что переменная `point` содержит координаты последнего по времени щелчка мышью.  В коде осуществляется проверка того, что точка `point` принадлежит области в форме креста.  Если точка лежит в области \(есть попадание\), то эта область закрашивается непрозрачной красной кистью.  В противном случае она закрашивается полупрозрачной красной кистью.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 <xref:System.Drawing.Region>   
 [Области в GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Практическое руководство. Обрезка изображения по границам области обрезки](../../../../docs/framework/winforms/advanced/how-to-use-clipping-with-a-region.md)