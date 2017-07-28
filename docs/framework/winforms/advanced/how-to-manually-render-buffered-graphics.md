---
title: "Практическое руководство. Визуализация буферизированной графики вручную | Microsoft Docs"
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
  - "BufferedGraphics - класс"
  - "мерцание, сокращение путем ручной отрисовки графики"
  - "графика [Windows Forms], отрисовка"
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Визуализация буферизированной графики вручную
При управлении собственной буферизованной графикой необходимо иметь возможность создавать буферы графики и визуализировать их.  Чтобы создать экземпляр класса <xref:System.Drawing.BufferedGraphics>, связанный с поверхностью рисования на экране, можно вызвать метод <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>.  Этот метод создает экземпляр <xref:System.Drawing.BufferedGraphics>, связанный с определенной поверхностью отрисовки, например формой или элементом управления.  После создания экземпляра <xref:System.Drawing.BufferedGraphics> можно добавлять графические объекты в представляемый им буфер через свойство <xref:System.Drawing.BufferedGraphics.Graphics%2A>.  После выполнения всех операций с графикой можно скопировать содержимое буфера на экран, вызвав метод <xref:System.Drawing.BufferedGraphics.Render%2A>.  
  
> [!NOTE]
>  При выполнении собственной отрисовки потребление памяти увеличится, хотя это увеличение может быть и незначительным.  
  
### Вывод буферизованной графики вручную  
  
1.  Получите ссылку на экземпляр класса <xref:System.Drawing.BufferedGraphicsContext>.  Подробнее см. в разделе [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
2.  Создайте экземпляр класса <xref:System.Drawing.BufferedGraphics>, вызвав метод <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>, как показано в примере ниже.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3.  С помощью свойства <xref:System.Drawing.BufferedGraphics.Graphics%2A> поместите в буфер графические объекты.  Например:  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4.  Завершив операции рисования в графическом буфере, вызовите метод <xref:System.Drawing.BufferedGraphics.Render%2A>, чтобы отрисовать содержимое буфера на связанной с ним поверхности рисования или на указанной поверхности, как показано в примере кода ниже.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5.  Выполнив отрисовку графики, вызовите метод `Dispose` экземпляра <xref:System.Drawing.BufferedGraphics>, чтобы освободить ресурсы системы.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## См. также  
 <xref:System.Drawing.BufferedGraphicsContext>   
 <xref:System.Drawing.BufferedGraphics>   
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)