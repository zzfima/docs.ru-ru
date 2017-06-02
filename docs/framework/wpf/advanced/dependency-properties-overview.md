---
title: "Общие сведения о свойствах зависимости | Microsoft Docs"
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
  - "вложенные свойства"
  - "привязка данных"
  - "свойства зависимостей"
  - "свойства, присоединенные"
  - "свойства, общие сведения"
  - "ресурсы, ссылки на"
  - "стили"
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Общие сведения о свойствах зависимости
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет набор служб, которые могут использоваться для расширения функциональности свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  Собирательно, эти службы называют системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Свойство, поддерживаемое системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], называется [свойством зависимостей](GTMT). Этот обзор содержит описание системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и возможностей [свойства зависимостей](GTMT). Он также включает руководство по использованию существующих [свойств зависимостей](GTMT) в разметке XAML и в программном коде.  Этот раздел также знакомит со специальными аспектами свойств зависимости такими, как метаданные свойства зависимости и способы создания собственного свойства зависимости в настраиваемом классе.  
  
   
  
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтение этого раздела подразумевает наличие базовых знаний о [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и об объектно\-ориентированном программировании.  Чтобы выполнить примеры в этом подразделе, следует также понимать принципы работы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и знать, как создаются приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения см. в разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
<a name="why_dependency_properties"></a>   
## Свойства среды CLR и свойства зависимостей  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства обычно предоставляются как свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)].  На базовом уровне можно напрямую взаимодействовать с этими свойствами и не знать, что они реализованы в виде [свойства зависимостей](GTMT).  Однако следует более близко ознакомиться с некоторыми или со всеми компонентами системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], чтобы можно было использовать их преимущества.  
  
 Целью [свойств зависимости](GTMT) является предоставление способа для вычисления значения свойства на основе значений других входных данных.  Эти другие входные данные могут включать свойства системы, такие как темы и пользовательские параметры, механизмы определения свойства по требованию, например, привязка данных и анимации\/раскадровки, многократное использование шаблонов, например, ресурсов и стилей, или значения, известные через связи типа родитель\-потомок с другими элементами в дереве элементов.  Кроме того, [свойство зависимости](GTMT) может быть реализовано для обеспечения независимой проверки, значений по умолчанию, обратных вызовов, следящих за изменениями других свойств, и системы, удерживающей значения свойства на основе информации потенциальной исполняющей среды.  Производные классы могут изменить некоторые специфические характеристики существующего свойства с помощью переопределения метаданных свойства зависимости скорее, чем переопределения фактической реализации существующих свойств или создания новых свойств.  
  
 В справочнике SDK можно определить, какое свойство является свойством зависимости по наличию раздела "Сведения о свойстве зависимости" на странице управляемой ссылки для этого свойства.  Раздел "Сведения о свойстве зависимости" включает ссылку на идентификатор поля <xref:System.Windows.DependencyProperty> для этого свойства зависимости, а также включает список параметров метаданных, установленных для этого свойства, информацию по переопределению каждого класса и другие сведения.  
  
<a name="back_dependency_properties"></a>   
## Свойства зависимости обеспечивают свойства CLR  
 [Свойства зависимости](GTMT) и система свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] расширяют функциональность свойства, предоставляя тип, который обеспечивает свойство, в качестве альтернативной реализации для стандартного шаблона обеспечения свойства с помощью закрытого поля.  Этот тип называется <xref:System.Windows.DependencyProperty>.  Другом важным типом, определяющим систему свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> определяет базовый класс, который может регистрировать [свойство зависимости](GTMT) и быть его владельцем.  
  
 Далее даны краткие определения терминов, используемых в этой документации [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] при описании [свойств зависимости](GTMT):  
  
-   **свойство зависимости.** Свойство, обеспечиваемое <xref:System.Windows.DependencyProperty>;  
  
-   **Идентификатор свойства зависимостей.** Экземпляр <xref:System.Windows.DependencyProperty>, который извлекается как возвращаемое значение при регистрации [свойства зависимостей](GTMT) и затем хранится в качестве статического члена класса.  Этот идентификатор используется в качестве параметра для многих [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], взаимодействующих с системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)];  
  
