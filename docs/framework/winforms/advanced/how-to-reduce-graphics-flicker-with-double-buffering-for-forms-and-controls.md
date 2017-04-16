---
title: "Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления | Microsoft Docs"
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
  - "DoubleBuffered - свойство"
  - "мерцание, сокращение в Windows Forms"
  - "графика, снижение мерцания двойной буферизации"
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления
При двойной буферизации для решения проблем, связанных с многократным повторением операций рисования, используется буфер в памяти.  Если двойная буферизация включена, все операции рисования сначала выполняются в памяти, а лишь затем на экране компьютера.  После завершения всех операций рисования содержимое буфера копируется из памяти непосредственно на связанную с ним область экрана.  Поскольку на экране выполняется лишь одна графическая операция, мерцание, которое часто возникает в сложных операциях рисования, исчезает. Для большинства приложений наилучших результатов можно достичь при использовании двойной буферизации [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] по умолчанию.  Двойная буферизация включена для стандартных элементов управления Windows Forms по умолчанию.  Включить двойную буферизацию в собственных формах и элементах управления можно двумя способами.  Для этого нужно либо присвоить свойству <xref:System.Windows.Forms.Control.DoubleBuffered%2A> значение `true`, либо вызвать метод <xref:System.Windows.Forms.Control.SetStyle%2A>, чтобы сделать флаг <xref:System.Windows.Forms.ControlStyles> равным `true`.  Оба эти способа позволяют включить для создаваемых пользователем форм и элементов управления двойную буферизацию по умолчанию и обеспечить немерцающее отображение графики.  Вызывать метод <xref:System.Windows.Forms.Control.SetStyle%2A> рекомендуется лишь в тех случаях, если пользователем был написан весь код отрисовки элемента управления.  
  
 В более сложных случаях буферизации, например для отображения анимации или при сложном управлении памятью, можно реализовать собственную логику двойной буферизации.  Дополнительные сведения см. в разделе [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
### Уменьшение эффекта дрожания  
  
-   Присвойте свойству <xref:System.Windows.Forms.Control.DoubleBuffered%2A> значение `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \- или \-  
  
-   Вызовите метод <xref:System.Windows.Forms.Control.SetStyle%2A>, чтобы установить флаг <xref:System.Windows.Forms.ControlStyles> равным `true`.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## См. также  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>   
 <xref:System.Windows.Forms.Control.SetStyle%2A>   
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)