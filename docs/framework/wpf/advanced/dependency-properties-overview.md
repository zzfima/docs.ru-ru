---
title: "Общие сведения о свойствах зависимости"
description: "Свойство, которое реализуется в системе свойств WPF известен как свойство зависимостей. В этом обзоре описывается в системе свойств WPF и возможности для свойства зависимостей."
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], attached
- properties [WPF], overview
- styles [WPF]
- attached properties [WPF]
- data binding [WPF]
- dependency properties [WPF]
- resources [WPF], references to
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aa1ad02de74cc73ea67267de7548442078a2f5db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-properties-overview"></a>Общие сведения о свойствах зависимости

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет набор служб, которые можно использовать для расширения функциональных возможностей свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. В совокупности эти службы обычно называются системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Свойство, поддерживаемое системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], называется свойством зависимостей. В этом обзоре описывается система свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и возможности свойства зависимостей. В обзоре также описывается использование существующих свойств зависимостей в языке XAML и коде. Кроме того, в обзоре представлены общие сведения о специальных аспектах свойств зависимостей, таких как метаданные свойств зависимостей и способы создания собственного свойства зависимостей в пользовательском классе.

## <a name="prerequisites"></a>Предварительные требования
В этом разделе предполагается, что у вас есть базовые знания о платформе [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] и объектно-ориентированном программировании. Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и написании приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Свойства среды CLR и свойства зависимостей
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства обычно представляются как свойства [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. На базовом уровне можно взаимодействовать с этими свойствами непосредственно и не знать, что они реализуются как свойства зависимостей. Тем не менее настоятельно рекомендуется ознакомиться с некоторыми, а лучше со всеми, функциями системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], чтобы воспользоваться преимуществами этих функций.

Свойства зависимостей предназначены для предоставления способа вычисления значения свойства по значениям других входных данных. Эти входные данные могут включать в себя системные свойства, такие как темы и пользовательские параметры, JIT-механизмы определения свойств, такие как привязка данных и анимации (раскадровки), шаблоны многократного использования, например ресурсы и стили, а также значения, известные благодаря отношениям между родительскими и дочерними элементами с другими элементами в дереве. Кроме того, свойство зависимостей может быть реализовано для обеспечения автономной проверки, значений по умолчанию, обратных вызовов, отслеживающих изменения других свойств, и системы, которая может приводить значения свойств на основе информации потенциальной среды выполнения. Производные классы также могут изменять некоторые специфические характеристики существующего свойства путем переопределения метаданных свойства зависимостей вместо того, чтобы переопределять фактические реализации существующих свойств или создавать новые свойства.

В справочнике по SDK можно определить, что это свойство является свойством зависимостей по наличию раздела сведений о свойстве зависимостей на странице управляемой ссылки для этого свойства. Сведения о свойстве зависимостей раздел содержит ссылку на <xref:System.Windows.DependencyProperty> идентификатор поля для этого свойства зависимости, а также включает список параметров метаданных, заданных для этого свойства, информацию о переопределениях каждого класса и другие сведения.

## <a name="dependency-properties-back-clr-properties"></a>Свойства зависимостей резервное свойств среды CLR
Свойства зависимостей и система свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] расширяют функциональные возможности свойства, предоставляя тип, который поддерживает свойство, в качестве альтернативной реализации для стандартного способа обеспечения свойства с помощью закрытого поля. Этот тип называется <xref:System.Windows.DependencyProperty>. Другие важные типа, который определяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] система свойств <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject>Определяет базовый класс для регистрации и владельцем свойства зависимостей.

Ниже приведен список терминов, используемых в этой документации [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] при описании свойств зависимостей.

- **Свойства зависимостей:** свойство, поддерживаемый <xref:System.Windows.DependencyProperty>.

- **Идентификатор для свойства зависимостей:** A <xref:System.Windows.DependencyProperty> экземпляр, который извлекается как возвращаемое значение при регистрации свойства зависимостей, а затем сохраняются в виде статический член класса. Этот идентификатор используется в качестве параметра для многих [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], взаимодействующих с системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- **CLR-оболочка.** Фактические реализации получения и задания свойства. Эти реализации включают идентификатор свойства зависимостей, используя его в <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> вызовов, таким образом обеспечение для свойства с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] системы свойств.

