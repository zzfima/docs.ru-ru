---
title: Отрисовка элементов управления Windows Forms
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
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968279"
---
# <a name="rendering-a-windows-forms-control"></a>Отрисовка элементов управления Windows Forms
Отрисовка обозначает процесс создания визуального представления на экране пользователя. Для отрисовки Windows Forms использует GDI (Новая библиотека графики Windows). Управляемые классы, предоставляющие доступ к GDI, находятся в <xref:System.Drawing?displayProperty=nameWithType> пространстве имен и его подпространствах имен.  
  
 При отрисовке элемента управления участвуют следующие элементы:  
  
- Функциональные возможности рисования, предоставляемые базовым <xref:System.Windows.Forms.Control?displayProperty=nameWithType>классом.  
  
- Неотъемлемые элементы библиотеки графических интерфейсов GDI.  
  
- Геометрия области рисования.  
  
- Процедура высвобождения графических ресурсов.  
  
## <a name="drawing-functionality-provided-by-control"></a>Функциональные возможности рисования, предоставляемые элементом управления  
 Базовый класс <xref:System.Windows.Forms.Control> предоставляет функциональные возможности рисования через его <xref:System.Windows.Forms.Control.Paint> событие. Элемент управления вызывает событие <xref:System.Windows.Forms.Control.Paint> каждый раз, когда ему требуется обновить его отображение. Дополнительные сведения о событиях в .NET Framework см. в разделе [обработка и вызов событий](../../../standard/events/index.md).  
  
 Класс данных событий для <xref:System.Windows.Forms.Control.Paint> события, <xref:System.Windows.Forms.PaintEventArgs>содержит данные, необходимые для рисования элемента управления — маркер графического объекта и прямоугольника, представляющий регион для рисования. Эти объекты показаны жирным шрифтом в следующем фрагменте кода.  
  
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
  
 <xref:System.Drawing.Graphics>— Это управляемый класс, который инкапсулирует функциональные возможности рисования, как описано в разделе о GDI далее в этой статье. Является экземпляром <xref:System.Drawing.Rectangle> структуры и определяет доступную область, в которой может нарисоваться элемент управления. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Разработчик элемента управления может вычислить <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> значение <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> с помощью свойства элемента управления, как описано в обсуждении геометрии далее в этом разделе.  
  
 Элемент управления должен предоставлять логику отрисовки путем переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> метода, от <xref:System.Windows.Forms.Control>которого он наследуется. <xref:System.Windows.Forms.Control.OnPaint%2A>Получает доступ к графическому объекту и прямоугольнику для рисования с помощью <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> и свойств экземпляра, <xref:System.Windows.Forms.PaintEventArgs> переданного в него.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Метод базового <xref:System.Windows.Forms.Control> класса не реализует какие бы то ни было функции рисования <xref:System.Windows.Forms.Control.Paint> , но вызывает делегаты событий, зарегистрированные в событии. <xref:System.Windows.Forms.Control.OnPaint%2A> При переопределении <xref:System.Windows.Forms.Control.OnPaint%2A>следует, как правило, <xref:System.Windows.Forms.Control.OnPaint%2A> вызывать метод базового класса <xref:System.Windows.Forms.Control.Paint> , чтобы зарегистрированные делегаты получили событие. Однако элементы управления, которые закрашены всю поверхность, не должны вызывать базовый <xref:System.Windows.Forms.Control.OnPaint%2A>класс, так как это приводит к мерцанию. Пример переопределения <xref:System.Windows.Forms.Control.OnPaint%2A> события см. в [разделе как Создайте элемент управления Windows Forms, отображающий](how-to-create-a-windows-forms-control-that-shows-progress.md)ход выполнения.  
  
