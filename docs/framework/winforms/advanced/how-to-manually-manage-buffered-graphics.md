---
title: Практическое руководство. Управление буферизацией графики вручную
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968600"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>Практическое руководство. Управление буферизацией графики вручную
Для более сложных сценариев двойного буферизации можно использовать классы .NET Framework для реализации собственной логики двойной буферизации. Класс, ответственный за выделение отдельных графических буферов и управление ими <xref:System.Drawing.BufferedGraphicsContext> , является классом. Каждое приложение имеет собственное значение по <xref:System.Drawing.BufferedGraphicsContext> умолчанию, которое управляет всей двойной буферизацией приложения по умолчанию. Ссылку на этот экземпляр можно получить, вызвав метод <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>Получение ссылки на BufferedGraphicsContext по умолчанию  
  
- <xref:System.Drawing.BufferedGraphicsManager.Current%2A> Задайте свойство, как показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > Вам не нужно вызывать `Dispose` метод <xref:System.Drawing.BufferedGraphicsContext> для ссылки <xref:System.Drawing.BufferedGraphicsManager> , полученной из класса. Обработчик обрабатывает все операции выделения и распределения памяти для экземпляров по умолчанию <xref:System.Drawing.BufferedGraphicsContext>. <xref:System.Drawing.BufferedGraphicsManager>  
  
     Для ресурсоемких графических приложений, таких как анимация, иногда можно повысить производительность, используя выделенный <xref:System.Drawing.BufferedGraphicsContext> вместо, <xref:System.Drawing.BufferedGraphicsContext> предоставленный <xref:System.Drawing.BufferedGraphicsManager>. Это позволяет создавать графические буферы и управлять ими по отдельности без снижения производительности при управлении всеми другими буферизованными графиками, связанными с приложением, хотя объем памяти, потребляемый приложением, будет больше.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>Создание выделенного BufferedGraphicsContext  
  
- Объявите и создайте новый экземпляр <xref:System.Drawing.BufferedGraphicsContext> класса, как показано в следующем примере кода.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Drawing.BufferedGraphicsContext>
- [Двойная буферизация графики](double-buffered-graphics.md)
- [Практическое руководство. Ручная прорисовка буферизованной графики](how-to-manually-render-buffered-graphics.md)
