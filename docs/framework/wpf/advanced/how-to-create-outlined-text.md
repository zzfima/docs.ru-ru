---
title: Практическое руководство. Вывод текста по контуру
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: d0ce46b9895589fd4635b567136204368a6431ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186857"
---
# <a name="how-to-create-outlined-text"></a>Практическое руководство. Вывод текста по контуру
В большинстве случаев, когда вы добавляете [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] орнамент в текстовые строки в приложении, вы используете текст с точки зрения коллекции дискретных символов, или глифов. Например, можно создать линейную градиентную <xref:System.Windows.Controls.Control.Foreground%2A> кисть <xref:System.Windows.Controls.TextBox> и применить ее к свойству объекта. При отображении или редактировании текстового окна линейная кисти градиента автоматически наносится на текущий набор символов в текстовой строке.  
  
 ![Текст, отображенный при помощи кисти линейного градиента](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 Тем не менее, вы <xref:System.Windows.Media.Geometry> также можете преобразовать текст в объекты, что позволяет создавать другие типы визуально богатого текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Когда текст преобразуется <xref:System.Windows.Media.Geometry> в объект, он больше не представляет собой набор символов, вы не можете изменить символы в строке текста. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста.  
  
 Следующие примеры иллюстрируют несколько способов создания визуальных эффектов путем изменения штриха и заполнения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 Также можно изменить прямоугольник ящика или выделить преобразованный текст. Следующий пример иллюстрирует способ создания визуальных эффектов путем изменения штриха и выделения преобразованного текста.  
  
 ![Текст с изображением кисти, нанесенной на штрих и выделение](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Пример  
 Ключом к преобразованию <xref:System.Windows.Media.Geometry> текста в <xref:System.Windows.Media.FormattedText> объект является использование объекта. После создания этого объекта можно использовать <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> методы для преобразования <xref:System.Windows.Media.Geometry> текста в объекты. Первый метод возвращает геометрию отформатированный текст; второй метод возвращает геометрию ограниченного окна отформатированный текст. Следующий пример кода показывает, <xref:System.Windows.Media.FormattedText> как создать объект и получить геометрию отформатированного текста и его ограничивающего окна.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Для отображения <xref:System.Windows.Media.Geometry> извлеченных объектов необходимо <xref:System.Windows.Media.DrawingContext> получить доступ к объекту, отображаемому преобразованный текст. В этих примерах кода это делается путем создания пользовательского объекта управления, который происходит от класса, который поддерживает пользовательский рендеринг.  
  
 Для <xref:System.Windows.Media.Geometry> отображения объектов в пользовательском элементе управления предоставьте переопределение для метода. <xref:System.Windows.UIElement.OnRender%2A> Ваш перекрывшийся <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> метод должен <xref:System.Windows.Media.Geometry> использовать метод для рисования объектов.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Для источника пользовательского объекта пользовательского управления можно найти [OutlineTextControl.cs для C-и](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) [OutlineTextControl.vb для Visual Basic.](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)
  
## <a name="see-also"></a>См. также раздел

- [Рисование форматированного текста](drawing-formatted-text.md)
