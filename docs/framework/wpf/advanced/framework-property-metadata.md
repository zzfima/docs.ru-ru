---
title: Метаданные свойств среды
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: c08cf28880d86331e3b561f1749333d401ba903e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964207"
---
# <a name="framework-property-metadata"></a>Метаданные свойств среды
Параметры метаданных свойств среды сообщаются для свойств элементов объектов, которые, как считается, в архитектуре [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находятся на уровне среды WPF. Как правило, при проектировании на уровне платформы WPF такие функции, как отрисовка, привязка данных и уточнение системы свойств, обрабатываются [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API презентации и исполняемыми файлами. Метаданные свойств среды запрашиваются этими системами для определения функциональных характеристик конкретных свойств элемента.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Вам следует также ознакомиться с разделом [Метаданные свойства зависимости](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Передаваемые сведения в метаданных свойств среды  
 Метаданные свойств среды можно разделить на следующие категории.  
  
- Свойства макета отчетности, влияющие на элемент<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>( <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>,). Вы можете установить эти флаги в метаданных, если свойство влияет на соответствующие аспекты, а также реализует <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы в классе, чтобы предоставить макету определенное поведение отрисовки и информацию. системой. Как правило, такая реализация проверяет аннулирование свойств в свойствах зависимости, где любое из этих свойств макета имело в метаданных свойств значение true, и только для таких аннулирований необходимо запросить новый проход макета.  
  
- Свойства макета отчетности, влияющие на родительский элемент элемента (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). В некоторых примерах по умолчанию <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> для этих флагов заданы значения и. <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. По умолчанию свойства зависимости не наследуют значения. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>позволяет также передавать пути наследования в визуальное дерево, которое необходимо для некоторых сценариев компоновки элементов управления.  
  
    > [!NOTE]
    > Термин "наследует" в контексте значений свойств имеет особое значение для свойств зависимостей; это означает, что дочерние элементы могут наследовать фактическое значение свойства зависимости от родительских элементов (это обусловлено возможностью системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на уровне среды WPF). Это не имеет ничего общего непосредственно с типом управляемого кода и наследованием элементов через производные типы. Подробнее см. в разделе [Наследование значения свойства](property-value-inheritance.md).  
  
- Характеристики привязки данных отчетов (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). По умолчанию свойства зависимости в среде поддерживают привязку данных с односторонним поведением привязки. Вы можете отключить привязку данных, если в ней нет какого-либо сценария (поскольку они должны быть гибкими и расширяемыми, в API-интерфейсах по умолчанию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не много примеров таких свойств). Вы можете задать для привязки свойство двустороннее по умолчанию для свойств, которые связывают поведение элемента управления с его компонентами (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> например,) или где двусторонняя привязка является общим и ожидаемым сценарием для пользователей (<xref:System.Windows.Controls.TextBox.Text%2A> например,). Изменение метаданных, связанных с привязкой данных, влияет только на значение по умолчанию; на уровне отдельных привязок это значение по умолчанию всегда можно изменить. Сведения о режимах связывания и связывании в целом см. в разделе [Общие сведения о связывании данных](../data/data-binding-overview.md).  
  
- Сообщает, должны ли свойства заноситься в журнал приложениями или службами, которые поддерживают<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>ведение журнала (). Для общих элементов ведение журнала не включено по умолчанию, но оно выборочно включается для некоторых пользовательских элементов управления вводом. Это свойство предназначено для прочтения службами ведения журнала, включая реализацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ведения журнала, и обычно устанавливается для пользовательских элементов управления, таких как пользовательский выбор в списках, который необходимо сохранять на протяжении нескольких шагов навигации. Сведения о журнале см. в разделе [Общие сведения о навигации](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Чтение FrameworkPropertyMetadata  
 Каждое из свойств, связанных выше, является конкретными свойствами, <xref:System.Windows.FrameworkPropertyMetadata> которые добавляет к его немедленному <xref:System.Windows.UIPropertyMetadata>базовому классу. Каждое из этих свойств будет иметь значение `false` по умолчанию. Запрос метаданных для свойства, при котором важно знать значение этих свойств, должен попытаться привести возвращаемые метаданные в <xref:System.Windows.FrameworkPropertyMetadata>, а затем проверить значения отдельных свойств по мере необходимости.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Задание метаданных  
 При создании нового экземпляра метаданных для применения метаданных к новой регистрации свойства зависимости можно выбрать, какой класс метаданных использовать: базовый <xref:System.Windows.PropertyMetadata> или какой-либо производный класс, <xref:System.Windows.FrameworkPropertyMetadata>например. Как правило, следует использовать <xref:System.Windows.FrameworkPropertyMetadata>, особенно если свойство взаимодействует с системой свойств и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] такими функциями, как макет и привязка данных. Другим вариантом для более сложных сценариев является наследование от <xref:System.Windows.FrameworkPropertyMetadata> для создания собственного класса отчетов с метаданными с дополнительной информацией, переданной в ее членах. Или вы можете использовать <xref:System.Windows.PropertyMetadata> или <xref:System.Windows.UIPropertyMetadata> для обмена степенью поддержки функций вашей реализации.  
  
 Для существующих свойств (<xref:System.Windows.DependencyProperty.AddOwner%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> вызова) следует всегда переопределять тип метаданных, используемый исходной регистрацией.  
  
 При создании <xref:System.Windows.FrameworkPropertyMetadata> экземпляра существует два способа заполнения метаданных значениями для конкретных свойств, которые обмениваются характеристиками свойств платформы:  
  
1. Используйте сигнатуру `flags` конструктора, которая разрешает параметр. <xref:System.Windows.FrameworkPropertyMetadata> Этот параметр должен быть заполнен всеми нужными объединенными значениями <xref:System.Windows.FrameworkPropertyMetadataOptions> флагов перечисления.  
  
2. Используйте одну из подписей без `flags` параметра, а затем установите каждое логическое <xref:System.Windows.FrameworkPropertyMetadata> свойство `true` отчета в значение для каждого требуемого изменения характеристик. Если сделать это, необходимо настроить эти свойства до создания каких-либо элементов с этим свойством зависимости. Логические свойства доступны для чтения и записи, чтобы разрешить поведение, которое избегает параметра `flags` и все равно заполняет метаданные, однако метаданные необходимо эффективно паковать, прежде чем использовать свойство. Таким образом, попытка задать свойства после запроса метаданных будет недопустимой операцией.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Поведение слияния метаданных свойств среды  
 При переопределении метаданных свойств среды различные характеристики метаданных объединяются или заменяют друг друга.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>объединяется. При добавлении нового <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>ответный вызов сохраняется в метаданных. Если не указать <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> в переопределении, <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> значение будет выдвинуто как ссылка из ближайшего предка, указанного в метаданных.  
  
- Фактическое поведение системы свойств для <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> заключается в том, что реализации для всех владельцев метаданных в иерархии сохраняются и добавляются в таблицу с порядком выполнения в системе свойств, что обратные вызовы самого глубокого производного класса вызывается первым. Наследуемые обратные вызовы выполняются только один раз и считается, что они принадлежат классу, разместившему их в метаданных.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>заменяется. Если не указать <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> в переопределении, <xref:System.Windows.PropertyMetadata.DefaultValue%2A> значение берется из ближайшего предка, указанного в метаданных.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>реализации заменяются. При добавлении нового <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>ответный вызов сохраняется в метаданных. Если не указать <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> в переопределении, <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> значение будет выдвинуто как ссылка из ближайшего предка, указанного в метаданных.  
  
- Поведение системы свойств заключается в том, что <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> вызывается только в немедленных метаданных. Ссылки на другие <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> реализации в иерархии не сохраняются.  
  
- Флаги <xref:System.Windows.FrameworkPropertyMetadataOptions> перечисления объединяются в виде битовой операции OR.  Если указать <xref:System.Windows.FrameworkPropertyMetadataOptions>, то исходные параметры не будут перезаписаны.  Чтобы изменить параметр, установите соответствующее свойство для <xref:System.Windows.FrameworkPropertyMetadata>. Например, если <xref:System.Windows.FrameworkPropertyMetadata> исходный объект <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> задает флаг, его можно изменить, задав <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> для `false`значение.  
  
 Это поведение реализуется <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>и может быть переопределено в производных классах метаданных.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Метаданные свойства зависимостей](dependency-property-metadata.md)
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Пользовательские свойства зависимостей](custom-dependency-properties.md)
