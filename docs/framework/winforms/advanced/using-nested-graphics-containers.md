---
title: Использование вложенных графических контейнеров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182468"
---
# <a name="using-nested-graphics-containers"></a>Использование вложенных графических контейнеров
GDI предоставляет контейнеры, которые можно использовать для временной замены <xref:System.Drawing.Graphics> или увеличения части состояния в объекте. Вы создаете контейнер, <xref:System.Drawing.Graphics.BeginContainer%2A> вызывая <xref:System.Drawing.Graphics> метод объекта. Вы можете <xref:System.Drawing.Graphics.BeginContainer%2A> звонить неоднократно, чтобы сформировать вложенные контейнеры. Каждый <xref:System.Drawing.Graphics.BeginContainer%2A> звонок должен быть сопряжен <xref:System.Drawing.Graphics.EndContainer%2A>с вызовом.  
  
## <a name="transformations-in-nested-containers"></a>Преобразования в nested контейнерах  
 Следующий пример <xref:System.Drawing.Graphics> создает объект и <xref:System.Drawing.Graphics> контейнер внутри этого объекта. Мировая трансформация <xref:System.Drawing.Graphics> объекта представляет собой перевод 100 единиц в направлении x и 80 единиц в направлении y. Мировая трансформация контейнера представляет собой 30-градусное вращение. Код делает звонок `DrawRectangle(pen, -60, -30, 120, 60)` дважды. Первый вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> находится внутри контейнера; то есть, вызов находится между <xref:System.Drawing.Graphics.BeginContainer%2A> вызовами и <xref:System.Drawing.Graphics.EndContainer%2A>. Второй вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> находится после вызова <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 В предыдущем коде прямоугольник, взятый изнутри контейнера, преобразуется сначала мировой трансформацией контейнера <xref:System.Drawing.Graphics> (вращения), а затем мировой трансформацией объекта (переводом). Прямоугольник, вырисованный извне контейнера, преобразуется только мировой трансформацией <xref:System.Drawing.Graphics> объекта (переводом). На следующей иллюстрации показаны два прямоугольника:
  
 ![Иллюстрация, которая показывает вложенные контейнеры.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Отсечение в вложенных контейнерах  
 Следующий пример показывает, как вложенные контейнеры обрабатывают области отсечения. Код создает <xref:System.Drawing.Graphics> объект и контейнер <xref:System.Drawing.Graphics> внутри этого объекта. Область отсечения <xref:System.Drawing.Graphics> объекта представляет собой прямоугольник, а область отсечения контейнера — эллипс. Код делает два вызова <xref:System.Drawing.Graphics.DrawLine%2A> метода. Первый вызов <xref:System.Drawing.Graphics.DrawLine%2A> находится внутри контейнера, а <xref:System.Drawing.Graphics.DrawLine%2A> второй звонок находится за <xref:System.Drawing.Graphics.EndContainer%2A>пределами контейнера (после вызова). Первая линия обрезается пересечением двух областей отсечения. Вторая линия обрезается только прямоугольной областью <xref:System.Drawing.Graphics> отсечения объекта.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 На следующей иллюстрации показаны две обрезанные линии:
  
 ![Иллюстрация, на рисунке вложенный контейнер с обрезанными линиями.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Как видно из двух предыдущих примеров, преобразования и области отсечения являются кумулятивными в вложенных контейнерах. Если установить мировые преобразования контейнера <xref:System.Drawing.Graphics> и объекта, то оба преобразования будут применяться к элементам, взятым из контейнера. Преобразование контейнера будет применяться в первую очередь, а преобразование <xref:System.Drawing.Graphics> объекта будет применяться во-вторых. При установке областей отсечения контейнера и <xref:System.Drawing.Graphics> объекта элементы, взятые из контейнера, будут обрезаны пересечением двух областей отсечения.  
  
## <a name="quality-settings-in-nested-containers"></a>Настройки качества в вложенных контейнерах  
 Настройки качества<xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.TextRenderingHint%2A>(, и т.п.) в вложенных контейнерах не являются кумулятивными; скорее, параметры качества контейнера временно заменяют параметры <xref:System.Drawing.Graphics> качества объекта. При создании нового контейнера параметры качества этого контейнера устанавливаются значениями по умолчанию. Например, предположим, <xref:System.Drawing.Graphics> что у вас <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>есть объект с режимом сглаживания. При создании контейнера режим сглаживания внутри контейнера является режимом сглаживания по умолчанию. Вы можете установить режим сглаживания контейнера, и любые предметы, взятые из контейнера, будут нарисованы в соответствии с режимом, который вы установите. Элементы, нарисованные после вызова, <xref:System.Drawing.Graphics.EndContainer%2A> будут нарисованы в соответствии с режимом сглаживания (),<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>который был на месте до <xref:System.Drawing.Graphics.BeginContainer%2A>вызова.  
  
## <a name="several-layers-of-nested-containers"></a>Несколько слоев вложенных контейнеров  
 Вы не ограничены одним <xref:System.Drawing.Graphics> контейнером в объекте. Можно создать последовательность контейнеров, каждый из которых вложен в предшествующее, и можно указать преобразование мира, область отсечения и параметры качества каждого из этих вложенных контейнеров. Если вы называете метод рисования изнутри внутреннего контейнера, преобразования будут применены в порядке, начиная с внутреннего контейнера и заканчивая внешним контейнером. Элементы, извлеченные из внутреннего контейнера, будут обрезаны пересечением всех областей отсечения.  
  
 Следующий пример <xref:System.Drawing.Graphics> создает объект и устанавливает его <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>намек на визуализацию текста. Код создает два контейнера, один из них вложен в другой. Текст отображения намек на <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>внешний контейнер установлен на , и текст <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>рендеринга намек внутреннего контейнера установлен на . Код рисует три строки: одну из внутреннего контейнера, одну из <xref:System.Drawing.Graphics> внешнего контейнера и одну из самого объекта.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 На следующей иллюстрации показаны три строки. Строки, взятые из внутреннего <xref:System.Drawing.Graphics> контейнера и от объекта, сглаживаются путем антиализа. Строка, извлеченная из внешнего контейнера, не сглаживается антиализамией, так как <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство настроено на <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Иллюстрация, которая показывает строки, взятые из вложенных контейнеров.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Drawing.Graphics>
- [Управление состоянием объекта Graphics](managing-the-state-of-a-graphics-object.md)