В следующем примере определяется `IsSpinning` свойства зависимостей и показывает связь между <xref:System.Windows.DependencyProperty> идентификатор для свойства, которое выполняется резервное.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
Соглашение об именовании, свойства и его обеспечивающее <xref:System.Windows.DependencyProperty> поле имеет значение. Имя поля всегда определяется как имя свойства с добавленным суффиксом `Property`. Дополнительные сведения об этом соглашении и разъяснения по нему см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Установка значений свойств
Свойства можно задать с помощью кода или XAML.

### <a name="setting-property-values-in-xaml"></a>Установка значения свойства в XAML 
В следующем примере на XAML задается красный цвет фона кнопки. В этом примере показан случай, где простое строковое значение для атрибута в языке XAML, преобразованные средством синтаксического анализа WPF XAML в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] типа ( <xref:System.Windows.Media.Color>, посредством <xref:System.Windows.Media.SolidColorBrush>) в созданном коде.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

Язык XAML поддерживает различные синтаксические формы для задания свойств. Выбор синтаксиса для конкретного свойства зависит от типа значения, которое использует свойство, а также других факторов, например наличия преобразователя типов. Дополнительные сведения об использовании синтаксиса XAML для задания свойств см. в разделе [Общие сведения о XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) и [Подробное описание синтаксиса XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).

В следующем примере на языке XAML в качестве примера синтаксиса без атрибутов показан другой цвет фона кнопки. Здесь вместо задания простой заливки цветом в качестве фона определяется изображение. Это делается с помощью элемента, представляющего изображение, и источника изображения, указанного как атрибут вложенного элемента. Это пример синтаксиса элемента свойства.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Задание свойств в коде
 Задание значений свойств зависимостей с помощью кода обычно представляет собой обращение к реализации метода установки, предоставленного "оболочкой" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Получение значения свойства также является фактически вызовом реализации метода получения, имеющегося в "оболочке":

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