-   **программа\-оболочка среды CLR.** Фактические реализации получения и задания свойства.  Эти реализации включают идентификатор свойства зависимости, используя его в вызовах <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>, предоставляя таким образом обеспечение для свойства, использующего систему свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В следующем примере определяется [свойство зависимости](GTMT) `IsSpinning` и показывается отношение идентификатора <xref:System.Windows.DependencyProperty> к обеспечиваемому им свойству.  
  
 [!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
 [!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
[!code-csharp[PropertiesOvwSupport#DPFormBasic2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic2)]  
  
 Важным является правило именования свойства и его обеспечивающее поле <xref:System.Windows.DependencyProperty>.  Имя поля всегда является и именем свойства с добавлением суффикса `Property`.  Дополнительные сведения об этом правиле и его основаниях содержатся в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
<a name="setting_property_values"></a>   
## Установка значений свойства  
 Свойства можно задать либо в программном коде либо в разметке XAML.  
  
<a name="local_property_values"></a>   
### Установка значений свойства в XAML  
 В следующем примере XAML задается красный цвет фона кнопки.  В этом примере показана ситуация, в которой в созданном коде строковый параметр для атрибута XAML является типом, преобразуемым средством синтаксического анализа XAML системы WPF в тип [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] \(<xref:System.Windows.Media.Color> в виде объекта <xref:System.Windows.Media.SolidColorBrush>\).  
  
 [!code-xml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]  
  
 XAML поддерживает различные формы синтаксиса для задания свойств.  Выбор синтаксиса для конкретного свойства будет зависеть как от типа значения, используемого свойством, так и от других факторов, таких как наличие преобразователя типа.  Дополнительные сведения об использовании синтаксиса XAML для задания свойств см. в разделах [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 В качестве примера безатрибутного синтаксиса в следующем примере XAML задается другой цвет фона кнопки.  В этот раз, вместо настройки простой заливки цветом фон задается в виде изображения с помощью элемента, представляющего это изображение, и источника этого изображения, указанного как атрибут вложенного элемента.  Это пример синтаксиса элемента свойства.  
  
 [!code-xml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]  
  
<a name="setting_properties_code"></a>   
### Установка свойств в программном коде  
 Установка значений [свойства зависимости](GTMT) в коде обычно заключается просто в вызове реализации задания свойства, предоставляемого "программой\-оболочкой" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]  
  
 Получение значения свойства также, фактически, является вызовом для реализации получения "программы\-оболочки":  
  
 [!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]  
  
 Также можно непосредственно вызвать систему свойства [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>.  Обычно это необязательно при использовании существующих свойств \(оболочки наиболее удобны и предоставляют лучшее предоставление свойства для средств разработчика\), но непосредственный вызов [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] подходит для определенных случаев.  
  
 Свойства можно также установить в XAML, а позднее получить доступ к ним в программном коде через код программной части.  Дополнительные сведения см. в разделе [Код программной части и XAML в WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
<a name="functionality"></a>   
## Функциональность свойства, предоставленная свойством зависимости  
 Свойство зависимости обеспечивает функциональность, расширяющую функциональность свойства в отличие от свойства, которое обеспечивается полем.  Часто каждый такой набор функций представляет или поддерживает специальную возможность общего набора возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   [Ресурсы](#setting_properties_resources)  
  
-   [привязка данных,](#setting_properties_data_binding)  
  
-   [Стили](#setting_properties_styles)  
  
-   [Анимации](#animations)  
  
-   [переопределения метаданных,](#metadata)  
  
-   [наследование значения свойства,](#setting_properties_inheritance)  
  
-   [интеграция конструктора WPF.](#vs2008_integration)  
  
<a name="setting_properties_resources"></a>   
### Ресурсы  
 Значение свойства зависимости может быть задано ссылкой на ресурс.  Ресурсы обычно указываются как значения свойства `Resources` корневого элемента страницы или приложения \(эти расположения делают возможным наиболее удобный доступ к ресурсу\).  В следующем примере показан порядок определения ресурса <xref:System.Windows.Media.SolidColorBrush>.  
  
 [!code-xml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]  
  
 После того как ресурс определен, на него можно ссылаться и использовать его для предоставления значения свойства:  
  
 [!code-xml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]  
  
 На данный ресурс ссылаются как на [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) \(в XAML WPF можно использовать либо статическую, либо динамическую ссылку на ресурс\).  Чтобы использовать динамическую ссылку на ресурс, необходимо установить свойство зависимости, поэтому это является специфическим использованием динамической ссылки на ресурс, которое становится возможным благодаря системе свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
> [!NOTE]
>  Ресурсы рассматриваются как локальное значение. Это означает, что если задать другое локальное значение, то ссылка на ресурс будет удалена.  Дополнительные сведения см. в разделе [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
<a name="setting_properties_data_binding"></a>   
### Привязка данных  
 Свойство зависимости может ссылаться на значение с помощью привязки данных.  Привязка данных работает через специальный синтаксис расширения разметки в XAML или объект <xref:System.Windows.Data.Binding> в программном коде.  С помощью привязки данных определение окончательного значения свойства откладывается до времени выполнения, а во время выполнения значение извлекается из источника данных.  
  
 В следующем примере показана установка свойства <xref:System.Windows.Controls.ContentControl.Content%2A> для элемента управления <xref:System.Windows.Controls.Button> с помощью привязки, объявленной в XAML.  Привязка использует наследуемый контекст данных и источник данных <xref:System.Windows.Data.XmlDataProvider> \(не показано\).  Привязка сама задает нужное свойство источника с помощью <xref:System.Windows.Data.Binding.XPath%2A> в источнике данных.  
  
 [!code-xml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]  
  
> [!NOTE]
>  Привязки рассматриваются как локальное значение. Это означает, что если задать другое локальное значение, то привязка будет удалена.  Дополнительные сведения см. в разделе [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
 Свойства зависимости или класс <xref:System.Windows.DependencyObject> изначально не поддерживают <xref:System.ComponentModel.INotifyPropertyChanged> для формирования уведомлений об изменениях в значении свойства источника <xref:System.Windows.DependencyObject> для операций привязки данных.  Дополнительных сведения о создании свойств для использования в привязке данных, которые могли бы предоставлять отчет об изменениях в целевой привязке данных, см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
<a name="setting_properties_styles"></a>   
### Стили  
 Стили и шаблоны являются двумя главными мотивированными скриптами для использования свойств зависимости.  Стили особенно полезны для настройки свойств, определяющих [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] приложения.  Обычно стили определяются в качестве ресурсов в XAML.  Стили взаимодействуют с системой свойств, так как они обычно содержат "присвоения" для конкретного свойства, а также "триггеры", которые изменяют значение свойства на основе значения реального времени для другого свойства.  
  
 В следующем примере создается очень простой стиль \(который будет определяться внутри словаря <xref:System.Windows.FrameworkElement.Resources%2A>, не показано\), а затем этот стиль применяется непосредственно к свойству <xref:System.Windows.FrameworkElement.Style%2A> для элемента управления <xref:System.Windows.Controls.Button>.  Присвоение в стиле задает значение "зеленый" свойства <xref:System.Windows.Controls.Control.Background%2A> для элемента управления <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]  
  
 [!code-xml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]  
  
 Дополнительные сведения см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="animations"></a>   
### Анимации  
 Свойства зависимости могут быть анимированными.  При применении и выполнении анимации анимированное значение действует с более высоким приоритетом, чем любое значение \(например локальное значение\), которое свойство имеет в противном случае.  
  
 В следующем примере анимируется значение элемента <xref:System.Windows.Controls.Control.Background%2A> в свойстве <xref:System.Windows.Controls.Button> \(формально, <xref:System.Windows.Controls.Control.Background%2A> анимируется с использованием синтаксиса элемента свойства для указания пустого <xref:System.Windows.Media.SolidColorBrush> как <xref:System.Windows.Controls.Control.Background%2A>, затем свойство <xref:System.Windows.Media.SolidColorBrush.Color%2A> этого элемента <xref:System.Windows.Media.SolidColorBrush> оказывается непосредственно анимируемым свойством\).  
  
 [!code-xml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]  
  
 Дополнительные сведения об анимации свойств содержатся в разделах [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
<a name="metadata"></a>   
### Переопределения метаданных  
 Можно изменять некоторые параметры поведения [свойства зависимости](GTMT) с помощью переопределения метаданных для этого свойства при создании производного от класса, изначально регистрирующего [свойство зависимости](GTMT).  Переопределение метаданных зависит от идентификатора <xref:System.Windows.DependencyProperty>.  Переопределение метаданных не требует повторной реализации свойства.  Изменение метаданных изначально обрабатывается системой свойств; каждый класс потенциально содержит отдельные метаданные для всех свойств, которые наследуются от базовых классов, на основе каждого типа.  
  
 В следующем примере метаданные переопределяются для свойства зависимости <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>.  Переопределение этих метаданных свойства зависимости является частью шаблона реализации, создающего элементы управления, которые могут использовать стили по умолчанию из темы.  
  
 [!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
 [!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]  
  
 Дополнительные сведения о переопределении или получении метаданных свойства содержатся в разделе [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="setting_properties_inheritance"></a>   
### Наследование значения свойства  
 Элемент может наследовать значения свойства зависимостей от родительского элемента дерева объектов.  
  
> [!NOTE]
>  Поведение наследования значения свойства доступно не глобально для всех свойств зависимости, поскольку время вычисления наследования оказывает влияние на быстродействие системы.  Наследование значения свойства обычно доступно только для свойств, где определенный скрипт предполагает, что наследование свойств значения является подходящим методом.  Определить, поддерживает ли свойство зависимостей наследование, можно с помощью раздела **Сведения о свойстве зависимостей** для этого свойства зависимостей справочнике SDK.  
  
 В следующем примере показана привязка и присвоение значений свойству <xref:System.Windows.FrameworkElement.DataContext%2A>, указывающему источник привязки, который не был показан в предыдущем примере привязки.  Никакие последующие привязки в дочерних объектах не требуют задания источника, они могу использовать унаследованное значение из объекта <xref:System.Windows.FrameworkElement.DataContext%2A> в родительском объекте <xref:System.Windows.Controls.StackPanel>.  \(Также можно напрямую задать для дочернего объекта собственное значение <xref:System.Windows.FrameworkElement.DataContext%2A> или <xref:System.Windows.Data.Binding.Source%2A> в объекте <xref:System.Windows.Data.Binding> и намеренно не использовать унаследованное значение для контекста данных привязок.\)  
  
 [!code-xml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]  
  
 Дополнительные сведения см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="vs2008_integration"></a>   
### Интеграция конструктора WPF  
 Пользовательский элемент управления со свойствами, которые реализованы в виде свойств зависимостей, получает соответствующую поддержку [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  Примером является возможность редактирования прямых и вложенных свойств зависимостей с помощью окна **Свойства**.  Дополнительные сведения см. в разделе [Общие сведения о разработке управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="value_determination"></a>   
## Приоритет значения свойств зависимостей  
 Получение значения [свойства зависимости](GTMT) означает, что потенциально получено значение, которое было установлено для этого свойства посредством любого из остальных источников входных данных на основе свойств, участвующих в системе свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Приоритет значения свойства зависимости осуществляется таким образом, чтобы можно было предсказать взаимодействие различных скриптов для получения свойствами их значений.  
  
 Рассмотрим следующий пример.  В примере выполняется включение стиля, который применяется для всех кнопок и их свойств <xref:System.Windows.Controls.Control.Background%2A>, затем также указывается одна кнопка с локально заданным значением <xref:System.Windows.Controls.Control.Background%2A>.  
  
> [!NOTE]
>  Иногда при описании свойств зависимости в документации SDK использует термин "локальное значение" или "локально заданное значение".  Локально заданное значение является значением свойства, которое устанавливается непосредственно для экземпляра объекта в программном коде или как атрибут элемента в XAML.  
  
 Фактически, для первой кнопки свойство установлено дважды, но применяется только одно значение с более высоким приоритетом.  локально заданное значение имеет наивысший приоритет \(за исключением случая выполняемой анимации, но не для анимации, применяемой в этом примере\) и, таким образом, для цвета фона первой кнопки используется локально заданное значение вместо значения присваивающего объекта.  Вторая кнопка не имеет локального значения \(и никаких других значений с более высоким приоритетом, чем стиль, заданный присваивающим объектом\) и, таким образом, цвет фона для этой кнопки поступает из стиля присваивающего объекта.  
  
 [!code-xml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  
  
### Обоснования приоритета свойств зависимости  
 Обычно, нежелательно, чтобы стили применялись всегда и скрывали каждое локально заданное значение отдельного элемента \(в противном случае будет очень сложно использовать стили или элементы в общем\).  Поэтому значения, полученные из стилей, работают с более низким приоритетом, чем локально заданные значения.  Более полный список свойств зависимости и расположений, из которых могут поступать действующие значения свойства зависимости, см. в разделе [Приоритет значения свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).  
  
> [!NOTE]
>  Существует ряд свойств, определенных для элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые не являются свойствами зависимости.  В целом, свойства были реализованы в виде свойств зависимостей только там, где возникала необходимость поддерживать по крайней мере один из скриптов, реализуемых системой свойств: привязка данных, стили, анимирование, поддержка значений по умолчанию, наследование, вложенные свойства или недействительность.  
  
<a name="dp_implement_roadmap"></a>   
## Дополнительные сведения о свойствах зависимости  
  
-   [Присоединенное свойство](GTMT) является типом свойства, поддерживающим специализированный синтаксис XAML.  Вложенное свойство часто не имеет соответствия 1:1 со свойством [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и не обязательно является [свойством зависимости](GTMT).  Обычная цель [вложенного свойства](GTMT) заключается в разрешении дочерним элементам отправлять отчеты о значении свойств родительским элементам, даже если родительский и дочерний элементы не обладают этим свойством как частью списка элементов класса.  Основной скрипт заключается в разрешении дочерним элементам уведомлять родительский элемент о том, как они должны быть представлены в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; пример содержится в разделе <xref:System.Windows.Controls.DockPanel.Dock%2A> или <xref:System.Windows.Controls.Canvas.Left%2A>.  Дополнительные сведения см. в разделе [Общие сведения о вложенных свойствах зависимостей](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
-   Разработчики компонента или разработчики приложения могут пожелать создать собственное [свойство зависимости](GTMT) для включения возможностей, таких как привязка данных или поддержка стилей, или для аннулирования и поддержки приведения значения.  Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Обычно свойства зависимости должны рассматриваться как открытые свойства, доступные или, по крайней мере, видимые любому вызывающему объекту, который имеет доступ к экземпляру.  Дополнительные сведения см. в разделе [Безопасность свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
## См. также  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Свойства зависимости "только для чтения"](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Архитектура WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)