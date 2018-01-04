---
title: "Метаданные свойств среды"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fec11a973572dce9e8d6f77bf65ce31ee77eb41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="framework-property-metadata"></a>Метаданные свойств среды
Параметры метаданных свойств среды сообщаются для свойств элементов объектов, которые, как считается, в архитектуре [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] находятся на уровне среды WPF. В целом привязка к уровню среды WPF подразумевает, что такие функции, как отрисовка, привязка данных и уточнение системных свойств, обрабатываются в презентации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] и исполняемых файлах. Метаданные свойств среды запрашиваются этими системами для определения функциональных характеристик конкретных свойств элемента.  
  
 
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Вам следует также ознакомиться с разделом [Метаданные свойства зависимости](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Передаваемые сведения в метаданных свойств среды  
 Метаданные свойств среды можно разделить на следующие категории.  
  
-   Передающие свойства макета, влияющие на элемент (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). Может устанавливать эти флаги в метаданных, если свойство влияет на соответствующие аспекты, а также при реализации <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> методы в классе для предоставления поведение визуализации и сведения о макете система. Как правило, такая реализация проверяет аннулирование свойств в свойствах зависимости, где любое из этих свойств макета имело в метаданных свойств значение true, и только для таких аннулирований необходимо запросить новый проход макета.  
  
-   Свойства макета, влияющие на родительским элементом для отчетов (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Вот несколько примеров, где эти флаги устанавливаются по умолчанию <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> и <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. По умолчанию свойства зависимости не наследуют значения. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>позволяет перемещать путь наследования по визуальному дереву, что необходимо для некоторых сценариев управления композиции.  
  
    > [!NOTE]
    >  Термин "наследует" в контексте значений свойств имеет особое значение для свойств зависимостей; это означает, что дочерние элементы могут наследовать фактическое значение свойства зависимости от родительских элементов (это обусловлено возможностью системы свойств [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] на уровне среды WPF). Это не имеет ничего общего непосредственно с типом управляемого кода и наследованием элементов через производные типы. Подробнее см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Передающие характеристики привязки данных (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). По умолчанию свойства зависимости в среде поддерживают привязку данных с односторонним поведением привязки. Привязку данных можно было бы отключить, если бы сценарий для нее отсутствовал в принципе (поскольку они должны быть гибкими и расширяемыми, однако примеров таких свойств в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] по умолчанию не много). Можно задать привязку для получения двусторонней привязки по умолчанию для свойств, которые связывают поведения элемента управления среди его компонентных составляющих (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> приведен пример) или где двусторонняя привязка является общим и ожидаемым скриптом для пользователей (<xref:System.Windows.Controls.TextBox.Text%2A> приведен пример). Изменение метаданных, связанных с привязкой данных, влияет только на значение по умолчанию; на уровне отдельных привязок это значение по умолчанию всегда можно изменить. Сведения о режимах связывания и связывании в целом см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Отчеты, должны ли свойства помещенные в журнал приложениями или службами, поддерживающими ведение журнала (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). Для общих элементов ведение журнала не включено по умолчанию, но оно выборочно включается для некоторых пользовательских элементов управления вводом. Это свойство предназначено для прочтения службами ведения журнала, включая реализацию [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ведения журнала, и обычно устанавливается для пользовательских элементов управления, таких как пользовательский выбор в списках, который необходимо сохранять на протяжении нескольких шагов навигации. Сведения о журнале см. в разделе [Общие сведения о навигации](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Чтение FrameworkPropertyMetadata  
 Каждый из вышеописанные свойства являются специальными свойствами, <xref:System.Windows.FrameworkPropertyMetadata> добавляет его непосредственно к базовому классу <xref:System.Windows.UIPropertyMetadata>. Каждое из этих свойств будет иметь значение `false` по умолчанию. Запрос метаданных для свойства, где важны значения этих свойств должен попытаться преобразовать возвращенные метаданные в <xref:System.Windows.FrameworkPropertyMetadata>, а затем при необходимости проверить значения отдельных свойств.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Задание метаданных  
 Когда вы создаете новый экземпляр метаданных в целях применения метаданных к новой регистрации свойства зависимостей, вы можете выбрать класс, который метаданных для использования: базовый <xref:System.Windows.PropertyMetadata> или некоторые производного класса, такие как <xref:System.Windows.FrameworkPropertyMetadata>. В общем случае следует использовать <xref:System.Windows.FrameworkPropertyMetadata>, особенно в том случае, если свойство взаимодействует с системой свойств и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функции, такие как макет и привязки данных. Другим вариантом в более сложных сценариях является наследование от <xref:System.Windows.FrameworkPropertyMetadata> для создания собственных метаданных reporting класса вместе с дополнительной информацией, передаваемое в его члены. Или же можно использовать <xref:System.Windows.PropertyMetadata> или <xref:System.Windows.UIPropertyMetadata> для связи степени поддержки для возможностей реализации.  
  
 Для существующих свойств (<xref:System.Windows.DependencyProperty.AddOwner%2A> или <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> вызова), следует всегда использовать переопределение с помощью типа метаданных, используемых исходной регистрации.  
  
 Если вы создаете <xref:System.Windows.FrameworkPropertyMetadata> экземпляра, существует два способа для заполнения метаданных значениями для определенных свойств, которые взаимодействуют с характеристиками свойств среды:  
  
1.  Используйте <xref:System.Windows.FrameworkPropertyMetadata> сигнатуры конструктора, который позволяет `flags` параметра. Этот параметр должен быть заполнен всеми нужными комбинированных значений из <xref:System.Windows.FrameworkPropertyMetadataOptions> флаги перечисления.  
  
2.  Использование одной из сигнатур без `flags` параметра и задание каждого предоставляемого логического свойства для <xref:System.Windows.FrameworkPropertyMetadata> для `true` для каждого нужного изменения характеристик. Если сделать это, необходимо настроить эти свойства до создания каких-либо элементов с этим свойством зависимости. Логические свойства доступны для чтения и записи, чтобы разрешить поведение, которое избегает параметра `flags` и все равно заполняет метаданные, однако метаданные необходимо эффективно паковать, прежде чем использовать свойство. Таким образом, попытка задать свойства после запроса метаданных будет недопустимой операцией.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Поведение слияния метаданных свойств среды  
 При переопределении метаданных свойств среды различные характеристики метаданных объединяются или заменяют друг друга.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>объединяются. При добавлении нового <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, ответного вызова хранится в метаданных. Если вы не укажете <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> при переопределении значения <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> переходит в качестве ссылки из ближайшего родительского объекта, указанного в метаданных.  
  
-   Фактическое поведение системы свойств для <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> том, что реализации для всех владельцев метаданных в иерархии сохраняются и добавляются в таблицу в порядке выполнения системой свойств выполняется, обратные вызовы наиболее глубоко производного класса, Сначала вызывается. Наследуемые обратные вызовы выполняются только один раз и считается, что они принадлежат классу, разместившему их в метаданных.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A>заменяется. Если вы не укажете <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> при переопределении значения <xref:System.Windows.PropertyMetadata.DefaultValue%2A> поступают из ближайшего родительского объекта, указанного в метаданных.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>реализации заменяются. При добавлении нового <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, ответного вызова хранится в метаданных. Если вы не укажете <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> при переопределении значения <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> переходит в качестве ссылки из ближайшего родительского объекта, указанного в метаданных.  
  
-   Поведение системы свойств только в том случае, <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> вызывается в интерпретации метаданных. Ссылки на другие <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> сохраняются реализации в иерархии.  
  
-   Флаги <xref:System.Windows.FrameworkPropertyMetadataOptions> перечисления, объединяются в виде битовой операции OR.  При указании <xref:System.Windows.FrameworkPropertyMetadataOptions>, первоначальные значения параметров, не перезаписываются.  Чтобы изменить параметр, установите соответствующее свойство на <xref:System.Windows.FrameworkPropertyMetadata>. Например если исходный <xref:System.Windows.FrameworkPropertyMetadata> набора объектов <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> флаг, можно изменить, задав <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> для `false`.  
  
 Это поведение реализуется <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>и могут переопределяться в производных классах метаданных.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>  
 [Метаданные свойства зависимостей](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
