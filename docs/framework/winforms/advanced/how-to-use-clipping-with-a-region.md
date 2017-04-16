---
title: "Практическое руководство. Обрезка изображения по границам области обрезки | Microsoft Docs"
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
  - "области, усечение"
  - "области, ограничение поверхности для рисования"
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Обрезка изображения по границам области обрезки
Одним из свойств класса <xref:System.Drawing.Graphics> является область обрезки.  Все операции рисования, выполняемые объектом <xref:System.Drawing.Graphics>, ограничиваются областью обрезки данного объекта <xref:System.Drawing.Graphics>.  Для установки границ области обрезки служит метод <xref:System.Drawing.Graphics.SetClip%2A>.  
  
## Пример  
 В следующем примере создается контур, состоящий из одного многоугольника.  Затем конструируется область на основе созданного ранее контура.  Область передается методу <xref:System.Drawing.Graphics.SetClip%2A> объекта <xref:System.Drawing.Graphics>, а затем отображаются две строки.  
  
 Обрезанные строки показаны на следующем рисунке.  
  
 ![Клип](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Области в GDI\+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)