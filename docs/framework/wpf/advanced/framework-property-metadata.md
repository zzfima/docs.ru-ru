---
title: "Метаданные свойств среды | Microsoft Docs"
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
  - "метаданные свойств платформы"
  - "метаданные, свойства платформы"
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Метаданные свойств среды
Параметры метаданных свойств среды выводятся для свойств объектных элементов, которые находятся на [уровне среды WPF](GTMT) в архитектуре [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В общем, обозначение [уровень среды WPF](GTMT) означает, что такие возможности, как отрисовка, привязка данных и уточнения системы свойств, обрабатываются [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] представлением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и исполняемыми файлами.  Метаданные свойств среды запрашиваются этими системами для определения зависимых от свойств характеристик конкретных свойств элементов.  
  
   
  
<a name="prerequisites"></a>   
## Предварительные требования  
 Этот раздел предполагает понимание [свойств зависимости](GTMT) с точки зрения пользователя существующих свойств зависимости для классов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и предварительное прочтение раздела [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Также необходимо ознакомиться с [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## Передаваемые сведения в метаданных свойств среды  
 Метаданные свойств среды можно разделить на следующие категории:  
  
-   Передающие свойства макета, влияющие на элемент \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>\).  Можно задать эти флаги в метаданных, если свойство влияет на соответствующие аспекты, а также при реализации методов <xref:System.Windows.FrameworkElement.MeasureOverride%2A> \/ <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> в классе для предоставления определенного поведения и данных отрисовки системе макета.  Обычно такая реализация проверяет аннулирование свойств в свойствах зависимости, где любое из этих свойств макета имеет значение true в метаданных свойств, и только такое аннулирование потребует нового прохода разметки.  
  
-   Передающие свойства макета, влияющие на родительский элемент элемента \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>\).  Примеры, в которых эти флаги задаются по умолчанию: <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=fullName> и <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=fullName>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>.  По умолчанию свойства зависимостей не наследуют значения.  <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> позволяет перемещать путь наследования по визуальному дереву, что необходимо в некоторых сценариях создания элементов управления.  
  
    > [!NOTE]
    >  Термин «наследует» в контексте значений свойств имеет особое значение для свойств зависимости; это означает, что дочерние элементы могут наследовать текущее значение свойства зависимости от родительских элементов из\-за возможностей системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на [уровне среды WPF](GTMT).  Он ничего не делает непосредственно с типом управляемого кода и наследованием членов при помощи производных типов.  Дополнительные сведения см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Передающие характеристики привязки данных \(<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>\).  По умолчанию свойства зависимости в среде поддерживают привязку данных с поведением односторонней привязки.  Можно отключить привязку данных, если для нее не существует каких\-либо скриптов \(поскольку они предназначены для гибкости и расширяемости, существует лишь небольшое количество примеров таких свойств в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] по умолчанию\).  Можно установить привязку для получения двусторонней привязки по умолчанию для свойств, связывающих вместе модели поведения элемента управления среди его компонентных составляющих \(например, <xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A>\), или там, где двусторонняя привязка является общим и ожидаемым скриптом для пользователей \(например, <xref:System.Windows.Controls.TextBox.Text%2A>\).  Изменение метаданных, связанных с привязкой данных, влияет только на значение по умолчанию. Это значение по умолчанию всегда можно изменять по отдельности для каждой привязки.  Дополнительные сведения о режимах привязки и о привязке в целом см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Передающие сведения о том, должны ли свойства заноситься в журнал приложениями или службами, поддерживающими ведение журнала \(<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>\).  Для общих элементов ведение журнала не включено по умолчанию, но оно выборочно включается для некоторых пользовательских элементов управления ввода.  Это свойство предназначено для прочтения службами ведения журнала, в том числе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализацией ведения журнала, и обычно устанавливается для пользовательских элементов управления, таких как пользовательский выбор в списке, который должен сохраняться при переходах.  Дополнительные сведения о журналах см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## Чтение FrameworkPropertyMetadata  
 Все вышеописанные свойства являются специальными свойствами, которые <xref:System.Windows.FrameworkPropertyMetadata> добавляют непосредственно в свой базовый класс <xref:System.Windows.UIPropertyMetadata>.  Каждое из этих свойств будет иметь значение `false` по умолчанию.  Запрос метаданных для свойства, для которого важны значения этих свойств, должен попытаться преобразовать возвращенные метаданные в <xref:System.Windows.FrameworkPropertyMetadata>, а затем при необходимости проверить значения отдельных свойств.  
  
