---
title: Отрисовка элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 0e1a7ca5dc0414d518c081b1db2dca5477d4f743
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742382"
---
# <a name="rendering-a-windows-forms-control"></a>Отрисовка элементов управления Windows Forms
Отрисовка обозначает процесс создания визуального представления на экране пользователя. Для отрисовки Windows Forms использует GDI (Новая библиотека графики Windows). Управляемые классы, предоставляющие доступ к GDI, находятся в пространстве имен <xref:System.Drawing?displayProperty=nameWithType> и его подпространствах имен.  
  
 При отрисовке элемента управления участвуют следующие элементы:  
  
- Функции рисования, предоставляемые базовым классом <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
- Неотъемлемые элементы библиотеки графических интерфейсов GDI.  
  
- Геометрия области рисования.  
  
- Процедура высвобождения графических ресурсов.  
  
## <a name="drawing-functionality-provided-by-control"></a>Функциональные возможности рисования, предоставляемые элементом управления  
 Базовый класс <xref:System.Windows.Forms.Control> предоставляет функции рисования с помощью <xref:System.Windows.Forms.Control.Paint> события. Элемент управления вызывает событие <xref:System.Windows.Forms.Control.Paint>, когда ему требуется обновить его отображение. Дополнительные сведения о событиях в .NET Framework см. в разделе [обработка и вызов событий](../../../standard/events/index.md).  
  
 Класс данных событий для события <xref:System.Windows.Forms.Control.Paint>, <xref:System.Windows.Forms.PaintEventArgs>, содержит данные, необходимые для рисования элемента управления — маркер для графического объекта и объект Rectangle, представляющий регион для рисования. Эти объекты показаны жирным шрифтом в следующем фрагменте кода.  
  
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
  
 <xref:System.Drawing.Graphics> является управляемым классом, который инкапсулирует функциональные возможности рисования, как описано в разделе о GDI далее в этой статье. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> является экземпляром структуры <xref:System.Drawing.Rectangle> и определяет доступную область, в которой может нарисоваться элемент управления. Разработчик элемента управления может вычислить <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> с помощью свойства <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> элемента управления, как описано в обсуждении геометрии далее в этом разделе.  
  
 Элемент управления должен предоставлять логику отрисовки путем переопределения метода <xref:System.Windows.Forms.Control.OnPaint%2A>, который он наследует от <xref:System.Windows.Forms.Control>. <xref:System.Windows.Forms.Control.OnPaint%2A> получает доступ к графическому объекту и прямоугольнику для рисования через <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойства экземпляра <xref:System.Windows.Forms.PaintEventArgs>, переданного в него.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Метод <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса <xref:System.Windows.Forms.Control> не реализует никаких функций рисования, но вызывает только делегаты событий, зарегистрированные в событии <xref:System.Windows.Forms.Control.Paint>. При переопределении <xref:System.Windows.Forms.Control.OnPaint%2A>обычно следует вызывать метод <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса, чтобы зарегистрированные делегаты получали событие <xref:System.Windows.Forms.Control.Paint>. Однако элементы управления, которые отрисовываются всю поверхность, не должны вызывать <xref:System.Windows.Forms.Control.OnPaint%2A>базового класса, так как это приводит к мерцанию. Пример переопределения события <xref:System.Windows.Forms.Control.OnPaint%2A> см. в разделе [как создать элемент управления Windows Forms, отображающий ход выполнения](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
> [!NOTE]
> Не вызывайте <xref:System.Windows.Forms.Control.OnPaint%2A> непосредственно из элемента управления; Вместо этого вызовите метод <xref:System.Windows.Forms.Control.Invalidate%2A> (наследуется от <xref:System.Windows.Forms.Control>) или другой метод, который вызывает <xref:System.Windows.Forms.Control.Invalidate%2A>. Метод <xref:System.Windows.Forms.Control.Invalidate%2A>, в свою очередь, вызывает <xref:System.Windows.Forms.Control.OnPaint%2A>. Метод <xref:System.Windows.Forms.Control.Invalidate%2A> перегружен и, в зависимости от аргументов, передаваемых в <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, элемент управления перерисовывает часть его экранной области.  
  
 Базовый класс <xref:System.Windows.Forms.Control> определяет другой метод, который удобен для рисования — метод <xref:System.Windows.Forms.Control.OnPaintBackground%2A>.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> рисует фон (и, таким образом, форму) окна и гарантированно будет быстрым, в то время как <xref:System.Windows.Forms.Control.OnPaint%2A> закрашивает сведения и может быть медленнее, поскольку отдельные запросы на рисование объединяются в одно событие <xref:System.Windows.Forms.Control.Paint>, охватывающее все области, которые необходимо перерисовать. Может потребоваться вызвать <xref:System.Windows.Forms.Control.OnPaintBackground%2A> если, например, нужно нарисовать градиентный фон для элемента управления.  
  
 Хотя <xref:System.Windows.Forms.Control.OnPaintBackground%2A> имеет элемент, подобный событиям и принимающий тот же аргумент, что и метод `OnPaint`, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> не является истинным методом события. События `PaintBackground` и <xref:System.Windows.Forms.Control.OnPaintBackground%2A> не вызывают делегаты событий. При переопределении метода <xref:System.Windows.Forms.Control.OnPaintBackground%2A> производный класс не требуется для вызова метода <xref:System.Windows.Forms.Control.OnPaintBackground%2A> своего базового класса.  
  
## <a name="gdi-basics"></a>Основы GDI+  
 Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования различных фигур, таких как круги, треугольники, дуги и эллипсы, а также методы для отображения текста. Пространство имен <xref:System.Drawing?displayProperty=nameWithType> и его подпространств имен содержат классы, инкапсулирующие графические элементы, такие как фигуры (круги, прямоугольники, дуги и др.), цвета, шрифты, кисти и т. д. Дополнительные сведения о GDI см. [в разделе Использование управляемых графических классов](../advanced/using-managed-graphics-classes.md). Основные сведения о GDI также описаны в разделе [как создать элемент управления Windows Forms, отображающий ход выполнения](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## <a name="geometry-of-the-drawing-region"></a>Геометрия области рисования  
 Свойство <xref:System.Windows.Forms.Control.ClientRectangle%2A> элемента управления указывает прямоугольную область, доступную для элемента управления на экране пользователя, а свойство <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> объекта <xref:System.Windows.Forms.PaintEventArgs> — область, которая на самом деле окрашена. (Помните, что рисование выполняется в <xref:System.Windows.Forms.Control.Paint> методе события, который принимает экземпляр <xref:System.Windows.Forms.PaintEventArgs> в качестве аргумента). Элементу управления может потребоваться закрасить только часть его доступной области, как в случае, когда изменяется небольшой раздел экрана элемента управления. В таких ситуациях разработчик элемента управления должен вычислить фактический прямоугольник для рисования и передать его в <xref:System.Windows.Forms.Control.Invalidate%2A>. Перегруженные версии <xref:System.Windows.Forms.Control.Invalidate%2A>, принимающие <xref:System.Drawing.Rectangle> или <xref:System.Drawing.Region> в качестве аргумента, используют этот аргумент для создания <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойства <xref:System.Windows.Forms.PaintEventArgs>.  
  
 В следующем фрагменте кода показано, как `FlashTrackBar` настраиваемый элемент управления рассчитывает прямоугольную область для рисования. Переменная `client` обозначает свойство <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>. Полный пример см. в разделе [как создать элемент управления Windows Forms, отображающий ход выполнения](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Освобождение графических ресурсов  
 Объекты Graphics являются ресурсоемкими, так как они используют системные ресурсы. К таким объектам относятся экземпляры класса <xref:System.Drawing.Graphics?displayProperty=nameWithType>, а также экземпляры <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>и других графических классов. Очень важно создать графический ресурс только в том случае, если он вам нужен, и сразу выпустить его, как только вы завершите его использование. При создании типа, реализующего интерфейс <xref:System.IDisposable>, вызовите его метод <xref:System.IDisposable.Dispose%2A>, когда завершите работу с ним, чтобы освободить ресурсы.  
  
 В следующем фрагменте кода показано, как пользовательский элемент управления `FlashTrackBar` создает и освобождает ресурс <xref:System.Drawing.Brush>. Полный исходный код см. в разделе [как создать элемент управления Windows Forms, отображающий ход выполнения](how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](how-to-create-a-windows-forms-control-that-shows-progress.md)
