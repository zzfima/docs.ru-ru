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
ms.openlocfilehash: f23f54283849ddaa827a98f0f28a39a72305dc1d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095233"
---
# <a name="drawing-formatted-text"></a>Рисование форматированного текста
В этом разделе содержатся общие сведения о функциях объекта <xref:System.Windows.Media.FormattedText>. Этот объект предоставляет низкоуровневый элемент управления для рисования текста в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Общие сведения о технологии  
 Объект <xref:System.Windows.Media.FormattedText> позволяет рисовать многострочный текст, в котором каждый символ в тексте можно форматировать отдельно. В следующем примере показан текст, к которому применено несколько форматов.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Для разработчиков, выполняющих миграцию из API Win32, в таблице в разделе [миграции Win32](#win32_migration) перечислены флаги Win32 DrawText и приблизительный эквивалент в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### <a name="reasons-for-using-formatted-text"></a>Причины использования форматированного текста  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеется множество элементов управления для рисования текста на экране. Каждый элемент управления предназначен для различных сценариев и имеет свой собственный список функций и ограничений. Как правило, элемент <xref:System.Windows.Controls.TextBlock> следует использовать, если требуется ограниченная поддержка текста, например краткое предложение в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> можно использовать, если требуется минимальная поддержка текста. Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
 Объект <xref:System.Windows.Media.FormattedText> предоставляет больше возможностей форматирования текста, чем [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] текстовых элементов, и может быть полезен в случаях, когда требуется использовать текст в качестве декоративного элемента. Дополнительные сведения см. в следующем разделе: [Преобразование форматированного текста в геометрический объект](#converting_formatted_text).  
  
 Кроме того, объект <xref:System.Windows.Media.FormattedText> полезен для создания объектов, ориентированных на текст <xref:System.Windows.Media.DrawingVisual>. <xref:System.Windows.Media.DrawingVisual> — это упрощенный класс рисования, используемый для отрисовки фигур, изображений или текста. Дополнительные сведения см. в разделе [Пример проверки нажатия с использованием DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
## <a name="using-the-formattedtext-object"></a>Использование объекта FormattedText  
 Чтобы создать форматированный текст, вызовите конструктор <xref:System.Windows.Media.FormattedText.%23ctor%2A>, чтобы создать <xref:System.Windows.Media.FormattedText> объект. После создания исходной строки форматированного текста можно применить ряд стилей форматирования.  
  
 Используйте свойство <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>, чтобы ограничить текст заданной шириной. Текст будет автоматически перенесен, чтобы заданная ширина не была нарушена. Используйте свойство <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>, чтобы ограничить текст определенной высотой. Если текст выходит за указанные пределы по высоте, отображается многоточие (…).  
  
 ![Текст, отображаемый с помощью WordWrap и многоточия.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать методы <xref:System.Windows.Media.FormattedText.SetFontSize%2A> и <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>, чтобы изменить форматирование первых пяти символов в тексте.  
  
 В следующем примере кода создается объект <xref:System.Windows.Media.FormattedText>, а затем к тексту применяется несколько стилей форматирования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Единица измерения "Размер шрифта"  
 Как и в случае с другими текстовыми объектами в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях, объект <xref:System.Windows.Media.FormattedText> использует аппаратно-независимые пиксели в качестве единицы измерения. Однако большинство приложений Win32 используют в качестве единицы измерения точки. Если вы хотите использовать отображаемый текст в единицах точек в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях, необходимо преобразовать независимые от устройства единицы (1/1/96 дюйма на единицу) в пункты. В следующем примере кода показано выполнение этого преобразования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>Преобразование форматированного текста в геометрический объект  
 Форматированный текст можно преобразовать в <xref:System.Windows.Media.Geometry>ные объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать объект <xref:System.Windows.Media.Geometry>, основанный на контуре текстовой строки.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с кистью изображения, примененной к обводке и выделению](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Когда текст преобразуется в <xref:System.Windows.Media.Geometry> объект, он больше не является набором символов — нельзя изменить символы в текстовой строке. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста. Дополнительные сведения см. в разделе [Создание контурного текста](how-to-create-outlined-text.md).  
  
 Можно также преобразовать форматированный текст в объект <xref:System.Windows.Media.PathGeometry> и использовать объект для выделения текста. Например, можно применить анимацию к объекту <xref:System.Windows.Media.PathGeometry>, чтобы анимация обменялась по контуру форматированного текста.  
  
 В следующем примере показан форматированный текст, преобразованный в объект <xref:System.Windows.Media.PathGeometry>. Анимированное многоточие повторяет путь штрихов отрисованного текста.  
  
 ![Сфера, следующая по геометрическому пути текста](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Сфера, следующая по геометрическому пути текста  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Можно создать другие интересные варианты использования форматированного текста после его преобразования в объект <xref:System.Windows.Media.PathGeometry>. Например, можно обрезать видео для отображения внутри текста.  
  
 ![Отображение видео по геометрическому пути текста](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Миграция Win32  
 Функции <xref:System.Windows.Media.FormattedText> для рисования текста похожи на функции функции Win32 DrawText. Для разработчиков, выполняющих миграцию из API Win32, в следующей таблице перечислены флаги Win32 DrawText и приблизительный эквивалент в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Флаг DrawText|Эквивалент WPF|Примечания|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Height%2A>, чтобы вычислить соответствующую координату "y" для Win32 DrawText.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Для вычисления прямоугольника вывода используйте свойства <xref:System.Windows.Media.FormattedText.Height%2A> и <xref:System.Windows.Media.FormattedText.Width%2A>.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment.Center>.|  
|DT_EDITCONTROL|None|Необязательно. Ширина пробелов и отрисовка последней строки соответствуют этим параметрам в элементе управления редактированием среды.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming.CharacterEllipsis>.<br /><br /> Используйте <xref:System.Windows.TextTrimming.WordEllipsis> для получения DT_END_ELLIPSIS Win32 с DT_WORD_ELIPSIS завершающим многоточием — в данном случае символ многоточие выполняется только для слов, которые не умещаются в одной строке.|  
|DT_EXPAND_TABS|None|Необязательно. Символы табуляции автоматически расширяются до точек каждые 4 размера максимального пробела (это примерно соответствует ширине 8 независимых от языка символов).|  
|DT_EXTERNALLEADING|None|Необязательно. Внешнее ведение всегда включается в междустрочный интервал. Используйте свойство <xref:System.Windows.Media.FormattedText.LineHeight%2A> для создания определяемого пользователем межстрочного междустрочного промежутка.|  
|DT_HIDEPREFIX|None|Не поддерживается. Удалите "&" из строки перед созданием объекта <xref:System.Windows.Media.FormattedText>.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Это выравнивание текста по умолчанию. Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment.Left>. (только WPF)|  
|DT_MODIFYSTRING|None|Не поддерживается.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Отсечение не происходит автоматически. Если нужно обрезать текст, используйте свойство <xref:System.Windows.Media.Visual.VisualClip%2A>.|  
|DT_NOFULLWIDTHCHARBREAK|None|Не поддерживается.|  
|DT_NOPREFIX|None|Необязательно. Символ & в строке всегда рассматривается как обычный символ.|  
|DT_PATHELLIPSIS|None|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming.WordEllipsis>.|  
|DT_PREFIX|None|Не поддерживается. Если вы хотите использовать подчеркивания для текста, например сочетания клавиш или ссылку, используйте метод <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>.|  
|DT_PREFIXONLY|None|Не поддерживается.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment.Right>. (только WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Установите свойство <xref:System.Windows.Media.FormattedText.FlowDirection%2A> в значение <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|None|Необязательно. <xref:System.Windows.Media.FormattedText> объекты ведут себя как один элемент управления Line, если только свойство <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> не задано или текст содержит символ возврата каретки или перевода строки (CR/LF).|  
|DT_TABSTOP|None|Отсутствует поддержка пользовательских позиций табуляции.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Необязательно. По умолчанию используется выравнивание по верхнему краю. Другие значения вертикального позиционирования можно определить с помощью свойства <xref:System.Windows.Media.FormattedText.Height%2A>, чтобы вычислить соответствующую позицию Win32 DrawText "y".|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Height%2A>, чтобы вычислить соответствующую координату "y" для Win32 DrawText.|  
|DT_WORDBREAK|None|Необязательно. Разбиение по словам происходит автоматически с <xref:System.Windows.Media.FormattedText> объектами. Его нельзя отключить.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming.WordEllipsis>.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.FormattedText>
- [Документы в WPF](documents-in-wpf.md)
- [Оформление в WPF](typography-in-wpf.md)
- [Создание контурного текста](how-to-create-outlined-text.md)
- [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
