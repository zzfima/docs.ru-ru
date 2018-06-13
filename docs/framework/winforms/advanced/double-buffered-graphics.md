---
title: Двойная буферизация графики
ms.date: 03/30/2017
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
ms.openlocfilehash: ea4b4b8616ed0b3eab2ddd6b2ec57a39909a0fce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524070"
---
# <a name="double-buffered-graphics"></a>Двойная буферизация графики
Мерцание является распространенной проблемой при программировании графики. Графические операции, требующие нескольких сложных операций рисования, могут вызвать мерцание отображаемых изображений или иным образом нарушить их восприятие. Чтобы устранить эти проблемы, .NET Framework предоставляет доступ к двойной буферизации.  
  
 Двойная буферизация использует буфер памяти для решения проблем мерцания, связанных с несколькими операциями рисования. Если двойная буферизация включена, все операции рисования сначала обрабатываются в буфере памяти вместо области рисования на экране. После завершения всех операций рисования буфер памяти копируется непосредственно в связанную с ним область рисования. Поскольку на экране выполняется лишь одна графическая операция, удается избежать мерцания, связанного со сложными операциями рисования.  
  
## <a name="default-double-buffering"></a>Двойная буферизация по умолчанию  
 Самый простой способ использования двойной буферизации в приложении — использование двойной буферизации по умолчанию для форм и элементов управления, предоставляемой .NET Framework. Вы можете включить двойную буферизацию для форм Windows Forms и элементов управления Windows, задав <xref:System.Windows.Forms.Control.DoubleBuffered%2A> свойства `true` или с помощью <xref:System.Windows.Forms.Control.SetStyle%2A> метод. Дополнительные сведения см. в разделе [Практическое руководство. Уменьшение эффекта дрожания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md).  
  
## <a name="manually-managing-buffered-graphics"></a>Управление буферизацией графики вручную  
 В более сложных сценариях буферизации, например при анимации или сложном управлении памятью, можно использовать классы .NET Framework для реализации вашей собственной логики двойной буферизации. Этот класс отвечает за выделение и управление отдельных буферов графики является <xref:System.Drawing.BufferedGraphicsContext> класса. Каждый домен приложения имеет свой собственный по умолчанию <xref:System.Drawing.BufferedGraphicsContext> экземпляр, который управляет всеми двойную буферизацию для этого приложения. В большинстве случаев будет существовать только один домен приложения для каждого приложения, поэтому обычно есть одно значение по умолчанию <xref:System.Drawing.BufferedGraphicsContext> каждого приложения. По умолчанию <xref:System.Drawing.BufferedGraphicsContext> управлять экземплярами с <xref:System.Drawing.BufferedGraphicsManager> класса. Можно получить ссылку на значение по умолчанию <xref:System.Drawing.BufferedGraphicsContext> экземпляр путем вызова <xref:System.Drawing.BufferedGraphicsManager.Current%2A>. Можно также создать выделенную <xref:System.Drawing.BufferedGraphicsContext> экземпляр, который может повысить производительность графические приложения. Дополнительные сведения о создании <xref:System.Drawing.BufferedGraphicsContext> см. в разделе [как: управление буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md).  
  
## <a name="manually-displaying-buffered-graphics"></a>Вывод буферизованной графики вручную  
 Можно использовать экземпляр <xref:System.Drawing.BufferedGraphicsContext> класса, чтобы создать буферы графики, вызвав <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>, который возвращает экземпляр класса <xref:System.Drawing.BufferedGraphics> класса. Объект <xref:System.Drawing.BufferedGraphics> управляет буфером памяти, связанный с поверхностью отрисовки, например формы или элемента управления.  
  
 После создания экземпляра, <xref:System.Drawing.BufferedGraphics> класс управляет отрисовки в буфер в памяти графики. Можно подготовить к просмотру графический буфер памяти через <xref:System.Drawing.BufferedGraphics.Graphics%2A>, который предоставляет <xref:System.Drawing.Graphics> объект, который непосредственно представляет буфера памяти. Вы можете отобразить к этому <xref:System.Drawing.Graphics> объекта так же, как и для <xref:System.Drawing.Graphics> , представляющий поверхность рисования. После графики в буфер, можно использовать <xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType> следует скопировать содержимое буфера на поверхность рисования на экране.  
  
 Дополнительные сведения об использовании <xref:System.Drawing.BufferedGraphics> см. в описании [вручную визуализации буферизацией графики](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md). Дополнительные сведения об отрисовке графики см. в разделе [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [Практическое руководство. Прорисовка буферизированной графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [Практическое руководство. Уменьшение эффекта мерцания изображения посредством двойной буферизации для форм и элементов управления](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [Практическое руководство. Управление буферизацией графики вручную](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
