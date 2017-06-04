---
title: "Использование вложенных графических контейнеров | Microsoft Docs"
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
  - "графика [Windows Forms], усечение"
  - "графика, вложенные контейнеры"
  - "графика, преобразования во вложенных объектах"
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Использование вложенных графических контейнеров
Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет контейнеры, которые можно использовать, чтобы временно заменить или дополнить некоторую составляющую состояния объекта <xref:System.Drawing.Graphics>.  Чтобы создать контейнер, можно вызвать метод <xref:System.Drawing.Graphics.BeginContainer%2A> объекта <xref:System.Drawing.Graphics>.  Для создания вложенных контейнеров можно многократно вызывать метод <xref:System.Drawing.Graphics.BeginContainer%2A>.  Каждому вызову метода <xref:System.Drawing.Graphics.BeginContainer%2A> должен соответствовать вызов метода <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## Преобразования во вложенных контейнерах  
 В приведенном ниже примере создаются объект <xref:System.Drawing.Graphics> и контейнер внутри этого объекта <xref:System.Drawing.Graphics>.  Объемным преобразованием объекта <xref:System.Drawing.Graphics> является сдвиг на 100 единиц в направлении оси x и на 80 единиц в направлении оси y.  Объемным преобразованием контейнера является поворот на 30 градусов.  Код осуществляет вызов метода  `DrawRectangle(pen, -60, -30, 120, 60)`  дважды.  Первый вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> осуществляется внутри контейнера. Это значит, что он происходит между вызовами <xref:System.Drawing.Graphics.BeginContainer%2A> и <xref:System.Drawing.Graphics.EndContainer%2A>.  Второй вызов <xref:System.Drawing.Graphics.DrawRectangle%2A> происходит после вызова <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 В приведенном выше коде к прямоугольнику, рисуемому внутри контейнера, применяется сначала объемное преобразование контейнера \(поворот\), а затем объемное преобразование объекта <xref:System.Drawing.Graphics> \(сдвиг\).  К прямоугольнику, рисуемому вне контейнера, применяется только объемное преобразование объекта <xref:System.Drawing.Graphics> \(сдвиг\).  Два нарисованных прямоугольника показаны на следующем рисунке.  
  
 ![Вложенные контейнеры](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## Обрезка во вложенных контейнерах  
 В приведенном ниже примере демонстрируется, каким образом вложенные контейнеры работают с областями обрезки.  В приведенном примере создаются объект <xref:System.Drawing.Graphics> и контейнер внутри этого объекта <xref:System.Drawing.Graphics>.  Областью обрезки объекта <xref:System.Drawing.Graphics> является прямоугольник, а областью обрезки контейнера — эллипс.  В коде осуществляются два вызова метода <xref:System.Drawing.Graphics.DrawLine%2A>.  Первый вызов <xref:System.Drawing.Graphics.DrawLine%2A> осуществляется внутри контейнера, а второй вызов <xref:System.Drawing.Graphics.DrawLine%2A> — вне контейнера \(после вызова метода <xref:System.Drawing.Graphics.EndContainer%2A>\).  Первая линия обрезается по области, являющейся пересечением двух указанных областей отсечения.  Вторая линия обрезается по прямоугольнику, являющемуся областью обрезки объекта <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Две обрезанные линии показаны на следующем рисунке.  
  
 ![Вложенный контейнер](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Как показывается в двух приведенных выше примерах, преобразования и области обрезки во вложенных контейнерах являются кумулятивными.  Если объемные преобразования устанавливаются как для контейнера, так и для объекта <xref:System.Drawing.Graphics>, к отображаемым внутри контейнера объектам применяются оба эти преобразования.  Сначала применяется преобразование контейнера, а затем осуществляется преобразование объекта <xref:System.Drawing.Graphics>.  Если области обрезки устанавливаются как для контейнера, так и для объекта <xref:System.Drawing.Graphics>, областью обрезки для объектов, отображаемых внутри контейнера, является пересечение указанных областей обрезки.  
  
## Параметры качества во вложенных контейнерах  
 Параметры качества \(<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A> и т. д.\) во вложенных контейнерах не являются кумулятивными; вместо этого параметры качества контейнера временно замещают параметры качества объекта <xref:System.Drawing.Graphics>.  При создании нового контейнера в качестве параметров качества для него устанавливаются значения по умолчанию.  Например, рассмотрим объект <xref:System.Drawing.Graphics> с режимом сглаживания <xref:System.Drawing.Drawing2D.SmoothingMode>.  Когда создается контейнер, режим сглаживания в нем является режимом сглаживания по умолчанию.  Можно свободно устанавливать режим сглаживания контейнера, и любые объекты, отображаемые внутри этого контейнера, будут рисоваться в установленном режиме.  Объекты, рисуемые после вызова метода <xref:System.Drawing.Graphics.EndContainer%2A>, будут рисоваться с режимом сглаживания \(<xref:System.Drawing.Drawing2D.SmoothingMode>\), действовавшим до вызова метода <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## Различные уровни вложенных контейнеров  
 Нет ограничения на использование в объекте <xref:System.Drawing.Graphics> только одного контейнера.  Можно создать последовательность контейнеров, вложенных друг в друга, и указать объемное преобразование, область обрезки и параметры качества для каждого из этих вложенных контейнеров.  Если вызывается какой\-либо метод рисования из контейнера наибольшего уровня вложенности, преобразования применяются по порядку, начиная с этого контейнера и оканчивая контейнером наименьшего уровня вложенности.  Объекты, отображаемые из контейнера наибольшей степени вложенности, обрезаются по области, являющейся пересечением всех областей обрезки.  
  
 В следующем примере создается объект <xref:System.Drawing.Graphics>, для которого устанавливается режим сглаживания текста <xref:System.Drawing.Drawing2D.SmoothingMode>.  В коде создаются два контейнера, один из них вложен в другой.  Для режим сглаживания внешнего контейнера устанавливается значение <xref:System.Drawing.Text.TextRenderingHint>, а для режима сглаживания внутреннего контейнера — <xref:System.Drawing.Drawing2D.SmoothingMode>.  Код выводит на экран три строки: одну из внутреннего контейнера, одну из внешнего контейнера и одну из самого объекта <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Три нарисованные строки показаны на следующем рисунке.  Строки, выводимые из внутреннего контейнера и из объекта <xref:System.Drawing.Graphics>, размываются с помощью сглаживания.  Строка, выводимая из внешнего контейнера, не подвергается сглаживанию, потому что свойство <xref:System.Drawing.Graphics.TextRenderingHint%2A> в этом случае имеет значение <xref:System.Drawing.Text.TextRenderingHint>.  
  
 ![Вложенные контейнеры](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## См. также  
 <xref:System.Drawing.Graphics>   
 [Управление состоянием объекта Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)