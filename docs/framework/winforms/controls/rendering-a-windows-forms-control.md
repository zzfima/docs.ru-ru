---
title: "Отрисовка элементов управления Windows Forms"
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
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 07e75bd44ab960744224c2d2d2cf2e53c42860fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="rendering-a-windows-forms-control"></a>Отрисовка элементов управления Windows Forms
Отрисовка относится к процессу создания визуального представления на экране пользователя. Windows Forms использует [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (новой библиотеки графики Windows) для подготовки к просмотру. Управляемые классы, предоставляющие доступ к [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] в <xref:System.Drawing?displayProperty=nameWithType> пространства имен и его подпространства.  
  
 Во время отрисовки элемента управления участвуют следующие элементы.  
  
-   Рисование функциональных возможностей, предоставляемых базовым классом <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
-   Главные [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] графическую библиотеку.  
  
-   Геометрия области рисования.  
  
-   Процедура освобождения графических ресурсов.  
  
## <a name="drawing-functionality-provided-by-control"></a>Рисование функциональные возможности, предоставляемые элементом управления  
 Базовый класс <xref:System.Windows.Forms.Control> предоставляет функциональные возможности рисования посредством его <xref:System.Windows.Forms.Control.Paint> событий. Элемент управления вызывает <xref:System.Windows.Forms.Control.Paint> событие каждый раз, когда необходимо обновить его отображения. Дополнительные сведения о событиях в платформе .NET Framework см. в разделе [обработка и вызов событий](../../../../docs/standard/events/index.md).  
  
 Класс данных события для <xref:System.Windows.Forms.Control.Paint> событий, <xref:System.Windows.Forms.PaintEventArgs>, содержащий данные, необходимые для отображения элемента управления — дескриптор графический объект и объект прямоугольник, представляющий область для рисования. Эти объекты, отображаемые полужирным шрифтом в следующем фрагменте кода.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics>является управляемым классом, инкапсулирующим функциональность рисования, как описано в обсуждение [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] далее в этом разделе. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Является экземпляром класса <xref:System.Drawing.Rectangle> структуры и определяет доступные области, в котором можно нарисовать элемент управления. Разработчик элемента управления может вычислить <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> с помощью <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойства элемента управления, как описано в описании геометрии далее в этом разделе.  
  
 Элемент управления должен предоставить логики отрисовки путем переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метод, который наследует от <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A>Получает доступ к графический объект и прямоугольника для рисования с помощью <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойства <xref:System.Windows.Forms.PaintEventArgs> переданным ему экземпляром.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A> Метод базового <xref:System.Windows.Forms.Control> класс не реализует какой-либо функциональности, но просто вызывает делегата события, которые зарегистрированы с помощью <xref:System.Windows.Forms.Control.Paint> событий. При переопределении <xref:System.Windows.Forms.Control.OnPaint%2A>, как правило, следует вызвать <xref:System.Windows.Forms.Control.OnPaint%2A> получать метод базового класса, чтобы зарегистрированные делегаты <xref:System.Windows.Forms.Control.Paint> событий. Тем не менее, элементы управления, которые их всю поверхность рисования не должен вызывать базовый класс <xref:System.Windows.Forms.Control.OnPaint%2A>, как это вызовет мерцание. Пример переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> событий, в разделе [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
>  Не вызывайте <xref:System.Windows.Forms.Control.OnPaint%2A> непосредственно из элемента управления; вместо этого вызовите <xref:System.Windows.Forms.Control.Invalidate%2A> метод (наследуется от <xref:System.Windows.Forms.Control>) или другим методом, который вызывает <xref:System.Windows.Forms.Control.Invalidate%2A>. <xref:System.Windows.Forms.Control.Invalidate%2A> В свою очередь вызывает метод <xref:System.Windows.Forms.Control.OnPaint%2A>. <xref:System.Windows.Forms.Control.Invalidate%2A> Метод перегружен, и в зависимости от аргументов предоставляемое <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, элемент управления перерисовывает некоторые или все его области экрана.  
  
 Базовый <xref:System.Windows.Forms.Control> класс определяет другой метод, который удобен для рисования — <xref:System.Windows.Forms.Control.OnPaintBackground%2A> метод.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>Рисует фон (и тем самым фигуры) окна и гарантированно будет быстро, при <xref:System.Windows.Forms.Control.OnPaint%2A> рисует детали и может работать медленнее, так как индивидуальные запросы на рисование объединены в один <xref:System.Windows.Forms.Control.Paint> событие, которое охватывает все аспекты, которые должны быть перерисовке. Может возникнуть необходимость вызвать <xref:System.Windows.Forms.Control.OnPaintBackground%2A> , если для экземпляра необходимо нарисовать цвета градиента фона для элемента управления.  
  
 Во время <xref:System.Windows.Forms.Control.OnPaintBackground%2A> имеет событийного номенклатуру и принимает тем же аргументом, как `OnPaint` метод <xref:System.Windows.Forms.Control.OnPaintBackground%2A> не является истинным методом события. Имеется не `PaintBackground` событий и <xref:System.Windows.Forms.Control.OnPaintBackground%2A> вызывает делегаты событий. При переопределении метода <xref:System.Windows.Forms.Control.OnPaintBackground%2A> метода производного класса не требуется для вызова <xref:System.Windows.Forms.Control.OnPaintBackground%2A> метод базового класса.  
  
## <a name="gdi-basics"></a>Основные сведения о GDI +  
 <xref:System.Drawing.Graphics> Класс предоставляет методы для рисования различных форм, таких как круги, треугольники, дуги и эллипсы, а также методы для отображения текста. <xref:System.Drawing?displayProperty=nameWithType> Пространства имен и его подпространства содержат классы, инкапсулирующие графические элементы, такие как фигуры (круги, прямоугольники, дуги и другие), цвета, шрифты, кисти и т. д. Дополнительные сведения о [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], в разделе [использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md). Основы [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] описаны в [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Геометрия области рисования  
 <xref:System.Windows.Forms.Control.ClientRectangle%2A> Свойство элемента управления задает прямоугольную область, доступных для элемента управления на экране пользователя во время <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойство <xref:System.Windows.Forms.PaintEventArgs> задает область, которая фактически нарисована. (Помните, что рисование выполняется <xref:System.Windows.Forms.Control.Paint> событие метода, принимающего <xref:System.Windows.Forms.PaintEventArgs> экземпляр в качестве аргумента). Элемент управления может потребовать перерисовать только часть его доступной области, как в случае изменения отображения элемента управления при небольшом разделе. В такой ситуации разработчик элемента управления должен рассчитать фактический прямоугольник для рисования в и передать его <xref:System.Windows.Forms.Control.Invalidate%2A>. Перегруженные версии <xref:System.Windows.Forms.Control.Invalidate%2A> , которые принимают <xref:System.Drawing.Rectangle> или <xref:System.Drawing.Region> в качестве аргумента, используют этот аргумент для создания <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойство <xref:System.Windows.Forms.PaintEventArgs>.  
  
 В следующем фрагменте кода показано использование `FlashTrackBar` прямоугольную область для рисования в вычисляет пользовательского элемента управления. `client` Обозначает переменную <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойство. Полный пример см. в разделе [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Освобождение ресурсов графики  
 Графические объекты обходится дорого, потому что они используют системные ресурсы. Такие объекты содержат экземпляры <xref:System.Drawing.Graphics?displayProperty=nameWithType> класса, а также экземпляры <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>и другие графические классы. Очень важно создать графический ресурс только в том случае, если она необходима и отпустите его сразу после завершения его использования. При создании типа, реализующего <xref:System.IDisposable> интерфейсом, вызовите его <xref:System.IDisposable.Dispose%2A> метод при завершении работы с ним для освобождения ресурсов.  
  
 В следующем фрагменте кода показано использование `FlashTrackBar` пользовательский элемент управления создает и освобождает <xref:System.Drawing.Brush> ресурсов. Полный исходный код в разделе [как: создание Windows Forms элемента управления, показывает ход выполнения](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
