---
title: "Использование вложенных графических контейнеров"
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
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10c5a1b077e4339f17093e5eb935416bb1ae3d1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-nested-graphics-containers"></a>Использование вложенных графических контейнеров
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет контейнеры, которые можно использовать, чтобы временно заменить или дополнить часть состояния в <xref:System.Drawing.Graphics> объекта. Создать контейнер, вызвав <xref:System.Drawing.Graphics.BeginContainer%2A> метод <xref:System.Drawing.Graphics> объекта. Можно вызвать <xref:System.Drawing.Graphics.BeginContainer%2A> несколько раз для создания вложенных контейнеров. Каждый вызов <xref:System.Drawing.Graphics.BeginContainer%2A> должны составлять пару с помощью вызова <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Преобразования во вложенных контейнерах  
 В следующем примере создается <xref:System.Drawing.Graphics> объекта и контейнера внутри этого <xref:System.Drawing.Graphics> объекта. Мировое преобразование объекта <xref:System.Drawing.Graphics> объект является сдвиг 100 единиц по оси x и 80 единиц по оси y. Мировое преобразование контейнера является поворот на 30 градусов. Код выполняет вызов `DrawRectangle(pen, -60, -30, 120, 60)` дважды. Первый вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> внутри контейнера; то есть происходит между вызовами методов <xref:System.Drawing.Graphics.BeginContainer%2A> и <xref:System.Drawing.Graphics.EndContainer%2A>. Второй вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> после вызова метода <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 В приведенном выше коде прямоугольник, полученными в результате внутри контейнера, применяется сначала по мировое преобразование контейнера (поворот), а затем по мировое преобразование объекта <xref:System.Drawing.Graphics> (сдвиг). Прямоугольник, соединяющей вне контейнера, применяется только мировое преобразование объекта <xref:System.Drawing.Graphics> (сдвиг). На следующем рисунке двух прямоугольников.  
  
 ![Вложенные контейнеры](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>Обрезка во вложенных контейнеров  
 В следующем примере показано, каким образом вложенные контейнеры работают с областями обрезки. Код создает <xref:System.Drawing.Graphics> объекта и контейнера внутри этого <xref:System.Drawing.Graphics> объекта. Вырезанной <xref:System.Drawing.Graphics> объект представляет собой прямоугольник, а областью обрезки контейнера — эллипс. В коде осуществляются два вызова <xref:System.Drawing.Graphics.DrawLine%2A> метод. Первый вызов <xref:System.Drawing.Graphics.DrawLine%2A> находится внутри контейнера, а второй вызов <xref:System.Drawing.Graphics.DrawLine%2A> выходит за пределы контейнера (после вызова <xref:System.Drawing.Graphics.EndContainer%2A>). Первая строка обрезается, пересечение указанных областей обрезки. Вторая строка обрезается по прямоугольный вырезанной <xref:System.Drawing.Graphics> объекта.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 На следующем рисунке две обрезанные линии.  
  
 ![Вложенные контейнера](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Как показано в двух приведенных выше примерах, преобразования и области отсечения накапливаются в вложенных контейнеров. Если задать объемные преобразования контейнера и <xref:System.Drawing.Graphics> объекта, оба эти преобразования применяются к отображаемым внутри контейнера. Преобразование контейнера будут применяться первыми, а преобразование <xref:System.Drawing.Graphics> второй применен объект. Если значение области отсечения контейнера и <xref:System.Drawing.Graphics> объектов, отображаемых внутри контейнера будет обрезан пересечением указанных областей обрезки.  
  
## <a name="quality-settings-in-nested-containers"></a>Параметры качества во вложенных контейнеров  
 Параметры качества (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>и т. д) в вложенных контейнеров не суммируются; вместо этого параметры качества контейнера временно замещают параметры качества <xref:System.Drawing.Graphics> объекта. При создании нового контейнера параметры качества для него заданы значения по умолчанию. Например, предположим, что у вас есть <xref:System.Drawing.Graphics> объект с режим сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. При создании контейнера, режим сглаживания в контейнер является режимом сглаживания по умолчанию. Можно задать режим сглаживания контейнера, и любые отображаемых внутри контейнера, будут отрисовываться соответствии с заданными режимом. Объекты, отображаемые после вызова <xref:System.Drawing.Graphics.EndContainer%2A> будет рисоваться с режимом сглаживания (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>), которая была перед вызовом <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Несколько уровней вложенных контейнеров  
 Вы не ограничены один контейнер в <xref:System.Drawing.Graphics> объекта. Можно создать последовательность контейнеров, вложенных друг в друга, и можно указать мировое преобразование, отсеченной области и параметры качества для каждого из этих вложенных контейнеров. Если вызвать метод рисования из внутреннего контейнера преобразования применяются в порядке, начиная с самой внутренней контейнера и заканчивая внешнего контейнера. Объекты, отображаемые из внутреннего контейнера обрезаются пересечением всех областей обрезки.  
  
 В следующем примере создается <xref:System.Drawing.Graphics> и устанавливает его подсказка отрисовки текста <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Код создает два контейнера, один вложен в другой. Подсказка по визуализации текста внешнего контейнера имеет значение <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, а подсказка отрисовки текста внутреннего контейнера имеет значение <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Код выводит на экран три строки: одну из внутреннего контейнера, одну из внешнего контейнера и одну из <xref:System.Drawing.Graphics> сам объект.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 На следующем рисунке три строки. Строки, выводимые из внутреннего контейнера и <xref:System.Drawing.Graphics> объекта, размываются с помощью сглаживания. Строка, выводимая из внешнего контейнера не размываются с помощью сглаживания, так как <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойству <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Вложенные контейнеры](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>См. также  
 <xref:System.Drawing.Graphics>  
 [Управление состоянием графического объекта](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)
