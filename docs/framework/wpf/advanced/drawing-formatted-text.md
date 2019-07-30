---
title: Рисование форматированного текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: 3b410bcf609aca2cb201042247b8768f243ac93a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629745"
---
# <a name="drawing-formatted-text"></a>Рисование форматированного текста
В этом разделе приводятся общие сведения о возможностях <xref:System.Windows.Media.FormattedText> объекта. Этот объект предоставляет низкоуровневый элемент управления для рисования текста в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Общие сведения о технологии  
 <xref:System.Windows.Media.FormattedText> Объект позволяет рисовать многострочный текст, в котором каждый символ в тексте можно форматировать отдельно. В следующем примере показан текст, к которому применено несколько форматов.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
>  Для разработчиков, осуществляющих переход с API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], в таблице из раздела [Миграция Win32](#win32_migration) перечислены флаги DrawText [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и примерный эквивалент в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### <a name="reasons-for-using-formatted-text"></a>Причины использования форматированного текста  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется множество элементов управления для рисования текста на экране. Каждый элемент управления предназначен для своего сценария и имеет собственный список функций и ограничений. Как правило <xref:System.Windows.Controls.TextBlock> , элемент следует использовать, если требуется ограниченная поддержка текста, например краткое предложение [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]в. <xref:System.Windows.Controls.Label>может использоваться, если требуется минимальная поддержка текста. Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
 Объект предоставляет больше возможностей форматирования текста, чем [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] текстовые элементы управления, и может быть полезен в случаях, когда требуется использовать текст в качестве декоративного элемента. <xref:System.Windows.Media.FormattedText> Дополнительные сведения см. в следующем разделе: [Преобразование форматированного текста в геометрический объект](#converting_formatted_text).  
  
 Кроме того <xref:System.Windows.Media.FormattedText> , объект полезен для создания объектов, производных <xref:System.Windows.Media.DrawingVisual>от текста. <xref:System.Windows.Media.DrawingVisual>— Это упрощенный класс рисования, используемый для отрисовки фигур, изображений или текста. Дополнительные сведения см. в разделе [Пример проверки нажатия с использованием DrawingVisuals](https://go.microsoft.com/fwlink/?LinkID=159994).  
  
## <a name="using-the-formattedtext-object"></a>Использование объекта FormattedText  
 Чтобы создать форматированный текст, вызовите <xref:System.Windows.Media.FormattedText.%23ctor%2A> конструктор, чтобы <xref:System.Windows.Media.FormattedText> создать объект. После создания исходной строки форматированного текста можно применить ряд стилей форматирования.  
  
 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> Используйте свойство, чтобы ограничить текст определенной шириной. Текст будет автоматически перенесен, чтобы заданная ширина не была нарушена. <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> Используйте свойство, чтобы ограничить текст определенной высотой. Если текст выходит за указанные пределы по высоте, отображается многоточие (…).  
  
 ![Текст, отображаемый с помощью WordWrap и многоточия.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать <xref:System.Windows.Media.FormattedText.SetFontSize%2A> методы и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> , чтобы изменить форматирование первых пяти символов в тексте.  
  
 В следующем примере кода создается <xref:System.Windows.Media.FormattedText> объект, а затем к тексту применяется несколько стилей форматирования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Единица измерения "Размер шрифта"  
 Как и в <xref:System.Windows.Media.FormattedText> случае с другими [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] текстовыми объектами в приложениях, объект использует аппаратно-независимые пиксели в качестве единицы измерения. Однако большинство приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] используют в качестве единицы измерения точки. Если вы хотите использовать отображаемый текст в единицах точек в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях, необходимо преобразовать независимые от устройства единицы (1/1/96 дюйма на единицу) в пункты. В следующем примере кода показано выполнение этого преобразования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Преобразование форматированного текста в геометрический объект  
 Форматированный текст можно преобразовать в <xref:System.Windows.Media.Geometry> объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура текстовой строки.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с кистью изображения, примененной к обводке и выделению](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Когда текст преобразуется в <xref:System.Windows.Media.Geometry> объект, он больше не является набором символов — нельзя изменить символы в текстовой строке. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста. Дополнительные сведения см. в разделе [Создание контурного текста](how-to-create-outlined-text.md).  
  
 Можно также преобразовать форматированный текст в <xref:System.Windows.Media.PathGeometry> объект и использовать объект для выделения текста. Например, можно применить анимацию к <xref:System.Windows.Media.PathGeometry> объекту, чтобы анимация обменялась по контуру форматированного текста.  
  
 В следующем примере показан форматированный текст, преобразованный в <xref:System.Windows.Media.PathGeometry> объект. Анимированное многоточие повторяет путь штрихов отрисованного текста.  
  
 ![Сфера, следующая по геометрическому пути текста](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Сфера, следующая по геометрическому пути текста  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Можно создать другие интересные применения для форматированного текста после его преобразования в <xref:System.Windows.Media.PathGeometry> объект. Например, можно обрезать видео для отображения внутри текста.  
  
 ![Отображение видео по геометрическому пути текста](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Миграция Win32  
 Функции <xref:System.Windows.Media.FormattedText> для рисования текста похожи на [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] функции функции DrawText. Для разработчиков, осуществляющих переход с API [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], в таблице перечислены флаги DrawText [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] и примерный эквивалент в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Флаг DrawText|Эквивалент WPF|Примечания|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство, чтобы вычислить [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] соответствующую DrawText координату y. <xref:System.Windows.Media.FormattedText.Height%2A>|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Используйте свойства <xref:System.Windows.Media.FormattedText.Width%2A> и для вычисления прямоугольника вывода. <xref:System.Windows.Media.FormattedText.Height%2A>|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство со значением <xref:System.Windows.TextAlignment.Center>. <xref:System.Windows.Media.FormattedText.TextAlignment%2A>|  
|DT_EDITCONTROL|None|Не требуется. Ширина пробелов и отрисовка последней строки соответствуют этим параметрам в элементе управления редактированием среды.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство со значением <xref:System.Windows.TextTrimming.CharacterEllipsis>. <xref:System.Windows.Media.FormattedText.Trimming%2A><br /><br /> Используйте <xref:System.Windows.TextTrimming.WordEllipsis> для получения [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DT_END_ELLIPSIS с DT_WORD_ELIPSIS End многоточие — в данном случае символ многоточие выполняется только для слов, которые не умещаются в одной строке.|  
|DT_EXPAND_TABS|None|Не требуется. Символы табуляции автоматически расширяются до точек каждые 4 размера максимального пробела (это примерно соответствует ширине 8 независимых от языка символов).|  
|DT_EXTERNALLEADING|None|Не требуется. Внешнее ведение всегда включается в междустрочный интервал. <xref:System.Windows.Media.FormattedText.LineHeight%2A> Используйте свойство для создания определяемого пользователем межстрочного междустрочного промежутка.|  
|DT_HIDEPREFIX|None|Не поддерживается. Удалите "&" из строки перед созданием <xref:System.Windows.Media.FormattedText> объекта.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Это выравнивание текста по умолчанию. Используйте свойство со значением <xref:System.Windows.TextAlignment.Left>. <xref:System.Windows.Media.FormattedText.TextAlignment%2A> (только WPF)|  
|DT_MODIFYSTRING|None|Не поддерживается.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Отсечение не происходит автоматически. Если нужно обрезать текст, используйте <xref:System.Windows.Media.Visual.VisualClip%2A> свойство.|  
|DT_NOFULLWIDTHCHARBREAK|None|Не поддерживается.|  
|DT_NOPREFIX|None|Не требуется. Символ & в строке всегда рассматривается как обычный символ.|  
|DT_PATHELLIPSIS|None|Используйте свойство со значением <xref:System.Windows.TextTrimming.WordEllipsis>. <xref:System.Windows.Media.FormattedText.Trimming%2A>|  
|DT_PREFIX|None|Не поддерживается. Если вы хотите использовать подчеркивания для текста, например сочетания клавиш или ссылку, используйте <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> метод.|  
|DT_PREFIXONLY|None|Не поддерживается.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство со значением <xref:System.Windows.TextAlignment.Right>. <xref:System.Windows.Media.FormattedText.TextAlignment%2A> (только WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Задайте для свойства <xref:System.Windows.Media.FormattedText.FlowDirection%2A> значение <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|None|Не требуется. <xref:System.Windows.Media.FormattedText>объекты ведут себя как один элемент управления Line, если только <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> свойство не задано или текст содержит символ возврата каретки или перевода строки (CR/LF).|  
|DT_TABSTOP|None|Отсутствует поддержка пользовательских позиций табуляции.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Не требуется. По умолчанию используется выравнивание по верхнему краю. Другие значения вертикального позиционирования можно определить с помощью <xref:System.Windows.Media.FormattedText.Height%2A> свойства, чтобы вычислить соответствующую [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] позицию DrawText "y".|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство, чтобы вычислить [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] соответствующую DrawText координату y. <xref:System.Windows.Media.FormattedText.Height%2A>|  
|DT_WORDBREAK|None|Не требуется. Разбиение по словам происходит <xref:System.Windows.Media.FormattedText> автоматически с объектами. Его нельзя отключить.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство со значением <xref:System.Windows.TextTrimming.WordEllipsis>. <xref:System.Windows.Media.FormattedText.Trimming%2A>|  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.FormattedText>
- [Документы в WPF](documents-in-wpf.md)
- [Оформление в WPF](typography-in-wpf.md)
- [Создание контурного текста](how-to-create-outlined-text.md)
- [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
