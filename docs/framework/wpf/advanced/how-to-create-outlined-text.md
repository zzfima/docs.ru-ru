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
ms.openlocfilehash: c79f5c1c6812b1175119133664e39995af29bd4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-outlined-text"></a>Практическое руководство. Вывод текста по контуру
В большинстве случаев при добавлении декоративных элементов в текстовые строки в вашей [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложение, вы используете текст в виде коллекции дискретных символов или глифов. Например, можно создать кисти линейного градиента и применить его к <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.TextBox> объекта. При отображении или измените текстовое поле кисти линейного градиента автоматически применяется текущий набор символов в текстовой строке.  
  
 ![Текст, отображаемый кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Пример кисти линейного градиента, применяются к текстовому полю  
  
 Тем не менее, можно преобразовать текст в <xref:System.Windows.Media.Geometry> объекты, что позволяет создавать другие типы визуально форматированного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объекта, основанного на структуре текстовой строки.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Пример кисти линейного градиента, применяемой к геометрии структуры текста  
  
 Если текст преобразуется в <xref:System.Windows.Media.Geometry> объекта, он больше не является набором символов — изменение символов в текстовой строке невозможно. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста.  
  
 Следующие примеры иллюстрируют несколько способов создания визуальных эффектов путем изменения обводки и заливку преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Пример установки разного цвета для штриха и заливки  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Пример применения кисти к штриху  
  
 Можно также изменить ограничивающего прямоугольника поля или выделить преобразованный текст. Следующий пример демонстрирует способ создания визуальных эффектов путем изменения обводки и выделения преобразованного текста.  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Пример применения кисти к штриху и выделению  
  
## <a name="example"></a>Пример  
 Ключ, чтобы преобразовать текст в <xref:System.Windows.Media.Geometry> необходимо использовать <xref:System.Windows.Media.FormattedText> объекта. После создания этот объект можно использовать <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> и <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> методов, чтобы преобразовать текст в <xref:System.Windows.Media.Geometry> объектов. Первый метод возвращает геометрии форматированного текста. Второй метод возвращает геометрию форматированный текст ограничивающего прямоугольника. В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> объекта и извлечение геометрических форм форматированного текста и его ограничивающего прямоугольника.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Чтобы отобразить извлеченные <xref:System.Windows.Media.Geometry> объектов, необходимо получить доступ к <xref:System.Windows.Media.DrawingContext> объекта, который отображает преобразованный текст. В этих примерах кода этого путем создания объекта пользовательского элемента управления, производный от класса, поддерживающего определенную пользователем отрисовку.  
  
 Для отображения <xref:System.Windows.Media.Geometry> объектов в пользовательский элемент управления, выполните переопределение для <xref:System.Windows.UIElement.OnRender%2A> метод. Переопределенный метод должен использовать <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> метод для отображения <xref:System.Windows.Media.Geometry> объектов.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
## <a name="see-also"></a>См. также  
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
