---
title: "Рисование форматированного текста | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "рисование, форматированный текст"
  - "форматированный текст [WPF]"
  - "текст [WPF]"
  - "оформление, рисование форматированного текста"
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Рисование форматированного текста
В этом разделе представлены общие сведения о функциях объекта <xref:System.Windows.Media.FormattedText>.  Данный объект предоставляет элемент управления нижнего уровня, предназначенные для рисования текста в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="technology_overview"></a>   
## Общие сведения о технологии  
 Объект <xref:System.Windows.Media.FormattedText> предназначен для рисования многострочного текста, в котором каждый символ можно форматировать отдельно.  В следующем примере показан текст, к которому применены несколько форматов.  
  
 ![Отображенный текст с использованием объекта FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
Текст, отображенный с помощью метода FormattedText  
  
> [!NOTE]
>  Для разработчиков, выполняющих задачи по миграции с [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API, в таблице раздела [Миграция Win32](#win32_migration) перечислены флаги [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText и их приблизительные эквиваленты в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
### Причины использования форматированного текста  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представлен ряд элементов управления для рисования текста на экране.  Каждый элемент управления предназначен для различных скриптов и содержит собственный список функций и ограничений.  В целом, элемент <xref:System.Windows.Controls.TextBlock> следует использовать, если требуется ограниченная поддержка текста, например для короткого предложения, которое нужно вставить в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  <xref:System.Windows.Controls.Label> может использоваться, если необходима минимальная поддержка текста.  Дополнительные сведения см. в разделе [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
 Объект <xref:System.Windows.Media.FormattedText> предоставляет более широкие возможности форматирования текста, чем текстовые элементы управления [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Этот объект может быть полезен в тех случаях, когда требуется использовать текст как декоративный элемент. Дополнительные сведения см. в разделе [Преобразование форматированного текста к геометрическому объекту](#converting_formatted_text).  
  
 Кроме того, объект <xref:System.Windows.Media.FormattedText> пригодится при создании объектов, производных от <xref:System.Windows.Media.DrawingVisual>, ориентированных на текст.  <xref:System.Windows.Media.DrawingVisual> — это упрощенный класс рисования, который используется для отрисовки фигур, изображений или текста.  Дополнительные сведения см. в разделе [Пример проверки нажатия с помощью DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).  
  
<a name="using_the_formattedtext_object"></a>   
## Использование объекта FormattedText  
 Чтобы создать форматированный текст, вызовите конструктор <xref:System.Windows.Media.FormattedText.%23ctor%2A> для создания объекта <xref:System.Windows.Media.FormattedText>.  После создания первоначально отформатированной текстовой строки можно применить весь диапазон стилей форматирования.  
  
 Используйте свойство <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>, чтобы ограничить ширину текста.  В соответствии с заданной шириной в тексте используется автоматический перенос слов.  Используйте свойство <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>, чтобы ограничить высоту текста.  Для текста, выходящего за пределы заданного значения высоты, отображается многоточие "…".  
  
 ![Отображенный текст с использованием объекта FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext02.png "FormattedText02")  
Отображенный текст с переносом слов и многоточием  
  
 Можно применить несколько стилей форматирования к одному или нескольким знакам.  Например, можно вызвать как метод <xref:System.Windows.Media.FormattedText.SetFontSize%2A>, так и метод <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> для изменения форматирования первых пяти знаков текста.  
  
 В следующем примере кода создается объект <xref:System.Windows.Media.FormattedText>, к которому применяется несколько стилей форматирования.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### Единица измерения размера шрифта  
 Как и для других текстовых объектов в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], в качестве единиц измерения для объекта <xref:System.Windows.Media.FormattedText> используются аппаратно\-независимые пиксели.  Однако в большинстве приложений [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] в качестве единиц измерения используются точки.  Если в приложениях [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] необходимо использовать отображение текста в единицах точек, следует преобразовать [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] в точки.  В следующем примере показано, как выполнить данное преобразование.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### Преобразование форматированного текста к геометрическому объекту  
 Можно преобразовать форматированный текст в объекты <xref:System.Windows.Media.Geometry>, что позволит создавать другие типы наглядного текста.  Например, можно создать объект <xref:System.Windows.Media.Geometry>, основанный на контуре строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Оконтуривание текста с использованием кисти линейного градиента  
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Пример установки разного цвета для штриха и заливки  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Пример применения кисти к штриху  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Пример применения кисти к штриху и выделению  
  
 Текст, преобразованный в объект <xref:System.Windows.Media.Geometry>, не является набором символов, для которого изменение символов в текстовой строке невозможно.  Тем не менее, внешний вид преобразованного текста можно изменять с помощью свойств штриха и заливки.  Штрих — это контур преобразованного текста, а заливка — область внутри контура преобразованного текста.  Дополнительные сведения см. в разделе [Создание контурного текста](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md).  
  
 Можно также преобразовать форматированный текст в объект <xref:System.Windows.Media.PathGeometry>, который можно использовать для выделения текста.  Например, можно применить анимацию к объекту <xref:System.Windows.Media.PathGeometry> так, что анимация будет следовать за контуром форматированного текста.  
  
 В следующем примере показан форматированный текст, который был преобразован в объект <xref:System.Windows.Media.PathGeometry>.  Анимированный эллипс следует по пути штрихов отображенного текста.  
  
 ![Сфера, следующая по геометрическому пути текста](../../../../docs/framework/wpf/advanced/media/textpathgeometry01.png "TextPathGeometry01")  
Сфера, следующая по геометрическому пути текста  
  
 Дополнительные сведения см. в разделе [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/ru-ru/29f8051e-798a-463f-a926-a099a99e9c67).  
  
 Можно создать другие интересные применения форматированного текста после преобразования его в объект <xref:System.Windows.Media.PathGeometry>.  Например, можно вырезать видео для отображения внутри него.  
  
 ![Отображение видео по геометрическому пути текста](../../../../docs/framework/wpf/advanced/media/videotextdemo01.png "VideoTextDemo01")  
Отображение видео по геометрическому пути текста  
  
<a name="win32_migration"></a>   
## Миграция Win32  
 Возможности <xref:System.Windows.Media.FormattedText> для рисования текста похожи на возможности функции [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText.  Для разработчиков, выполняющих задачи по миграции с [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API, в следующей таблице перечислены флаги [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText и их приблизительные эквиваленты в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
|Флаг DrawText|Эквивалент в WPF|Примечания|  
|-------------------|----------------------|----------------|  
|DT\_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Height%2A> для вычисления соответствующей y\-позиции [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText.|  
|DT\_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|Используйте свойства <xref:System.Windows.Media.FormattedText.Height%2A> и <xref:System.Windows.Media.FormattedText.Width%2A> для вычисления выходного прямоугольника.|  
|DT\_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment>.|  
|DT\_EDITCONTROL|None|Не требуется.  Отрисовка последней строки и пустого места соответствует элементу управления редактированием в Framework.|  
|DT\_END\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming>.<br /><br /> Используйте <xref:System.Windows.TextTrimming> для получения DT\_END\_ELLIPSIS [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] с заключительным многоточием DT\_WORD\_ELIPSIS. В этом случае знак многоточия отображается только в словах, которые не помещаются на одной строке.|  
|DT\_EXPAND\_TABS|None|Не требуется.  Символы табуляции автоматически развертываются на четыре длинных пробела, что по ширине приблизительно равно восьми независимым от языка символам.|  
|DT\_EXTERNALLEADING|None|Не требуется.  Внешнее межстрочное расстояние всегда включается в межстрочный интервал.  Используйте свойство <xref:System.Windows.Media.FormattedText.LineHeight%2A> для создания пользовательского межстрочного интервала.|  
|DT\_HIDEPREFIX|None|Не поддерживается.  Удалите знак "&" из строки перед созданием объекта <xref:System.Windows.Media.FormattedText>.|  
|DT\_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Это выравнивание текста по умолчанию.  Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment>.  \(Только для WPF\)|  
|DT\_MODIFYSTRING|None|Не поддерживается.|  
|DT\_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|Отсечение не происходит автоматически.  Чтобы вырезать текст, используйте свойство <xref:System.Windows.Media.Visual.VisualClip%2A>.|  
|DT\_NOFULLWIDTHCHARBREAK|None|Не поддерживается.|  
|DT\_NOPREFIX|None|Не требуется.  Знак "&" в строке всегда рассматривается как обычный символ.|  
|DT\_PATHELLIPSIS|None|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming>.|  
|DT\_PREFIX|None|Не поддерживается.  Чтобы использовать подчеркивание текста, например для клавиш быстрого вызова или ссылок, используйте метод <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>.|  
|DT\_PREFIXONLY|None|Не поддерживается.|  
|DT\_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.TextAlignment%2A> со значением <xref:System.Windows.TextAlignment>.  \(Только для WPF\)|  
|DT\_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|Установите для свойства <xref:System.Windows.Media.FormattedText.FlowDirection%2A> значение <xref:System.Windows.FlowDirection>.|  
|DT\_SINGLELINE|None|Не требуется.  Объекты <xref:System.Windows.Media.FormattedText> используются как однострочные элементы управления до тех пор, пока не установлено свойство <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> или в тексте не встречается символ возврата каретки или перевода строки \(CR\/LF\).|  
|DT\_TABSTOP|None|Не поддерживается для пользовательских позиций табуляции.|  
|DT\_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|Не требуется.  По умолчанию используется выравнивание по верхнему краю.  Другие значения вертикального расположения могут определяться с помощью свойства <xref:System.Windows.Media.FormattedText.Height%2A> для вычисления соответствующей y\-позиции [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText.|  
|DT\_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Height%2A> для вычисления соответствующей y\-позиции [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText.|  
|DT\_WORDBREAK|None|Не требуется.  Для объектов <xref:System.Windows.Media.FormattedText> перенос слов выполняется автоматически.  Отключить эту функцию нельзя.|  
|DT\_WORD\_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|Используйте свойство <xref:System.Windows.Media.FormattedText.Trimming%2A> со значением <xref:System.Windows.TextTrimming>.|  
  
## См. также  
 <xref:System.Windows.Media.FormattedText>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Создание контурного текста](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)   
 [How to: Create a PathGeometry Animation for Text](http://msdn.microsoft.com/ru-ru/29f8051e-798a-463f-a926-a099a99e9c67)