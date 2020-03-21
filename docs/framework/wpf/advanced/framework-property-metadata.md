---
title: Метаданные свойств среды
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 8fb6e1b4cf6aed9454e9e9f1a77277d2f3611ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186652"
---
# <a name="framework-property-metadata"></a>Метаданные свойств среды
Параметры метаданных свойств среды сообщаются для свойств элементов объектов, которые, как считается, в архитектуре [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находятся на уровне среды WPF. В целом обозначение на уровне рамочной системы WPF предполагает, что такие функции, как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] рендеринг, привязка данных и уточнения системы свойств, обрабатываются с помощью aIS-аПО и исполнителей презентации. Метаданные свойств среды запрашиваются этими системами для определения функциональных характеристик конкретных свойств элемента.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Вам следует также ознакомиться с разделом [Метаданные свойства зависимости](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>Передаваемые сведения в метаданных свойств среды  
 Метаданные свойств среды можно разделить на следующие категории.  
  
- Свойства макета отчетности,<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>влияющие на элемент (, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>). <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A> Вы можете установить эти флаги в метаданных, если свойство влияет <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> на эти соответствующие аспекты, и вы также реализуете методы в вашем классе для предоставления определенного поведения рендеринга и информации в систему макета. Как правило, такая реализация проверяет аннулирование свойств в свойствах зависимости, где любое из этих свойств макета имело в метаданных свойств значение true, и только для таких аннулирований необходимо запросить новый проход макета.  
  
- Свойства макета отчетности, влияющие на<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>родительский элемент элемента (, ). Некоторые примеры, когда эти <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> флаги установлены по умолчанию и <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. По умолчанию свойства зависимости не наследуют значения. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>позволяет путь наследования также путешествовать в визуальное дерево, которое необходимо для некоторых сценариев композиций управления.  
  
    > [!NOTE]
    > Термин "наследует" в контексте значений свойств имеет особое значение для свойств зависимостей; это означает, что дочерние элементы могут наследовать фактическое значение свойства зависимости от родительских элементов (это обусловлено возможностью системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на уровне среды WPF). Это не имеет ничего общего непосредственно с типом управляемого кода и наследованием элементов через производные типы. Для получения подробной информации [см.](property-value-inheritance.md)  
  
- Характеристики связывания данных (,<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>). <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A> По умолчанию свойства зависимости в среде поддерживают привязку данных с односторонним поведением привязки. Вы можете отключить привязку данных, если для нее не было сценария (поскольку они предназначены для гибкого [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и расширяемого характера, в AIS по умолчанию не так много примеров таких свойств). Можно установить привязку к двустороннему по умолчанию для свойств, которые связывают<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> поведение элемента управления между его компонентами (является примером) или когда двусторонняя привязка является общим и ожидаемым сценарием для пользователей (является<xref:System.Windows.Controls.TextBox.Text%2A> примером). Изменение метаданных, связанных с привязкой данных, влияет только на значение по умолчанию; на уровне отдельных привязок это значение по умолчанию всегда можно изменить. Сведения о режимах связывания и связывании в целом см. в разделе [Общие сведения о связывании данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Сообщение о том, следует ли вести журналы<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>по приложениям или службам, поддерживающим журналирование (). Для общих элементов ведение журнала не включено по умолчанию, но оно выборочно включается для некоторых пользовательских элементов управления вводом. Это свойство предназначено для прочтения службами ведения журнала, включая реализацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ведения журнала, и обычно устанавливается для пользовательских элементов управления, таких как пользовательский выбор в списках, который необходимо сохранять на протяжении нескольких шагов навигации. Сведения о журнале см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>Чтение FrameworkPropertyMetadata  
 Каждый из свойств, связанных выше, являются специфическими свойствами, которые <xref:System.Windows.FrameworkPropertyMetadata> добавляет к его непосредственной базовой категории. <xref:System.Windows.UIPropertyMetadata> Каждое из этих свойств будет иметь значение `false` по умолчанию. Запрос метаданных для свойства, где знание значения этих свойств имеет важное значение, должен попытаться бросить возвращенные метаданные <xref:System.Windows.FrameworkPropertyMetadata>в, а затем проверить значения отдельных свойств по мере необходимости.  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>Задание метаданных  
 При создании нового экземпляра метаданных для целей применения метаданных к новой регистрации собственности зависимости у вас <xref:System.Windows.PropertyMetadata> есть выбор, который <xref:System.Windows.FrameworkPropertyMetadata>класс метаданных использовать: базовый или некоторый производный класс, например . Как правило, вы <xref:System.Windows.FrameworkPropertyMetadata>должны использовать, особенно если ваша [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] собственность имеет какое-либо взаимодействие с системой свойств и такими функциями, как макет и привязка данных. Другой вариант для более сложных <xref:System.Windows.FrameworkPropertyMetadata> сценариев заключается в том, чтобы извлечь из создания собственного класса отчетности метаданных с дополнительной информацией, перевозимых в его членов. Или вы <xref:System.Windows.PropertyMetadata> можете <xref:System.Windows.UIPropertyMetadata> использовать или сообщить степень поддержки функций вашей реализации.  
  
 Для существующих<xref:System.Windows.DependencyProperty.AddOwner%2A> свойств <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> (или вызова) всегда следует переопределить тип метаданных, используемый в первоначальной регистрации.  
  
 При создании экземпляра <xref:System.Windows.FrameworkPropertyMetadata> существует два способа заполнения метаданных значениями для конкретных свойств, связывающих характеристики свойств фреймворка:  
  
1. Используйте <xref:System.Windows.FrameworkPropertyMetadata> подпись конструктора, `flags` которая позволяет параметр. Этот параметр должен быть заполнен всеми <xref:System.Windows.FrameworkPropertyMetadataOptions> желаемыми комбинированными значениями флагов перечисления.  
  
2. Используйте одну из `flags` подписей без параметра, а <xref:System.Windows.FrameworkPropertyMetadata> затем `true` установите каждое свойство boolean отчетности на каждое желаемое характерное изменение. Если сделать это, необходимо настроить эти свойства до создания каких-либо элементов с этим свойством зависимости. Логические свойства доступны для чтения и записи, чтобы разрешить поведение, которое избегает параметра `flags` и все равно заполняет метаданные, однако метаданные необходимо эффективно паковать, прежде чем использовать свойство. Таким образом, попытка задать свойства после запроса метаданных будет недопустимой операцией.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>Поведение слияния метаданных свойств среды  
 При переопределении метаданных свойств среды различные характеристики метаданных объединяются или заменяют друг друга.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>сливается. Если вы добавите новый, <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>то обратный вызов хранится в метаданных. Если вы не <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> указали в переопределении, значение повышается как ссылка от ближайшего <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> предка, который указал его в метаданных.  
  
- Фактическое поведение системы свойств для <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> того, чтобы реализации для всех владельцев метаданных в иерархии сохранялись и добавлялись в таблицу, при этом порядок выполнения системой свойств в том, что сначала ссылаются обратные вызовы наиболее глубоко производного класса. Наследуемые обратные вызовы выполняются только один раз и считается, что они принадлежат классу, разместившему их в метаданных.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>заменяется. Если вы не <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> укажете в переопределении, значение исходит от ближайшего <xref:System.Windows.PropertyMetadata.DefaultValue%2A> предка, который указал его в метаданных.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>реализации заменяются. Если вы добавите новый, <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>то обратный вызов хранится в метаданных. Если вы не <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> указали в переопределении, значение повышается как ссылка от ближайшего <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> предка, который указал его в метаданных.  
  
- Поведение системы свойств заключается в том, что вызывается только <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> в непосредственных метаданных. Ссылки на <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> другие реализации в иерархии не сохраняются.  
  
- Флаги <xref:System.Windows.FrameworkPropertyMetadataOptions> перечисления объединяются как bitwise или операции.  Если указать, <xref:System.Windows.FrameworkPropertyMetadataOptions>исходные параметры не перезаписаны.  Чтобы изменить опцион, установите <xref:System.Windows.FrameworkPropertyMetadata>соответствующее свойство на . Например, если <xref:System.Windows.FrameworkPropertyMetadata> исходный <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> объект устанавливает флаг, его <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> `false`можно изменить, установив на .  
  
 Это поведение <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>реализуется, и может быть переопределено на производных классах метаданных.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Метаданные свойства зависимости](dependency-property-metadata.md)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
