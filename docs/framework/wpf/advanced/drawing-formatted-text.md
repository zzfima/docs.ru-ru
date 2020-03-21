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
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186566"
---
# <a name="drawing-formatted-text"></a>Рисование форматированного текста
Эта тема содержит обзор особенностей <xref:System.Windows.Media.FormattedText> объекта. Этот объект предоставляет низкоуровневый элемент управления для рисования текста в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

## <a name="technology-overview"></a>Общие сведения о технологии  
 Объект <xref:System.Windows.Media.FormattedText> позволяет рисовать многолинейный текст, в котором каждый символ в тексте может быть индивидуально отформатирован. В следующем примере показан текст, к которому применено несколько форматов.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Для разработчиков, мигрирующих из API Win32, в таблице раздела [Win32 Migration](#win32_migration) перечислены [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]флаги Win32 DrawText и приблизительный эквивалент в разделе .  
  
### <a name="reasons-for-using-formatted-text"></a>Причины использования форматированного текста  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет множество элементов управления для отображения текста на экране. Каждый элемент управления предназначен для своего сценария и имеет собственный список функций и ограничений. Как правило, <xref:System.Windows.Controls.TextBlock> элемент должен использоваться при ограниченной поддержке текста, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]например, краткое предложение в . <xref:System.Windows.Controls.Label>может быть использован, когда требуется минимальная поддержка текста. Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
 Объект <xref:System.Windows.Media.FormattedText> предоставляет больше функций [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] форматирования текста, чем текстовые элементы управления, и может быть полезен в тех случаях, когда вы хотите использовать текст в качестве декоративного элемента. Дополнительные сведения см. в следующем разделе: [Преобразование форматированного текста в геометрический объект](#converting_formatted_text).  
  
 Кроме того, <xref:System.Windows.Media.FormattedText> объект полезен для <xref:System.Windows.Media.DrawingVisual>создания объектов, ориентированных на текст. <xref:System.Windows.Media.DrawingVisual>— это легкий класс рисования, который используется для визуализации форм, изображений или текста. Дополнительные сведения см. в разделе [Пример проверки нажатия с использованием DrawingVisuals](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).  
  
## <a name="using-the-formattedtext-object"></a>Использование объекта FormattedText  
 Чтобы создать отформатированный <xref:System.Windows.Media.FormattedText.%23ctor%2A> текст, позвоните в конструктор для создания <xref:System.Windows.Media.FormattedText> объекта. После создания исходной строки форматированного текста можно применить ряд стилей форматирования.  
  
 Используйте <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> свойство, чтобы ограничить текст определенной шириной. Текст будет автоматически перенесен, чтобы заданная ширина не была нарушена. Используйте <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> свойство, чтобы ограничить текст определенной высотой. Если текст выходит за указанные пределы по высоте, отображается многоточие (…).  
  
 ![Текст отображается с wordwrap и эллипсис.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 К одному или более символам можно применить несколько стилей форматирования. Например, можно вызвать <xref:System.Windows.Media.FormattedText.SetFontSize%2A> <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> как методы, так и методы для изменения форматирования первых пяти символов в тексте.  
  
 Следующий пример кода <xref:System.Windows.Media.FormattedText> создает объект, а затем применяет несколько стилей форматирования к тексту.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>Единица измерения "Размер шрифта"  
 Как и в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] случае с <xref:System.Windows.Media.FormattedText> другими текстовыми объектами в приложениях, объект использует независимые от устройства пиксели в качестве единицы измерения. Тем не менее, большинство приложений Win32 используют баллы в качестве единицы измерения. Если вы хотите использовать отображательный текст в единицах точек в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложениях, вам нужно преобразовать устройства независимых единиц (1/96-й дюйм на единицу) в точки. В следующем примере кода показано выполнение этого преобразования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>Преобразование форматированного текста в геометрический объект  
 Вы можете конвертировать <xref:System.Windows.Media.Geometry> отформатированный текст в объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с изображением кисти, нанесенной на штрих и выделение](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Когда текст преобразуется <xref:System.Windows.Media.Geometry> в объект, он больше не представляет собой набор символов, вы не можете изменить символы в строке текста. Тем не менее можно повлиять на внешний вид преобразованного текст, изменив его свойства штриха и заливки. Штрих — это контур преобразованного текста; заливка — это область внутри контура преобразованного текста. Дополнительные сведения см. в разделе [Создание контурного текста](how-to-create-outlined-text.md).  
  
 Вы также можете преобразовать <xref:System.Windows.Media.PathGeometry> отформатированный текст в объект и использовать объект для выделения текста. Например, можно применить анимацию <xref:System.Windows.Media.PathGeometry> к объекту так, чтобы анимация отсеяла контур отформатированный текст.  
  
 В следующем примере показан отформатированный <xref:System.Windows.Media.PathGeometry> текст, преобразованный в объект. Анимированное многоточие повторяет путь штрихов отрисованного текста.  
  
 ![Сфера, следующая по геометрическому пути текста](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
Сфера, следующая по геометрическому пути текста  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100)).  
  
 Вы можете создать другие интересные использования для отформатированный текст, как только он был преобразован в <xref:System.Windows.Media.PathGeometry> объект. Например, можно обрезать видео для отображения внутри текста.  
  
 ![Отображение видео по геометрическому пути текста](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Миграция Win32  
 Особенности <xref:System.Windows.Media.FormattedText> для рисования текста аналогичны функциям функции Win32 DrawText. Для разработчиков, мигрирующих из API Win32, в следующей таблице перечислены [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]флаги Win32 DrawText и приблизительный эквивалент в .  
  
|Флаг DrawText|Эквивалент WPF|Примечания|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте <xref:System.Windows.Media.FormattedText.Height%2A> свойство для вычисления соответствующей позиции Win32 DrawText 'y'.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Используйте <xref:System.Windows.Media.FormattedText.Height%2A> <xref:System.Windows.Media.FormattedText.Width%2A> и свойства для расчета выходного прямоугольника.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте <xref:System.Windows.Media.FormattedText.TextAlignment%2A> свойство с <xref:System.Windows.TextAlignment.Center>набором значений.|  
|DT_EDITCONTROL|None|Необязательно. Ширина пробелов и отрисовка последней строки соответствуют этим параметрам в элементе управления редактированием среды.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте <xref:System.Windows.Media.FormattedText.Trimming%2A> свойство <xref:System.Windows.TextTrimming.CharacterEllipsis>со значением.<br /><br /> Используйте, <xref:System.Windows.TextTrimming.WordEllipsis> чтобы получить Win32 DT_END_ELLIPSIS с DT_WORD_ELIPSIS конце эллипсис-в этом случае, характер эллипсис происходит только на словах, которые не подходят на одной строке.|  
|DT_EXPAND_TABS|None|Необязательно. Символы табуляции автоматически расширяются до точек каждые 4 размера максимального пробела (это примерно соответствует ширине 8 независимых от языка символов).|  
|DT_EXTERNALLEADING|None|Необязательно. Внешнее ведение всегда включается в междустрочный интервал. Используйте <xref:System.Windows.Media.FormattedText.LineHeight%2A> свойство для создания интервала между пользовательскими линиями.|  
|DT_HIDEPREFIX|None|Не поддерживается. Перед построением <xref:System.Windows.Media.FormattedText> объекта удалите "&" со строки.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Это выравнивание текста по умолчанию. Используйте <xref:System.Windows.Media.FormattedText.TextAlignment%2A> свойство с <xref:System.Windows.TextAlignment.Left>набором значений. (только WPF)|  
|DT_MODIFYSTRING|None|Не поддерживается.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Отсечение не происходит автоматически. Если вы хотите обрезать <xref:System.Windows.Media.Visual.VisualClip%2A> текст, используйте свойство.|  
|DT_NOFULLWIDTHCHARBREAK|None|Не поддерживается.|  
|DT_NOPREFIX|None|Необязательно. Символ & в строке всегда рассматривается как обычный символ.|  
|DT_PATHELLIPSIS|None|Используйте <xref:System.Windows.Media.FormattedText.Trimming%2A> свойство <xref:System.Windows.TextTrimming.WordEllipsis>со значением.|  
|DT_PREFIX|None|Не поддерживается. Если вы хотите использовать подчеркивания для текста, например ключ или ссылку на ускоритель, используйте <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> метод.|  
|DT_PREFIXONLY|None|Не поддерживается.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте <xref:System.Windows.Media.FormattedText.TextAlignment%2A> свойство с <xref:System.Windows.TextAlignment.Right>набором значений. (только WPF)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Установите свойство <xref:System.Windows.Media.FormattedText.FlowDirection%2A> в значение <xref:System.Windows.FlowDirection.RightToLeft>.|  
|DT_SINGLELINE|None|Необязательно. <xref:System.Windows.Media.FormattedText>объекты ведут себя как единый <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> элемент управления строкой, если только свойство не установлено или текст содержит корм возврата/линии перевозки (CR/LF).|  
|DT_TABSTOP|None|Отсутствует поддержка пользовательских позиций табуляции.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Необязательно. По умолчанию используется выравнивание по верхнему краю. Другие значения вертикального позиционирования <xref:System.Windows.Media.FormattedText.Height%2A> можно определить с помощью свойства для вычисления соответствующего положения Win32 DrawText 'y'.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте <xref:System.Windows.Media.FormattedText.Height%2A> свойство для вычисления соответствующей позиции Win32 DrawText 'y'.|  
|DT_WORDBREAK|None|Необязательно. Нарушение слова происходит <xref:System.Windows.Media.FormattedText> автоматически с объектами. Его нельзя отключить.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте <xref:System.Windows.Media.FormattedText.Trimming%2A> свойство <xref:System.Windows.TextTrimming.WordEllipsis>со значением.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.FormattedText>
- [Документы в WPF](documents-in-wpf.md)
- [Оформление в WPF](typography-in-wpf.md)
- [Создание контурного текста](how-to-create-outlined-text.md)
- [Практическое руководство. Создание анимации PathGeometry для текста](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
