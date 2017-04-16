---
title: "Практическое руководство. Управление буферизацией графики | Microsoft Docs"
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
  - "BufferedGraphicsContext - класс"
  - "мерцание, сокращение путем ручного управления графикой"
  - "графика, управление буферизацией"
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Управление буферизацией графики
В более сложных случаях буферизации можно воспользоваться классом [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], чтобы реализовать собственную логику двойной буферизации.  За выделение отдельных буферов графики и управление ими отвечает класс <xref:System.Drawing.BufferedGraphicsContext>.  У каждого приложения есть собственный контекст <xref:System.Drawing.BufferedGraphicsContext> по умолчанию, который управляет всей двойной буферизацией по умолчанию для данного приложения.  Ссылку на этот экземпляр можно получить, вызвав метод <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### Получение ссылки на объект BufferedGraphicsContext по умолчанию  
  
-   Установите свойство <xref:System.Drawing.BufferedGraphicsManager.Current%2A>, как показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Не нужно вызывать метод `Dispose` по ссылке <xref:System.Drawing.BufferedGraphicsContext>, полученной у класса <xref:System.Drawing.BufferedGraphicsManager>.  Объект <xref:System.Drawing.BufferedGraphicsManager> обрабатывает все выделение и распределение памяти для экземпляров <xref:System.Drawing.BufferedGraphicsContext> по умолчанию.  
  
     В приложениях, активно использующих графические возможности, например для показа анимации, бывает можно повысить производительность за счет использования выделенного объекта <xref:System.Drawing.BufferedGraphicsContext> вместо объекта <xref:System.Drawing.BufferedGraphicsContext>, предоставляемого классом <xref:System.Drawing.BufferedGraphicsManager>.  Это дает возможность создавать графические буферы и управлять ими по отдельности, не снижая производительность за счет управления остальными графическими буферами, связанными с приложениями. Но объем потребляемой приложением памяти в этом случае возрастет.  
  
### Создание выделенного объекта BufferedGraphicsContext  
  
-   Объявите и создайте экземпляр класса <xref:System.Drawing.BufferedGraphicsContext>, как это показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## См. также  
 <xref:System.Drawing.BufferedGraphicsContext>   
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Практическое руководство. Визуализация буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)