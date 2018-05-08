---
title: Практическое руководство. Управление буферизацией графики
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: f8675582fe6bafefd94d6a740c3263e407dfd4e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