> [!NOTE]
> Не вызывайте <xref:System.Windows.Forms.Control.OnPaint%2A> непосредственно из элемента управления; вместо этого <xref:System.Windows.Forms.Control.Invalidate%2A> вызовите метод (наследуется от <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Control.Invalidate%2A>) или другой метод, который вызывает. Метод <xref:System.Windows.Forms.Control.Invalidate%2A> , в свою очередь, <xref:System.Windows.Forms.Control.OnPaint%2A>вызывает. Метод перегружен, и, в зависимости от аргументов <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, перерисовок, элемент управления перерисовывает часть его экранной области. <xref:System.Windows.Forms.Control.Invalidate%2A>  
  
 Базовый <xref:System.Windows.Forms.Control> класс определяет другой метод, который удобен для рисования <xref:System.Windows.Forms.Control.OnPaintBackground%2A> — метод.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>Закрашивает фон (и, таким образом, форму) окна и гарантированно ускоряется, при <xref:System.Windows.Forms.Control.OnPaint%2A> этом данные записываются быстрее, поскольку отдельные запросы на рисование объединяются в одно <xref:System.Windows.Forms.Control.Paint> событие, охватывающее все области, которые должны быть перерисовке. Например, вы можете вызвать метод <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, если нужно нарисовать градиентный цвет фона для элемента управления.  
  
 Хотя <xref:System.Windows.Forms.Control.OnPaintBackground%2A> имеет элемент, подобный событиям, и принимает тот же аргумент `OnPaint` , что <xref:System.Windows.Forms.Control.OnPaintBackground%2A> и метод, не является истинным методом события. `PaintBackground` События и<xref:System.Windows.Forms.Control.OnPaintBackground%2A> не вызывают делегаты событий. При переопределении <xref:System.Windows.Forms.Control.OnPaintBackground%2A> метода производный класс не требуется для <xref:System.Windows.Forms.Control.OnPaintBackground%2A> вызова метода своего базового класса.  
  
## <a name="gdi-basics"></a>Основы GDI+  
 <xref:System.Drawing.Graphics> Класс предоставляет методы для рисования различных фигур, таких как круги, треугольники, дуги и эллипсы, а также методы для отображения текста. <xref:System.Drawing?displayProperty=nameWithType> Пространство имен и его подпространства имен содержат классы, инкапсулирующие графические элементы, такие как фигуры (круги, прямоугольники, дуги и др.), цвета, шрифты, кисти и т. д. Дополнительные сведения о GDI см. [в разделе Использование управляемых графических классов](../advanced/using-managed-graphics-classes.md). Основные [сведения о GDI также описаны в разделе как: Создайте элемент управления Windows Forms, отображающий](how-to-create-a-windows-forms-control-that-shows-progress.md)ход выполнения.  
  
## <a name="geometry-of-the-drawing-region"></a>Геометрия области рисования  
 Свойство элемента управления указывает прямоугольную область, доступную для элемента управления на экране пользователя, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> а свойство объекта <xref:System.Windows.Forms.PaintEventArgs> — область, которая на самом деле окрашена. <xref:System.Windows.Forms.Control.ClientRectangle%2A> (Помните, что рисование выполняется в <xref:System.Windows.Forms.Control.Paint> методе события, который <xref:System.Windows.Forms.PaintEventArgs> принимает экземпляр в качестве аргумента). Элементу управления может потребоваться закрасить только часть его доступной области, как в случае, когда изменяется небольшой раздел экрана элемента управления. В таких ситуациях разработчик элемента управления должен вычислить фактический прямоугольник для рисования и передать <xref:System.Windows.Forms.Control.Invalidate%2A>его в. Перегруженные <xref:System.Windows.Forms.Control.Invalidate%2A> версии, которые <xref:System.Drawing.Region> <xref:System.Drawing.Rectangle> принимают или в качестве аргумента, <xref:System.Windows.Forms.PaintEventArgs>используют этот аргумент для создания <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> свойства.  
  
 В следующем фрагменте кода показано, `FlashTrackBar` как пользовательский элемент управления выполняет вычисление прямоугольной области для рисования. `client` Переменная обозначает свойство. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> Полный пример см. в разделе [как Создайте элемент управления Windows Forms, отображающий](how-to-create-a-windows-forms-control-that-shows-progress.md)ход выполнения.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>Освобождение графических ресурсов  
 Объекты Graphics являются ресурсоемкими, так как они используют системные ресурсы. К <xref:System.Drawing.Graphics?displayProperty=nameWithType> таким объектам относятся экземпляры класса <xref:System.Drawing.Brush?displayProperty=nameWithType>, а также экземпляры, <xref:System.Drawing.Pen?displayProperty=nameWithType>и другие графические классы. Очень важно создать графический ресурс только в том случае, если он вам нужен, и сразу выпустить его, как только вы завершите его использование. При создании типа, реализующего <xref:System.IDisposable> интерфейс, вызовите его <xref:System.IDisposable.Dispose%2A> метод, когда завершите работу с ним, чтобы освободить ресурсы.  
  
 В следующем фрагменте кода показано, `FlashTrackBar` как пользовательский элемент управления создает и <xref:System.Drawing.Brush> освобождает ресурс. Полный исходный код см. в разделе [как Создайте элемент управления Windows Forms, отображающий](how-to-create-a-windows-forms-control-that-shows-progress.md)ход выполнения.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание элемента управления Windows Forms, отображающего ход выполнения](how-to-create-a-windows-forms-control-that-shows-progress.md)
