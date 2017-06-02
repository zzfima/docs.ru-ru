---
title: "Отрисовка элементов управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "пользовательские элементы управления [Windows Forms], графические ресурсы"
  - "пользовательские элементы управления [Windows Forms], аннулирование и рисование"
  - "пользовательские элементы управления [Windows Forms], отрисовка"
  - "OnPaintBackground - метод, вызовы в элементах управления Windows Forms"
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Отрисовка элементов управления Windows Forms
Отрисовка обозначает процесс создания визуального представления на экране пользователя.  Элементы управления Windows Forms используют для отрисовки [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] \(новую графическую библиотеку Windows\).  Управляемые классы, предоставляющие доступ к [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], расположены в пространстве имен <xref:System.Drawing?displayProperty=fullName> и его подпространствах имен.  
  
 В отрисовке элемента управления участвуют следующие элементы.  
  
-   Функциональные возможности рисования, обеспечиваемые базовым классом <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
-   Неотъемлемые элементы графической библиотеки [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
-   Геометрия области рисования.  
  
-   Процедура освобождения графических ресурсов.  
  
## Функциональность рисования, предоставленная элементом управления  
 Базовый класс <xref:System.Windows.Forms.Control> обеспечивает функциональные возможности рисования посредством его события <xref:System.Windows.Forms.Control.Paint>.  Элемент управления инициирует событие <xref:System.Windows.Forms.Control.Paint> в случае необходимости обновления его отображения.  Дополнительные сведения о событиях в .NET Framework см. в разделе [Обработка и создание событий](../../../../docs/standard/events/index.md).  
  
 Класс данных события для события <xref:System.Windows.Forms.Control.Paint>, <xref:System.Windows.Forms.PaintEventArgs>, содержит данные, необходимые для рисования элемента управления — дескриптор графического объекта и прямоугольного объекта, представляющих собой область для рисования.  Эти объекты выделены полужирным шрифтом в следующем фрагменте кода.  
  
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
  
 <xref:System.Drawing.Graphics> является управляемым классом, инкапсулирующим функциональность рисования, как это описано при обсуждении [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] далее в этом разделе.  <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> является экземпляром структуры <xref:System.Drawing.Rectangle>, определяющей доступные области, в которых можно нарисовать элемент управления.  Разработчик элемента управления может вычислить <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>, используя свойство <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> элемента управления, как показано ниже при описании геометрии в этом разделе.  
  
 Элемент управления должен предоставить логику отрисовки с помощью переопределения метода <xref:System.Windows.Forms.Control.OnPaint%2A>, наследующего от <xref:System.Windows.Forms.Control>.  <xref:System.Windows.Forms.Control.OnPaint%2A> получает доступ к графическому объекту и прямоугольнику для рисования с помощью передаваемых ему свойств <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> и <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> экземпляра <xref:System.Windows.Forms.PaintEventArgs>.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 Метод <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса <xref:System.Windows.Forms.Control> не реализует какой\-либо функциональности рисования. Он лишь вызывает делегатов события, зарегистрированных с событием <xref:System.Windows.Forms.Control.Paint>.  При переопределении <xref:System.Windows.Forms.Control.OnPaint%2A> следует, как правило, вызвать метод <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса, чтобы зарегистрированные делегаты получили событие <xref:System.Windows.Forms.Control.Paint>.  Однако элементы управления, вырисовывающие свои поверхности, не должны вызывать <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса, так как это вызовет мерцание изображения.  Пример переопределения события [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md) содержится в разделе <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
> [!NOTE]
>  Не вызывайте <xref:System.Windows.Forms.Control.OnPaint%2A> непосредственно из элемента управления. Вместо этого вызовите метод <xref:System.Windows.Forms.Control.Invalidate%2A> \(наследуемый от <xref:System.Windows.Forms.Control>\) или какой\-либо другой метод, вызывающий <xref:System.Windows.Forms.Control.Invalidate%2A>.  В свою очередь, метод <xref:System.Windows.Forms.Control.Invalidate%2A> запускает <xref:System.Windows.Forms.Control.OnPaint%2A>.  Метод <xref:System.Windows.Forms.Control.Invalidate%2A> перегружается, и, в зависимости от аргументов, примененных для <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, элемент управления частично или полностью перерисует свою поверхность экрана.  
  
 Базовый класс <xref:System.Windows.Forms.Control> определяет другой метод, полезный для рисования: метод <xref:System.Windows.Forms.Control.OnPaintBackground%2A>.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> рисует фон \(а значит, и форму\) окна и гарантированно делает это быстро, в то время как <xref:System.Windows.Forms.Control.OnPaint%2A> рисует детали и может работать медленнее, так как индивидуальные запросы на рисование объединены в одном событии <xref:System.Windows.Forms.Control.Paint>, которое перекрывает все области, которые должны быть перерисованы.  Может возникнуть необходимость вызвать <xref:System.Windows.Forms.Control.OnPaintBackground%2A>, например в случае, если потребуется нарисовать градиентный закрашенный фон для элемента управления.  
  
 Хотя <xref:System.Windows.Forms.Control.OnPaintBackground%2A> имеет систему обозначений, сходную с системой обозначений события, и принимает такие же аргументы, как и метод `OnPaint`, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> не является истинным методом события.  Событие `PaintBackground` не существует, и <xref:System.Windows.Forms.Control.OnPaintBackground%2A> не вызывает делегаты событий.  При переопределении метода <xref:System.Windows.Forms.Control.OnPaintBackground%2A> производный класс не требуется для вызова метода <xref:System.Windows.Forms.Control.OnPaintBackground%2A> его базового класса.  
  
## Основы GDI\+  
 Класс <xref:System.Drawing.Graphics> предоставляет методы для рисования различных форм, таких как круги, треугольники, дуги и эллипсы, а также методы для отображения текста.  Пространство имен <xref:System.Drawing?displayProperty=fullName> и его подпространства содержат классы, инкапсулирующие графические элементы, такие как формы \(круги, прямоугольники, дуги и др.\), цвета, шрифты, кисти и т.д.  Дополнительные сведения о [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] см. в разделе [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).  Основы [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] также приводятся в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
## Геометрия области рисования  
 Свойство <xref:System.Windows.Forms.Control.ClientRectangle%2A> элемента управления задает прямоугольную область, доступную для элемента управления на экране пользователя, в то время как свойство <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs> задает область, которая фактически нарисована.  \(Запомните, что рисование выполняется в методе события <xref:System.Windows.Forms.PaintEventArgs>, получающим экземпляр <xref:System.Windows.Forms.Control.Paint> в качестве аргумента\).  Элемент управления может потребовать перерисовать только часть доступной области, как в случае, когда изменяется небольшая часть его изображения.  В такой ситуации разработчик элемента управления должен рассчитать фактический прямоугольник, в котором будет вестись рисование, и передать его <xref:System.Windows.Forms.Control.Invalidate%2A>.  Перегруженные версии <xref:System.Windows.Forms.Control.Invalidate%2A>, получающие <xref:System.Drawing.Rectangle> или <xref:System.Drawing.Region> в качестве аргумента, используют этот аргумент для создания свойства <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Windows.Forms.PaintEventArgs>.  
  
 Следующий фрагмент кода показывает, как пользовательский элемент управления `FlashTrackBar` рассчитывает прямоугольную область, в которой будет вестись рисование.  Переменная `client` обозначает свойство <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>.  Полный пример содержится в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## Освобождение графических ресурсов  
 Графические объекты расходуют системные ресурсы.  Такие объекты содержат экземпляры класса <xref:System.Drawing.Graphics?displayProperty=fullName>, а также экземпляры <xref:System.Drawing.Brush?displayProperty=fullName>, <xref:System.Drawing.Pen?displayProperty=fullName> и другие графические классы.  Важно, чтобы графический ресурс создавался только тогда, когда он действительно нужен, и освобождался сразу после его использования.  При создании типа, реализующего интерфейс <xref:System.IDisposable>, вызовите его метод <xref:System.IDisposable.Dispose%2A> после окончания работы с ним для освобождения ресурсов.  
  
 Следующий фрагмент кода показывает, как пользовательский элементе управления `FlashTrackBar` создает и освобождает ресурс <xref:System.Drawing.Brush>.  Полный исходный код примера содержится в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## См. также  
 [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)