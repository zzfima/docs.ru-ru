---
title: "Пользовательские свойства зависимостей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- implementing [WPF], wrappers
- registering properties [WPF]
- properties [WPF], metadata
- metadata [WPF], for properties
- custom dependency properties [WPF]
- properties [WPF], registering
- wrappers [WPF], implementing
- dependency properties [WPF], custom
ms.assetid: e6bfcfac-b10d-4f58-9f77-a864c2a2938f
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1ee7c7b4e21d147bad1cd8e4b854c0ff4fe13aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="custom-dependency-properties"></a>Пользовательские свойства зависимостей
В этом разделе описываются основания для создания настраиваемых свойств зависимостей для приложений [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], а также этапы и некоторые варианты реализации, которые могут повысить производительность, удобство использования и универсальность свойств.  
  

  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] и написании простых приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="whatis"></a>   
## <a name="what-is-a-dependency-property"></a>Что такое свойство зависимостей?  
 Реализовать поведение, аналогичное свойству [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], для поддержки стилизации, привязки данных, наследования, анимации и значений по умолчанию можно путем реализации его как свойства зависимостей. Свойства зависимостей являются свойствами, которые зарегистрированы с помощью [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] системе свойств путем вызова <xref:System.Windows.DependencyProperty.Register%2A> метод (или <xref:System.Windows.DependencyProperty.RegisterReadOnly%2A>), и зарезервированы <xref:System.Windows.DependencyProperty> поле идентификатора. Свойства зависимостей может использоваться только <xref:System.Windows.DependencyObject> типов, но <xref:System.Windows.DependencyObject> находится достаточно высоко в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] иерархии классов, поэтому большинство классов, доступных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] могут поддерживать свойства зависимостей. Дополнительные сведения о свойствах зависимостей и некоторых терминах и соглашениях, используемых для их описания в этом [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)], см. в разделе [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
<a name="example_dp"></a>   
## <a name="examples-of-dependency-properties"></a>Примеры свойств зависимостей  
 Примеры свойств зависимостей, которые реализованы на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] классы содержат <xref:System.Windows.Controls.Control.Background%2A> свойства <xref:System.Windows.FrameworkElement.Width%2A> свойство и <xref:System.Windows.Controls.TextBox.Text%2A> свойство многие другие. Каждое свойство зависимостей, предоставленных классом имеет соответствующее открытое статическое поле типа <xref:System.Windows.DependencyProperty> предоставляется для этого же класса. Это идентификатор для свойства зависимостей. Идентификатор именуется по следующему соглашению: имя свойства зависимостей, за которым следует строка `Property`. Например, соответствующий <xref:System.Windows.DependencyProperty> поле идентификатора для <xref:System.Windows.Controls.Control.Background%2A> свойство <xref:System.Windows.Controls.Control.BackgroundProperty>. Идентификатор хранит сведения о свойстве зависимостей, как он был зарегистрирован, и идентификатор имеет затем используется для других операций, включающих свойству зависимостей, например при вызове <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
 Как упоминалось в разделе [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md), все свойства зависимостей в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (за исключением наиболее присоединенных свойств) также являются свойствами [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] из-за реализации "оболочки". Таким образом, из кода можно получать или задавать свойства зависимостей путем вызова методов доступа [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], определяющих оболочки таким же образом, как и для других свойств [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Как получатель установленных свойств зависимостей, который не используется обычно <xref:System.Windows.DependencyObject> методы <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A>, которые являются точку подключения для основной системы свойств. Вместо этого существующую реализацию [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] уже будет вызван свойства <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> в `get` и `set` реализации оболочки свойства правильное использование поле идентификатора . При собственной реализации настраиваемого свойства зависимостей вы будете определять оболочку аналогичным образом.  
  
<a name="backing_with_dp"></a>   
## <a name="when-should-you-implement-a-dependency-property"></a>Почему требуется реализовывать свойство зависимостей?  
 При реализации свойства в классе, при условии, что класс является производным от <xref:System.Windows.DependencyObject>, вы можете зарезервировать свое свойство с <xref:System.Windows.DependencyProperty> идентификатор и, следовательно, чтобы сделать его свойством зависимостей. Назначение свойства свойством зависимостей не всегда требуется и не всегда уместно и зависит от конкретной ситуации. В некоторых случаях достаточно просто снабдить свойство закрытым полем. Тем не менее реализовать свойство как свойство зависимостей потребуется, если свойство должно поддерживать одну или несколько из следующих возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Требуется, чтобы свойство было задаваемым в стиле. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
-   Требуется, чтобы свойство поддерживало привязку данных. Дополнительные сведения о свойствах зависимостей привязки данных см. в разделе [Привязка свойств двух элементов управления](../../../../docs/framework/wpf/data/how-to-bind-the-properties-of-two-controls.md).  
  
-   Требуется, чтобы свойство было задаваемым с помощью динамической ссылки ресурса. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Требуется настроить автоматическое наследование значения свойства из родительского элемента в дереве элементов. В этом случае зарегистрировать в <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод, даже если также создать оболочку для свойства [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] доступа. Дополнительные сведения см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Требуется, чтобы свойство поддерживало анимацию. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Требуется, чтобы система свойств сообщала об изменении предыдущего значения свойства действиями, выполняемыми системой свойств, окружением или пользователем, или путем чтения и использования стилей. Используя метаданные свойства, свойство может указывать метод обратного вызова, который будет вызываться каждый раз, когда система свойств определит, что значение свойства было однозначно изменено. Связанным понятием является приведение значения свойства. Дополнительные сведения см. в разделе [Проверка и обратные вызовы свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
-   Требуется использовать установленные соглашения о метаданных, которые также используются процессами [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], такими как передача сведений о том, нужно ли системе макета перестраивать визуальные компоненты элемента при изменении значения свойства. Или требуется возможность использовать переопределения метаданных таким образом, чтобы производные классы могли изменять основанные на метаданных характеристики, такие как значение по умолчанию.  
  
-   Требуется, чтобы свойства пользовательского элемента управления получали поддержку [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], например редактирование окна **Свойства**. Дополнительные сведения см. в разделе [Общие сведения о разработке элемента управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Рекомендуется рассмотреть возможность реализации сценариев путем переопределения метаданных существующего свойства зависимостей, вместо реализации совершенно нового свойства. Практическая польза переопределения метаданных зависит от сценария и того, насколько этот сценарий схож с реализацией существующих свойств зависимостей и классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения о переопределении метаданных для существующих свойств см. в разделе [Метаданные свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="checklist"></a>   
## <a name="checklist-for-defining-a-dependency-property"></a>Контрольный список определения свойства зависимостей  
 Определение свойства зависимостей состоит из четырех различных понятий. Эти понятия не обязательно являются строгими этапами процедуры, так как некоторые из них в итоге объединяются в одну строку кода в реализации.  
  
-   (Необязательно.) Создайте метаданные для свойства зависимостей.  
  
-   Зарегистрируйте имя свойства в системе свойств, указав тип владельца и тип значения свойства. Также укажите метаданные свойства, если они используются.  
  
-   Определение <xref:System.Windows.DependencyProperty> идентификатор как `public` `static` `readonly` поля в типе владельца.  
  
-   Определите свойство-"оболочку" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], имя которого соответствует имени свойства зависимостей. Реализуйте методы доступа `get` и `set` свойства-"оболочки" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] для подключения к свойству зависимостей, которое оно поддерживает.  
  
<a name="registering"></a>   
### <a name="registering-the-property-with-the-property-system"></a>Регистрация свойства в системе свойств  
 Чтобы назначить свойство свойством зависимостей, необходимо зарегистрировать это свойство в таблице, обслуживаемой системой свойств, и предоставить ему уникальный идентификатор, используемый в качестве квалификатора для последующих операций системы свойств. Эти операции могут быть внутренними операциями или вашим собственным кодом, вызывающим систему свойств [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]. Чтобы зарегистрировать свойство, вызовите <xref:System.Windows.DependencyProperty.Register%2A> метода в теле класса (внутри класса, но за пределами определения членов). Поле идентификатора также обеспечивается <xref:System.Windows.DependencyProperty.Register%2A> вызова метода, как возвращаемое значение. Причина, <xref:System.Windows.DependencyProperty.Register%2A> вызов выполняется за пределами другой член определения — так, как использовать это возвращаемое значение для назначения и создания `public` `static` `readonly` поле типа <xref:System.Windows.DependencyProperty> как часть класса. Это поле становится идентификатором для вашего свойства зависимостей.  
  
 [!code-csharp[WPFAquariumSln#RegisterAG](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerag)]
 [!code-vb[WPFAquariumSln#RegisterAG](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerag)]  
  
<a name="nameconventions"></a>   
### <a name="dependency-property-name-conventions"></a>Соглашения об именовании свойств зависимостей  
 Существуют установленные соглашения об именовании, касающиеся свойств зависимостей, которым необходимо следовать, если ситуация не является исключительной.  
  
 Само свойство зависимости будет иметь базовое имя — «AquariumGraphic» пример, в котором указан в качестве первого параметра <xref:System.Windows.DependencyProperty.Register%2A>. Это имя должно быть уникальным в пределах каждого регистрирующего типа. Считается, что свойства зависимостей, наследуемые через базовые типы, уже являются частью регистрирующего типа: имена наследуемых свойств нельзя зарегистрировать повторно. Однако существует способ добавления класса как владельца свойства зависимостей даже в том случае, если это свойство зависимостей не наследуется. Дополнительные сведения см. в разделе [Метаданные свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 При создании поля идентификатора назовите это поле по зарегистрированному имени свойства, добавив суффикс `Property`. Это поле является идентификатором для свойства зависимостей, и он будет использоваться позже в качестве входных данных для <xref:System.Windows.DependencyObject.SetValue%2A> и <xref:System.Windows.DependencyObject.GetValue%2A> вызовы, вы создадите в оболочках, любые другие кода доступ к свойству для кода, любой внешний код доступа можно разрешить , с помощью системы свойств или потенциально с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессоров.  
  
> [!NOTE]
>  Определение свойства зависимостей в теле класса является обычной реализацией, однако его также можно определить в статическом конструкторе класса. Этот подход может оказаться целесообразным, если для инициализации свойства зависимостей требуется несколько строк кода.  
  
<a name="wrapper1"></a>   
### <a name="implementing-the-wrapper"></a>Реализация "оболочки"  
 Реализация программы-оболочки должна вызывать <xref:System.Windows.DependencyObject.GetValue%2A> в `get` реализации, и <xref:System.Windows.DependencyObject.SetValue%2A> в `set` реализацию (исходный вызов регистрации и поле показаны здесь слишком для ясности).  
  
 На все, кроме исключительных ситуаций реализации оболочки выполнять только <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> действия, соответственно. Причина этого обсуждается в разделе [Загрузка кода XAML и свойства зависимостей](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
 Все существующие открытые свойства зависимостей, предоставляемые для классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], используют эту простую модель реализации оболочки. Основные сложности обработки свойств зависимостей определяются наследуемым поведением системы свойств или реализацией через другие понятия, такие как приведение или обратные вызовы изменения свойства через метаданные свойства.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
 Опять же, с общепринятой практикой имя свойства программы-оболочки должен быть совпадает с именем, выбранным и заданным как первый параметр <xref:System.Windows.DependencyProperty.Register%2A> вызов, зарегистрировавшего свойство. Если свойство не следует соглашению, это не обязательно ведет к его неработоспособности, однако будет наблюдаться несколько серьезных проблем.  
  
-   Не будут работать определенные аспекты стилей и шаблонов.  
  
-   Большинство инструментов и конструкторов полагается на соглашения об именовании для правильной сериализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], а также для предоставления помощи разработчику на уровне свойств.  
  
-   Текущая реализация загрузчика [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] полностью обходит оболочки и основывается на соглашении об именовании при обработке значений атрибутов. Дополнительные сведения см. в разделе [Загрузка кода XAML и свойства зависимостей](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md).  
  
<a name="metadata"></a>   
### <a name="property-metadata-for-a-new-dependency-property"></a>Метаданные свойства для нового свойства зависимостей  
 При регистрации свойства зависимостей через систему свойств создается объект метаданных, который хранит характеристики свойства. Многие из этих характеристик имеют значения по умолчанию, которые устанавливаются, если оно регистрируется с простой подписи <xref:System.Windows.DependencyProperty.Register%2A>. Другие подписи <xref:System.Windows.DependencyProperty.Register%2A> позволяют указывать метаданные, требуемые при регистрации свойства. Как правило, метаданные, задаваемые для свойства зависимостей, предполагают предоставление значений по умолчанию, применяемых для новых экземпляров, которые используют свойство.  
  
 При создании свойства зависимостей, который существует на производный класс <xref:System.Windows.FrameworkElement>, можно использовать более специализированный класс метаданных <xref:System.Windows.FrameworkPropertyMetadata> вместо базового <xref:System.Windows.PropertyMetadata> класса. Конструктор <xref:System.Windows.FrameworkPropertyMetadata> класс имеет несколько сигнатур, где можно указать различные характеристики метаданных в сочетании. Если требуется указать только значение по умолчанию, используйте подпись, которая принимает один параметр типа <xref:System.Object>. Передайте этот параметр объекта как значение определенного типа по умолчанию для свойства (предоставленное значение по умолчанию должно быть типом, предоставленным как `propertyType` параметр в <xref:System.Windows.DependencyProperty.Register%2A> вызова).  
  
 Для <xref:System.Windows.FrameworkPropertyMetadata>, можно также указать флаги параметра метаданных для свойства. Эти флаги преобразуются в дискретные свойства в метаданных свойства после регистрации и используются для передачи определенных условных объектов в другие процессы, например в обработчик макетов.  
  
#### <a name="setting-appropriate-metadata-flags"></a>Задание соответствующих флагов метаданных  
  
-   Если свойство (или изменения его значения) влияет на [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], и в частности влияет как система макета следует размер или отрисовки элемента на странице задайте одно или несколько из следующих флагов: <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>, <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>.  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsMeasure>Указывает, что изменение этого свойства требуется изменение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] подготовки отчетов, где содержащийся объект может потребовать больше или меньше места в родительском элементе. Например, этот флаг следует задать для свойства "Ширина".  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsArrange>Указывает, что изменение этого свойства требуется изменение [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] подготовки отчетов, обычно не требует изменений в выделенном пространстве, но указания изменения положения в пространстве. Например, этот флаг следует задать для свойства "Выравнивание".  
  
    -   <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsRender>Указывает, что произошло некоторые изменения, не влияет на макет и масштаб, но требуют повторной визуализации. Примером будет свойство, изменяющее цвет существующего элемента, например "Фон".  
  
    -   Эти флаги часто используются в качестве протокола в метаданных для собственных реализаций переопределения системы свойств или обратных вызовов макета. Например, может потребоваться <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> обратного вызова, который будет вызывать <xref:System.Windows.UIElement.InvalidateArrange%2A> Если любое свойство экземпляра сообщает об изменении значения и имеет <xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> как `true` в своих метаданных.  
  
-   Некоторые свойства могут влиять на характеристики отрисовки содержащего их родительского элемента указанными выше способами и помимо изменений в обязательном размере, упомянутых выше. Например, <xref:System.Windows.Documents.Paragraph.MinOrphanLines%2A> свойства, используемого в модели потокового документа, где изменения этого свойства можно изменять общую визуализацию документа нефиксированного формата, содержащего абзац. Используйте <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentArrange> или <xref:System.Windows.FrameworkPropertyMetadataOptions.AffectsParentMeasure> для определения подобных случаев в своих свойствах.  
  
-   По умолчанию свойства зависимостей поддерживают привязку данных. Вы можете специально отключить привязку данных для случаев, когда отсутствует практический смысл в привязке данных или когда быстродействие в привязке данных для больших объектов становится проблемой.  
  
-   По умолчанию привязка данных <xref:System.Windows.Data.Binding.Mode%2A> для значений по умолчанию свойства зависимостей для <xref:System.Windows.Data.BindingMode.OneWay>. Можно всегда изменить привязки <xref:System.Windows.Data.BindingMode.TwoWay> каждого экземпляра привязки, Дополнительные сведения см. [указать направление привязки](../../../../docs/framework/wpf/data/how-to-specify-the-direction-of-the-binding.md). Но как автор свойство зависимостей, можно сделать свойство использовать <xref:System.Windows.Data.BindingMode.TwoWay> режима привязки по умолчанию. Примером существующего свойства зависимостей является <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A?displayProperty=nameWithType>; сценарий для этого свойства представляет <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> задание логики и композиции <xref:System.Windows.Controls.MenuItem> взаимодействовать с стиля темы по умолчанию. <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> Логику свойство изначально использует привязку данных для поддержания состояния этого свойства в соответствии с другими свойствами состояния и вызовы методов. Другим примером свойства, который привязывает <xref:System.Windows.Data.BindingMode.TwoWay> по умолчанию является <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>.  
  
-   Можно также включить наследование свойства в пользовательское свойство зависимостей, задав <xref:System.Windows.FrameworkPropertyMetadataOptions.Inherits> флаг. Наследование свойств удобно для ситуации, когда родительские и дочерние элементы имеют общее свойство и для дочерних элементов имеет смысл задать то же значение свойства, что и в родительском элементе. Примером наследуемого свойства является <xref:System.Windows.FrameworkElement.DataContext%2A>, который используется для привязки операций, чтобы включить важный скрипт основной подробности для представления данных. Делая <xref:System.Windows.FrameworkElement.DataContext%2A> наследуемые, любые дочерние элементы наследуют контекст данных также. Благодаря наследованию значения свойства вы можете указать контекст данных в корне приложения или страницы и вам не потребуется уточнять его для привязок во всех возможных дочерних элементах. <xref:System.Windows.FrameworkElement.DataContext%2A>также представляет собой хороший пример для иллюстрации того, что наследование переопределяет значение по умолчанию, но может всегда быть локально установлено для любого конкретного дочернего элемента. Дополнительные сведения см. в разделе [использовать шаблон «основной-подробности» с иерархическими данными](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md). Наследование значения свойства может влиять на производительность, и таким образом, его следует использовать с осторожностью. Дополнительные сведения см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Задать <xref:System.Windows.FrameworkPropertyMetadataOptions.Journal> флаг, указывающий, если свойство зависимостей определено или используется службами навигации ведения журнала. Например, <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A> свойство; любого элемента, выбранного в выделенной области элемента управления должны сохраняться при истории журналирования.  
  
<a name="RODP"></a>   
## <a name="read-only-dependency-properties"></a>Свойства зависимости "только для чтения"  
 Можно определить свойство зависимости, которое доступно только для чтения. Однако ситуации для такого использования немного отличаются, как и процедура регистрации свойства в системе свойств и предоставление идентификатора. Дополнительные сведения см. в разделе [Свойства зависимостей "только для чтения"](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md).  
  
<a name="CTDP"></a>   
## <a name="collection-type-dependency-properties"></a>Свойства зависимостей типа коллекция  
 Свойства зависимостей типа коллекции имеют некоторые дополнительные проблемы при реализации, которые необходимо учитывать. Подробности см. в разделе [Свойства зависимостей типа коллекции](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md).  
  
<a name="SecurityC"></a>   
## <a name="dependency-property-security-considerations"></a>Замечания по безопасности свойств зависимостей  
 Свойства зависимостей должны объявляться как открытые свойства. Поля идентификаторов свойств зависимостей должны объявляться как открытые статические поля. Даже при попытке объявить другие уровни доступа (например, защищенный) к свойству зависимостей всегда можно обращаться через идентификатор в сочетании с [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] системы свойств. Даже защищенное поле идентификатора потенциально доступно из-за определения отчетов, или значение метаданных [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] , являющихся частью системы свойств, таких как <xref:System.Windows.LocalValueEnumerator>. Дополнительные сведения см. в разделе [Безопасность свойств зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-security.md).  
  
<a name="DPCtor"></a>   
## <a name="dependency-properties-and-class-constructors"></a>Свойства зависимостей и конструкторы класса  
 Есть общий принцип в программировании управляемого кода (он часто принудительно применяется средствами анализа кода, такими как FxCop), подразумевающий, что конструкторы класса не должны вызывать виртуальные методы. Этот принцип обусловлен тем, что конструкторы могут быть вызваны в качестве базовой инициализации конструктора производного класса, а ввод виртуального метода через конструктор может произойти в состоянии неполной инициализации конструируемого экземпляра объекта. При наследовании из любого класса, который уже является производным от <xref:System.Windows.DependencyObject>, следует иметь в виду, что сама система свойств вызывает методы и предоставляют виртуальные методы для внутренних целей. Эти виртуальные методы являются частью служб системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Переопределение методов позволяет производным классам участвовать в определении значения. Чтобы избежать потенциальных проблем при инициализации среды выполнения, не задавайте значения свойств зависимостей в конструкторах классов (если только вы не следуете конкретному шаблону конструктора). Подробнее см. в разделе [Шаблоны безопасного конструктора для DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Метаданные свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Общие сведения о разработке элементов управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Свойства зависимостей типа коллекции](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)  
 [Безопасность свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-security.md)  
 [Загрузка кода XAML и свойства зависимостей](../../../../docs/framework/wpf/advanced/xaml-loading-and-dependency-properties.md)  
 [Шаблоны безопасного конструктора для DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