<a name="Specifying_Metadata"></a>   
## Задание Метаданных  
 При создании нового экземпляра метаданных в целях применения метаданных при регистрации нового свойства зависимости имеется выбор используемого класса метаданных: базовый <xref:System.Windows.PropertyMetadata> или несколько производных классов, например, <xref:System.Windows.FrameworkPropertyMetadata>.  В общем случае, следует использовать <xref:System.Windows.FrameworkPropertyMetadata>, особенно если свойство взаимодействует с системой свойств и функциями [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], например, с макетом и привязкой данных.  Другим вариантом в более сложных сценариях является наследование от <xref:System.Windows.FrameworkPropertyMetadata> для создания собственного класса передачи метаданных с переносом дополнительных сведений в членах класса.  Для связи степени поддержки для возможностей реализации можно использовать <xref:System.Windows.PropertyMetadata> или <xref:System.Windows.UIPropertyMetadata>.  
  
 Для существующих свойств \(вызов <xref:System.Windows.DependencyProperty.AddOwner%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>\) следует всегда использовать переопределение с помощью типа метаданных, используемого в исходной регистрации.  
  
 Если создается экземпляр <xref:System.Windows.FrameworkPropertyMetadata>, существует два способа заполнения метаданных значениями для определенных свойств, которые взаимодействуют с характеристиками свойств среды:  
  
1.  Использование сигнатуры конструктора <xref:System.Windows.FrameworkPropertyMetadata>, допускающей параметр `flags`.  Этот параметр должен быть заполнен всеми нужными комбинированных значений флагов перечисления <xref:System.Windows.FrameworkPropertyMetadataOptions>.  
  
2.  Использование сигнатур без параметра `flags` и задание каждого предоставляемого логического свойства для <xref:System.Windows.FrameworkPropertyMetadata> значением `true` для каждого нужного изменения характеристик.  Если выполнить это, необходимо задать эти свойства перед созданием каких\-либо элементов с этим свойством зависимости; логические свойства являются свойствами, доступными для чтения и записи, что позволяет реализовать подобное поведение и по\-прежнему заполнять метаданные с избежанием параметра `flags`, но метаданные должны быть эффективно упакованы перед использованием свойств.  Таким образом, попытка задать свойства после запроса метаданных будет недопустимой операцией.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## Поведение слияния метаданных свойств среды  
 При переопределении метаданных свойств среды различные характеристики метаданных либо сливаются, либо заменяются.  
  
-   Объект <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> объединяется.  Если добавить новый обратный вызов <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, он сохранится в метаданных.  Если в переопределении не указан обратный вызов <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, значение <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> переходит в качестве ссылки из ближайшего родительского объекта, указанного в метаданных.  
  
-   Фактическое поведение системы свойств <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> заключается в том, что реализации для всех владельцев метаданных в иерархии сохраняются и добавляются в таблицу в порядке выполнения системой свойств \(сначала вызывается большинство обратных вызовов производного класса\).  Наследуемые обратные вызовы запускаются только один раз и считаются принадлежащими классу, которые поместил их в метаданные.  
  
-   Объект <xref:System.Windows.PropertyMetadata.DefaultValue%2A> заменяется.  Если в переопределении не указан обратный вызов <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, значение <xref:System.Windows.PropertyMetadata.DefaultValue%2A> переходит из ближайшего родительского объекта, указанного в метаданных.  
  
-   Реализации <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> заменяются.  Если добавить новый обратный вызов <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, он сохранится в метаданных.  Если в переопределении не указан обратный вызов <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, значение <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> переходит в качестве ссылки из ближайшего родительского объекта, указанного в метаданных.  
  
-   Поведение системы свойств состоит в том, что только <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> вызывается непосредственно из метаданных.  Ссылки на другие реализации <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> в иерархии не сохраняются.  
  
-   Флаги перечисления <xref:System.Windows.FrameworkPropertyMetadataOptions> объединяются посредством битовой операции ИЛИ.  Если указать параметры <xref:System.Windows.FrameworkPropertyMetadataOptions>, исходные параметры не перезаписываются.  Чтобы изменить параметр, установите соответствующее свойство в объекте <xref:System.Windows.FrameworkPropertyMetadata>.  Например, если исходный объект <xref:System.Windows.FrameworkPropertyMetadata> устанавливает флаг <xref:System.Windows.FrameworkPropertyMetadataOptions?displayProperty=fullName>, то его можно изменить, установив свойство <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=fullName> в значение `false`.  
  
 Это правило реализовано в классе <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A> и может быть переопределено в производных классах метаданных.  
  
## См. также  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>   
 [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)