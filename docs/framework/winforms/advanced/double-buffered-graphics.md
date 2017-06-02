---
title: "Двойная буферизация графики | Microsoft Docs"
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
  - "двойная буферизация"
  - "примеры [Windows Forms], двойная буферизация графики"
  - "мерцание, сокращение с помощью двойной буферизации"
  - "графика, двойная буферизация"
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Двойная буферизация графики
Мерцание является распространенной проблемой при программировании графики.  Графические операции, требующие нескольких сложных операций рисования, могут привести к тому, что визуализируемые изображения будут мерцать или иметь неприемлемый внешний вид.  Чтобы устранить эти неполадки, .NET Framework предоставляет доступ к двойной буферизации.  
  
 При двойной буферизации для решения проблем, связанных с многократным повторением операций рисования, используется буфер в памяти.  Если двойная буферизация включена, все операции рисования сначала выполняются в памяти, а лишь затем на экране компьютера.  После завершения всех операций рисования содержимое буфера копируется из памяти непосредственно на связанную с ним область экрана.  Поскольку на экране выполняется лишь одна графическая операция, мерцание, которое часто возникает в сложных операциях рисования, исчезает.  
  
## Двойная буферизация по умолчанию  
 Самый простой способ использования двойной буферизации — включить двойную буферизацию по умолчанию для всех форм и элементов управления, предоставляемых .NET Framework.  Чтобы включить двойную буферизацию для форм Windows Forms и элементов управления Windows, необходимо присвоить свойству <xref:System.Windows.Forms.Control.DoubleBuffered%2A> значение `true` или воспользоваться методом <xref:System.Windows.Forms.Control.SetStyle%2A>.  Дополнительные сведения см. в разделе [Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## Управление буферизацией графики вручную  
 В более сложных случаях буферизации, например для отображения анимации или при сложном управлении памятью, можно воспользоваться для реализации собственной логики двойной буферизации классами .NET Framework.  За выделение отдельных буферов графики и управление ими отвечает класс <xref:System.Drawing.BufferedGraphicsContext>.  У каждого домена приложения есть собственный экземпляр <xref:System.Drawing.BufferedGraphicsContext> по умолчанию, который управляет всей двойной буферизацией по умолчанию для данного приложения.  В большинстве случаев у приложения имеется лишь один домен и один экземпляр <xref:System.Drawing.BufferedGraphicsContext> по умолчанию.  Экземпляры <xref:System.Drawing.BufferedGraphicsContext> по умолчанию управляются классом <xref:System.Drawing.BufferedGraphicsManager>.  Ссылку на экземпляр <xref:System.Drawing.BufferedGraphicsContext> по умолчанию можно получить, обратившись к свойству [BufferedGraphicsManager.Current](frlrfSystemDrawingBufferedGraphicsManagerClassCurrentTopic).  Кроме того, можно повысить производительность приложений, активно использующих графические возможности, создав выделенный экземпляр <xref:System.Drawing.BufferedGraphicsContext>.  Дополнительные сведения о создании экземпляра <xref:System.Drawing.BufferedGraphicsContext> см. в разделе [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## Вывод буферизованной графики вручную  
 Чтобы использовать экземпляр класса <xref:System.Drawing.BufferedGraphicsContext> для создания графических буферов, можно вызвать метод [BufferedGraphicsContext.Allocate](frlrfSystemDrawingBufferedGraphicsContextClassAllocateTopic), который возвращает экземпляр класса <xref:System.Drawing.BufferedGraphics>.  Объект <xref:System.Drawing.BufferedGraphics> служит для управления буфером памяти, связанным с областью отрисовки, например с формой или элементом управления.  
  
 После создания объекта класса <xref:System.Drawing.BufferedGraphics> этот объект будет управлять отрисовкой изображения непосредственно в буфере памяти.  Для передачи изображения в буфер памяти можно использовать свойство [BufferedGraphics.Graphics](frlrfSystemDrawingBufferedGraphicsClassGraphicsTopic), которое служит для доступа к объекту <xref:System.Drawing.Graphics>, представляющему собой содержимое этого буфера памяти.  Передача изображений этому объекту <xref:System.Drawing.Graphics> ничем не отличается от передачи изображений объекту <xref:System.Drawing.Graphics>, который представляет собой область экрана.  После записи всей информации об изображении в буфер можно воспользоваться методом [BufferedGraphics.Render](frlrfSystemDrawingBufferedGraphicsClassRenderTopic), чтобы скопировать содержимое буфера в нужную область экрана.  
  
 Дополнительные сведения об использовании класса <xref:System.Drawing.BufferedGraphics> см. в разделе [Отрисовка буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md).  Дополнительные сведения об отрисовке графики см. в разделе [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
  
## См. также  
 <xref:System.Drawing.BufferedGraphics>   
 <xref:System.Drawing.BufferedGraphicsContext>   
 <xref:System.Drawing.BufferedGraphicsManager>   
 [Практическое руководство. Визуализация буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)   
 [Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)   
 [Практическое руководство. Управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)