---
title: "Практическое руководство. Управление буферизацией графики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 678b9ad5e8f9b40f927a35e98973cabc831c5cf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Практическое руководство. Управление буферизацией графики
Для более сложных случаях буферизации, можно использовать [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] классов для реализации собственной логики двойной буферизации. Этот класс отвечает за выделение и управление отдельных буферов графики является <xref:System.Drawing.BufferedGraphicsContext> класса. Каждое приложение имеет свой собственный по умолчанию <xref:System.Drawing.BufferedGraphicsContext> , управляет всеми двойную буферизацию для этого приложения. Ссылка на этот экземпляр можно получить, вызвав <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Для получения ссылки на значение по умолчанию BufferedGraphicsContext  
  
-   Задать <xref:System.Drawing.BufferedGraphicsManager.Current%2A> свойства, как показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  Необходимо вызвать `Dispose` метод <xref:System.Drawing.BufferedGraphicsContext> ссылки, полученные из <xref:System.Drawing.BufferedGraphicsManager> класса. <xref:System.Drawing.BufferedGraphicsManager> Обрабатывает все выделение памяти и распространения по умолчанию <xref:System.Drawing.BufferedGraphicsContext> экземпляров.  
  
     Для графические приложения, такие как анимация, иногда могут увеличить производительность с помощью специальной <xref:System.Drawing.BufferedGraphicsContext> вместо <xref:System.Drawing.BufferedGraphicsContext> , предоставляемые <xref:System.Drawing.BufferedGraphicsManager>. Это позволяет создавать и управлять ими буферы графики по отдельности, без несения издержек производительности управления все другие буферизованной графики связанных с приложением, то, что память, занятая приложения будет больше.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Чтобы создать выделенный BufferedGraphicsContext  
  
-   Объявите и создайте новый экземпляр <xref:System.Drawing.BufferedGraphicsContext> класса, как показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [Двойная буферизация графики](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [Практическое руководство. Прорисовка буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