Также можно вызывать в системе свойств [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> напрямую. Обычно в этом нет необходимости при использовании существующих свойств (оболочки более удобны и дают лучшее предоставление свойства для средств разработчика), но в некоторых сценариях удобнее использовать непосредственный вызов [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].

Свойства можно задать на языке XAML, а затем использовать их в коде, с помощью кода программной части. Дополнительные сведения см. в разделе [Код программной части и XAML в WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Свойство функциональные возможности, предоставляемые свойством зависимости
Свойство зависимостей предоставляет дополнительные функциональные возможности в сравнении с теми, которые предоставляются свойством, поддерживаемым полем. Часто каждая такая функция представляет или поддерживает какую-либо конкретную функцию из полного набора функций [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

- [Ресурсы](#resources)

- [Привязка данных](#data-binding)

- [Стили](#styles)

- [Анимации](#animations)

- [Переопределение метаданных](#metadata-overrides)

- [Наследование значения свойства](#property-value-inheritance)

- [Интеграция конструктора WPF](#wpf-designer-integration)

### <a name="resources"></a>Ресурсы
Значение свойства зависимостей можно задать ссылкой на ресурс. Ресурсы обычно указываются как значение свойства `Resources` корневого элемента страницы или приложения. (Эти расположения делают возможным наиболее удобный доступ к ресурсу.) В следующем примере показан способ определения <xref:System.Windows.Media.SolidColorBrush> ресурсов.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

После определения ресурса можно ссылаться на него и использовать для предоставления значения свойства:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

Этот конкретный ресурс называется [Расширение разметки DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) (в WPF XAML можно использовать статическую или динамическую ссылку на ресурс). Чтобы использовать динамическую ссылку на ресурс, необходимо задать значение для свойства зависимостей. Это явное использование динамической ссылки на ресурс, разрешенное системой свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).

> [!NOTE]
> Ресурсы считаются локальными значениями. Это означает, что если задается другое локальное значение, ссылка на ресурс удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

### <a name="data-binding"></a>привязка данных,
Свойства зависимостей могут ссылаться на значения через привязки данных. Привязка данных работает через специальный синтаксис расширения разметки в XAML, или <xref:System.Windows.Data.Binding> объекта в коде. Благодаря функции привязки данных определение окончательного значения свойства откладывается до времени выполнения. Затем значение извлекается из источника данных.

В следующем примере задается <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button>, с помощью привязки объявленную в XAML. Привязка использует контекст наследуемые данные и <xref:System.Windows.Data.XmlDataProvider> источника данных (не показано). Сама привязка указывает свойство нужного источника, <xref:System.Windows.Data.Binding.XPath%2A> в источнике данных.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> Привязки считаются локальными значениями. Это означает, что если задается другое локальное значение, привязка удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

Свойства зависимостей или <xref:System.Windows.DependencyObject> класса, выполните не имеет собственной поддержки <xref:System.ComponentModel.INotifyPropertyChanged> для формирования уведомлений об изменениях в <xref:System.Windows.DependencyObject> исходного значения свойства для операций привязки данных. Дополнительные сведения о создании свойств для использования в привязках данных, которые могут передавать сообщения об изменениях в целевой объект привязки данных, см. в разделе [Общие сведения о привязках данных](../../../../docs/framework/wpf/data/data-binding-overview.md).

### <a name="styles"></a>Стили
Существует два основных направления применения свойств зависимостей — стили и шаблоны. Стили особенно полезны для настройки свойств, определяющих приложение [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Обычно стили определяются в XAML в качестве ресурсов. Стили взаимодействуют с системой свойств, так как они обычно содержат код для задания значения конкретного свойства, а также "правила срабатывания", которые определяют изменение значения свойства в зависимости от значения другого свойства в режиме реального времени.

В следующем примере создается очень простой стиль (который будет определяться внутри <xref:System.Windows.FrameworkElement.Resources%2A> словаря, не показаны), этот стиль применяется непосредственно к <xref:System.Windows.FrameworkElement.Style%2A> свойство для <xref:System.Windows.Controls.Button>. Присвоение в стиле задает <xref:System.Windows.Controls.Control.Background%2A> свойства для элемента управления <xref:System.Windows.Controls.Button> зеленый цвет.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).

### <a name="animations"></a>Анимации
Свойства зависимостей могут быть анимированы. При выполнении анимации анимированное значение действует с более высоким приоритетом, чем любое другое значение (например, локальное значение), которое имелось бы у свойства.

В следующем примере анимируется <xref:System.Windows.Controls.Control.Background%2A> на <xref:System.Windows.Controls.Button> свойств (с технической точки зрения <xref:System.Windows.Controls.Control.Background%2A> анимации с помощью синтаксиса элемента свойства для указания пустого <xref:System.Windows.Media.SolidColorBrush> как <xref:System.Windows.Controls.Control.Background%2A>, то <xref:System.Windows.Media.SolidColorBrush.Color%2A> , свойство <xref:System.Windows.Media.SolidColorBrush> напрямую анимировать свойство).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Дополнительные сведения об анимации свойств см. в разделах [Общие сведения об анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [Общие сведения о раскадровках](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Переопределения метаданных
Правила взаимодействия свойства зависимостей можно изменять путем переопределения метаданных свойства при наследовании от класса, в котором это свойство зависимостей было изначально зарегистрировано. Переопределение метаданных зависит <xref:System.Windows.DependencyProperty> идентификатор. Переопределение метаданных не требует повторной реализации свойства. Изменение метаданных изначально обрабатывается системой свойств. Каждый класс потенциально содержит отдельные метаданные для всех свойств, которые наследуются от базовых классов, отдельно по каждому типу.

В следующем примере переопределяется метаданные для свойства зависимостей <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. Переопределение метаданных этого конкретного свойства зависимостей включено в состав шаблона реализации, с помощью которого создаются элементы управления, которые могут использовать стили, заданные по умолчанию в темах.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Дополнительные сведения о переопределении и получении метаданных свойства см. в разделе [Метаданные свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Наследование значения свойства
Элемент может наследовать значение свойства зависимостей от своего родительского элемента в дереве объектов.

> [!NOTE]
> Наследование значений свойств не включено глобально для всех свойств зависимостей, потому что выполнение вычислений при наследовании отрицательно сказывается на производительности. Наследование значений свойств обычно включается только для тех свойств, для которых в конкретном сценарии предполагается, что это наследование является оправданным. Определить, наследуется ли данное свойство зависимостей, можно, просмотрев раздел **Сведения о свойствах зависимостей** для этого свойства в справочнике по SDK.

В следующем примере показана привязка и задает <xref:System.Windows.FrameworkElement.DataContext%2A> свойства, указывающее источник привязки, который не был показан в предыдущем примере привязки. Все последующие привязки в дочерних объектов не обязательно для указания источника, они могут использовать унаследованное значение <xref:System.Windows.FrameworkElement.DataContext%2A> в родительском объекте <xref:System.Windows.Controls.StackPanel> объекта. (Кроме того, вместо этого может выбрать дочерний объект напрямую указать свой собственный <xref:System.Windows.FrameworkElement.DataContext%2A> или <xref:System.Windows.Data.Binding.Source%2A> в <xref:System.Windows.Data.Binding>и намеренно не использовать унаследованное значение для контекста данных привязок.)

[!code-xaml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Дополнительные сведения см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>Интеграция конструктора WPF
Пользовательский элемент управления со свойствами, которые реализуются как свойства зависимостей, получает соответствующую поддержку [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]. Один из примеров этого — возможность редактирования прямых и присоединенных свойств зависимостей с помощью окна **Свойства**. Дополнительные сведения см. в разделе [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Приоритет значения свойства зависимости
Извлекая значение свойства зависимостей, вы, вероятно, получаете значение, которое было установлено для этого свойства с использованием какого-либо другого свойства, дающего входное значение и участвующего в системе свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Для значений свойств зависимостей установлена система приоритетов, благодаря чему различные сценарии получения свойствами своих значений могут выполняться вполне предсказуемо.

Рассмотрим следующий пример. В примере содержит стиль, применяемый ко всем кнопкам и их <xref:System.Windows.Controls.Control.Background%2A> свойства, но также указывается одна кнопка с локально заданным <xref:System.Windows.Controls.Control.Background%2A> значение.

> [!NOTE]
> В документации по SDK при описании свойств зависимостей используется термин "локальное значение" или иногда "локально заданное значение". Локально заданное значение — это значение свойства, которое задается непосредственно для экземпляра объекта в коде или как атрибут элемента на языке XAML.  
  
Фактически для первой кнопки свойство задано дважды, но применяется только одно значение, то, у которого наивысший приоритет. Локально заданное значение имеет наивысший приоритет (исключение — выполняющаяся анимация, но анимаций нет в этом примере), поэтому вместо значения цвета фона первой кнопки, определенного стилем, используется локально заданное значение. Для второй кнопки не задано локальное значение (или другое значение с более высоким приоритетом, чем у стиля), поэтому цвет фона для этой кнопки определяется стилем.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>Почему существует приоритета свойств зависимостей
Обычно не требуется постоянное применение стиля, переопределяющее локально заданные значения отдельных элементов (в противном случае было бы вообще очень сложно использовать стили и элементы). Поэтому значения, определяемые стилем, имеют более низкий приоритет, чем локально заданные значения. Более полный список свойств зависимостей и порядок определения их действующих значений см. в разделе [Приоритет значений свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

> [!NOTE]
> Не все свойства, определенные для элементов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], являются свойствами зависимостей. Как правило, свойства реализуются в виде свойств зависимостей только в тех случаях, когда возникает потребность поддерживать по крайней мере один из сценариев, реализуемых системой свойств (привязку данных, применение стилей, анимацию, поддержку значений по умолчанию, наследование, присоединенные свойства или проверку).

## <a name="learning-more-about-dependency-properties"></a>Дополнительные сведения о свойствах зависимости  

- Присоединенное свойство — это тип свойства, поддерживающий специализированный синтаксис на языке XAML. Присоединенные свойства часто не имеют однозначного соответствия со свойствами [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] и не обязательно являются свойствами зависимостей. Обычным назначением присоединенного свойства является разрешение дочерним элементам передавать значения свойств родительским элементам, даже если это свойство не включено в список элементов класса обоих элементов — родительского и дочернего. Основной скрипт заключается в разрешении дочерним элементам уведомлять родительский элемент, как они представлены в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; например, в разделе <xref:System.Windows.Controls.DockPanel.Dock%2A> или <xref:System.Windows.Controls.Canvas.Left%2A>. Дополнительные сведения см. в разделе [Общие сведения о присоединенных свойствах](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

- У разработчиков компонентов и разработчиков приложений может возникнуть потребность в создании собственных свойств зависимостей для получения таких возможностей, как привязка данных, поддержка стилей, проверка и приведение данных. Дополнительные сведения см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

- Обычно свойства зависимостей определяются как открытые свойства, доступные или, по крайней мере, видимые любому вызывающему объекту, имеющему доступ к экземпляру. Дополнительные сведения см. в разделе [Безопасность свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-security.md).

## <a name="see-also"></a>См. также
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Свойства зависимости "только для чтения"](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Архитектура WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
