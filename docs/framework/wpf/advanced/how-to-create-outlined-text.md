---
title: Как выполнить Создание контурного текста
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
ms.openlocfilehash: a06ef9adbd5740fee74be2e9d8d13a8a5bdc5b95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521482"
---
# <a name="how-to-create-outlined-text"></a>Как выполнить Создание контурного текста
В большинстве случаев при добавлении декоративных элементов в текстовые строки в вашей [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложения, вы используете текст в виде коллекции дискретных символов или глифов. Например, можно создать кисть линейного градиента и применить его к <xref:System.Windows.Controls.Control.Foreground%2A> свойство <xref:System.Windows.Controls.TextBox> объекта. При отображении или измените текстовое поле, кисти линейного градиента применяется автоматически в текущий набор символов в текстовой строке.  
  
 ![Текст, отображаемый кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext01.jpg "OutlinedText01")  
Пример применения к текстовому полю кисти линейного градиента  
  
 Тем не менее, можно также преобразовать текст в <xref:System.Windows.Media.Geometry> объектами, позволяет создавать другие типы визуально форматированного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект, основанный на контуре строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Пример кисти линейного градиента, применяемое к геометрии структуры текста  
  
 Если текст преобразуется в <xref:System.Windows.Media.Geometry> объекта, он больше не является набором символов — изменение символов в текстовой строке невозможно. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста.  
  
 Следующие примеры иллюстрируют несколько способов создания визуальных эффектов посредством изменения штриха и заливки преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Пример установки разного цвета для штриха и заливки  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Пример применения кисти к штриху  
  
 Можно также изменить ограничивающий прямоугольник или выделения преобразованного текста. Следующий пример иллюстрирует способ создания визуальных эффектов посредством изменения штриха и выделения преобразованного текста.  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Пример применения кисти к штриху и выделению  
  
## <a name="example"></a>Пример  
 Ключ, чтобы преобразовать текст в <xref:System.Windows.Media.Geometry> объекта заключается в использовании <xref:System.Windows.Media.FormattedText> объекта. После создания этот объект можно использовать <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> и <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> методы, чтобы преобразовать текст в <xref:System.Windows.Media.Geometry> объектов. Первый метод возвращает геометрию форматированного текста. Второй метод возвращает ограничивающий прямоугольник геометрии форматированного текста. В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> объекта и извлечение геометрических форм форматированного текста и его ограничивающего прямоугольника.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Чтобы отобразить извлеченные <xref:System.Windows.Media.Geometry> объектов, необходимо получить доступ к <xref:System.Windows.Media.DrawingContext> объекта, который отображает преобразованный текст. В этих примерах кода это делается путем создания объекта пользовательского элемента управления, производный от класса, поддерживающего пользовательской отрисовки.  
  
 Для отображения <xref:System.Windows.Media.Geometry> объектов в пользовательском элементе управления, переопределите для <xref:System.Windows.UIElement.OnRender%2A> метод. Переопределенный метод должен использовать <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> метод для отображения <xref:System.Windows.Media.Geometry> объектов.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Источник объекта пример настраиваемого пользовательского элемента управления, см. в разделе [OutlineTextControl.cs для C# ](https://github.com/dotnet/samples/blob/master/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) и [OutlineTextControl.vb для Visual Basic](https://github.com/dotnet/samples/blob/master/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb). 
  
## <a name="see-also"></a>См. также
- [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
