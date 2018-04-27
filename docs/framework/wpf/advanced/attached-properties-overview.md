---
title: Общие сведения о вложенных свойствах зависимостей
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ceba94d80ca66ab228804ffff2a5b8f89a68d7c4
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="attached-properties-overview"></a>Общие сведения о вложенных свойствах зависимостей
Присоединенное свойство — это понятие, определяемое языком XAML. Присоединенное свойство предназначено для использования в качестве типа глобального свойства, которое может быть задано для любого объекта. В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] присоединенные свойства обычно определяются как особая форма свойства зависимости, не имеющего обычной "оболочки" свойства.  
  
   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы имеете представление о свойствах зависимостей с точки зрения потребителя существующих свойств зависимостей в классах [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и ознакомились с разделом [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Чтобы выполнить примеры в этом разделе, следует также иметь представление о XAML и написании простых приложений [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="attached_properties_usage"></a>   
## <a name="why-use-attached-properties"></a>Преимущества присоединенных свойств  
 Среди прочего, присоединенные свойства позволяют разным дочерним элементам задавать уникальные значения для свойства, которое фактически определено в родительском элементе. Конкретным примером этого сценария является уведомление дочерними элементами родительского элемента о порядке их представления в [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Одним из примеров является <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> свойства. <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Свойство создается как вложенное свойство, поскольку он разработан для элементов, содержащихся в <xref:System.Windows.Controls.DockPanel>, а не на <xref:System.Windows.Controls.DockPanel> сам. <xref:System.Windows.Controls.DockPanel> Класс определяет статические <xref:System.Windows.DependencyProperty> поле с именем <xref:System.Windows.Controls.DockPanel.DockProperty>, а затем предоставляет <xref:System.Windows.Controls.DockPanel.GetDock%2A> и <xref:System.Windows.Controls.DockPanel.SetDock%2A> методы как открытые методы доступа для вложенных свойств.  
  
<a name="attached_properties_xaml"></a>   
## <a name="attached-properties-in-xaml"></a>Присоединенные свойства в XAML  
 В XAML присоединенные свойства задаются с помощью синтаксиса *ПоставщикПрисоединенногоСвойства*.*ИмяСвойства*.  
  
 Ниже приведен пример, как можно задать <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> в XAML:  
  
 [!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 Обратите внимание, что использование похож на статическое свойство; всегда используется ссылка на тип <xref:System.Windows.Controls.DockPanel> , является владельцем и регистрирует присоединенное свойство, а не ссылка на экземпляр по указанному имени.  
  
 Кроме того, поскольку присоединенное свойство в XAML является атрибутом, который устанавливается в разметке, операция задания является значимой. Нельзя напрямую получить свойство в XAML, хотя существуют некоторые косвенные механизмы для сравнения значений, такие как триггеры в стилях (подробнее см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)).  
  
### <a name="attached-property-implementation-in-wpf"></a>Реализация присоединенного свойства в WPF  
 В [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] большинство присоединенных свойств, существующих в типах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которые связаны с представлением пользовательского интерфейса, реализуются как свойства зависимости. Присоединенные свойства являются понятием XAML, тогда как свойства зависимости являются понятием [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Поскольку присоединенные свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются свойствами зависимостей, они поддерживают понятия свойств зависимости, такие как метаданные свойства и значения по умолчанию из этих метаданных свойства.  
  
<a name="howused"></a>   
## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Как присоединенные свойства используются типом владельца  
 Хотя присоединенные свойства могут устанавливаться для любого объекта, это не означает, что задание свойства будет создавать осязаемый результат или что значение будет когда-либо использоваться другим объектом. Как правило, использование присоединенных свойств подразумевает, что объекты, поступающие из разнообразных иерархий классов или логических связей, могут передавать общую информацию в тип, который определяет присоединенное свойство. Тип, который определяет присоединенное свойство, обычно соответствует одной из следующих моделей.  
  
-   Тип, который определяет присоединенное свойство, может являться родительским элементом для элементов, которые будут задавать значения для присоединенного свойства. Тип, который затем выполняет итерацию его дочерних объектов согласно внутренней логике относительно некоторой структуры дерева объектов, получает значения и выполняет с этими значениями какие-либо действия.  
  
-   Тип, который определяет присоединенное свойство, будет использоваться в качестве дочернего элемента для разнообразных возможных родительских элементов и моделей содержимого.  
  
-   Тип, который определяет присоединенное свойство, представляет службу. Другие типы устанавливают значения для присоединенного свойства. Затем, когда элемент, задающий свойство, вычисляется в контексте службы, значения присоединенного свойства получаются через внутреннюю логику класса службы.  
  
### <a name="an-example-of-a-parent-defined-attached-property"></a>Пример присоединенного свойства, определенного родительским элементом  
 Наиболее типичный сценарий, в котором [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет присоединенное свойство, — когда родительский элемент поддерживает коллекцию дочерних элементов, а также реализует поведение, для которого особенности поведения передаются отдельно для каждого дочернего элемента.  
  
 <xref:System.Windows.Controls.DockPanel> Определяет <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> вложенное свойство зависимостей, и <xref:System.Windows.Controls.DockPanel> имеет код уровня класса как часть логики отрисовки (в частности, <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> и <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Объект <xref:System.Windows.Controls.DockPanel> экземпляр будет всегда проверять ли все его непосредственные дочерние элементы задано значение для <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. В таком случае эти значения становятся входными данными для логики отображения, применяемой к соответствующему дочернему элементу. Вложенные <xref:System.Windows.Controls.DockPanel> экземпляров каждого обрабатывать свои собственные коллекции непосредственных дочерних элементов, но это поведение зависит от реализации на то, как <xref:System.Windows.Controls.DockPanel> процессов <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> значения. Теоретически возможно наличие присоединенных свойств, оказывающих влияние на элементы за пределами непосредственного родителя. Если <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> вложенное свойство установлено для элемента, который не имеет <xref:System.Windows.Controls.DockPanel> возникает родительского элемента для обработки его, ошибка или исключение. Это просто означает, что было задано значение глобального свойства, но оно не имеет текущего <xref:System.Windows.Controls.DockPanel> родителя, который может использовать эту информацию.  
  
<a name="attached_properties_code"></a>   
## <a name="attached-properties-in-code"></a>Присоединенные свойства в коде  
 Присоединенные свойства в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не имеют обычных методов "оболочки" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] для простого получения и задания. Это происходит потому, что присоединенное свойство не обязательно входит в пространство имен [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] для экземпляров, в которых задано это свойство. Тем не менее обработчик XAML должен иметь возможность задавать эти значения при анализе XAML. Для поддержки эффективного использования присоединенных свойств тип владельца присоединенного свойства должен реализовывать специальные методы доступа в форме `Get`*ИмяСвойства* и `Set`*ИмяСвойства*. Такие специальные методы доступа также удобны для получения или задания присоединенного свойства в коде. С точки зрения кода присоединенное свойство аналогично резервному полю с методами доступа к методам вместо методов доступа к свойствам. Такое резервное поле может существовать для любого объекта и не требует специального определения.  
  
 В следующем примере кода показано задание присоединенного свойства в коде. В этом примере `myCheckBox` является экземпляром класса <xref:System.Windows.Controls.CheckBox> класса.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 Регистр аналогична XAML, если `myCheckBox` уже не были добавлены как дочерний элемент элемента `myDockPanel` в третьей строке кода, Четвертая строка кода не приведет к исключению, но значение свойства не будет взаимодействовать с <xref:System.Windows.Controls.DockPanel> родительского и, следовательно, ничего не будет делать. Только <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> заданное для дочернего элемента, в сочетании с наличием <xref:System.Windows.Controls.DockPanel> родительского элемента будет влиять на поведение в отображаемом приложении. (В этом случае вы может задать присоединенное свойство, а затем подключиться к дереву. Аналогично, можно подключиться к дереву, а затем задать присоединенное свойство. Любая последовательность действий дает тот же результат.)  
  
<a name="attached_properties_metadata"></a>   
## <a name="attached-property-metadata"></a>Метаданные присоединенного свойства  
 При регистрации свойства <xref:System.Windows.FrameworkPropertyMetadata> определяет характеристики свойства, например, является ли свойство влияет на отрисовку, размеры и т. д. Метаданные для присоединенного свойства, как правило, не отличаются от задаваемых для свойства зависимостей. Если задать значение по умолчанию в переопределении для метаданных присоединенного свойства, это значение становится значением по умолчанию неявного присоединенного свойства для экземпляров переопределяющего класса. В частности, значение по умолчанию передается, если некоторый процесс запрашивает значение присоединенного свойства с помощью метода доступа `Get` для этого свойства, указывая экземпляр класса, в котором заданы метаданные, и значение для этого присоединенного свойства не задано иным образом.  
  
 Если вы хотите разрешить наследование значений свойства, следует использовать присоединенные свойства, вместо неприсоединенных свойств зависимостей. Подробнее см. в разделе [Наследование значения свойства](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="custom"></a>   
## <a name="custom-attached-properties"></a>Настраиваемые присоединенные свойства  
  
<a name="create_attached_properties"></a>   
### <a name="when-to-create-an-attached-property"></a>Когда следует создавать присоединенное свойство  
 Присоединенное свойство можно создать, если требуется механизм задания свойств для классов, не являющихся определяющим классом. Наиболее распространенным сценарием является макет. Ниже приведены несколько существующих свойств макета <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, и <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. В этом сценарии элементы, которые существуют как дочерние элементы для элементов, управляющих макетом, могут индивидуально выражать требования макета для своих родительских элементов, задавая значение свойства, определяемого родительским элементом как присоединенное свойство.  
  
 Другой сценарий использования присоединенного свойства — когда класс представляет службу и требуется реализовать более прозрачную интеграцию службы классами.  
  
 Еще одним сценарием является получение поддержки [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], например редактирование окна **Свойства**. Дополнительные сведения см. в разделе [Общие сведения о разработке элемента управления](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Как упоминалось ранее, свойство следует регистрировать как присоединенное, если требуется использовать наследование значения свойства.  
  
<a name="how_do_i_create_attached_properties"></a>   
### <a name="how-to-create-an-attached-property"></a>Создание присоединенного свойства  
 Если ваш класс определяет вложенное свойство исключительно для использования на других типов, то не обязательно должен быть производным от <xref:System.Windows.DependencyObject>. Но вам нужно быть производным от <xref:System.Windows.DependencyObject> при выполнении общих [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модель предоставления вложенное свойство также является свойством зависимостей.  
  
 Определить вложенное свойство как свойство зависимости, объявив `public` `static` `readonly` поле типа <xref:System.Windows.DependencyProperty>. Это поле определяется с помощью возвращаемого значения <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод. Имя поля должно совпадать с именем присоединенного свойства с добавлением строки `Property`, чтобы следовать установленному шаблону [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] именования идентифицирующих полей по свойствам, которые они представляют. Поставщик присоединенного свойства также должен предоставлять статические методы `Get`*ИмяСвойства* и `Set`*ИмяСвойства* как методы доступа для присоединенных свойств. В противном случае это приведет к формированию системы свойств, которая не сможет использовать присоединенное свойство.  
  
> [!NOTE]
>  Если опустить метод доступа get присоединенного свойства, привязка данных для этого свойства не будет работать в средствах разработки, таких как Visual Studio и Expression Blend.  
  
#### <a name="the-get-accessor"></a>Метод доступа get  
 Сигнатура для метода доступа `Get`*ИмяСвойства* должна быть следующей.  
  
 `public static object Get` *ИмяСвойства* `(object` `target` `)`  
  
-   Объект `target` можно указать как более конкретный тип в реализации. Например <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> метода типам параметров как <xref:System.Windows.UIElement>, так как вложенное свойство предназначено только для задания на <xref:System.Windows.UIElement> экземпляров.  
  
-   Возвращаемое значение можно указать как более конкретный тип в реализации. Например <xref:System.Windows.Controls.DockPanel.GetDock%2A> метод его тип как <xref:System.Windows.Controls.Dock>, так как значение может быть задано только это перечисление.  
  
#### <a name="the-set-accessor"></a>Метод доступа set  
 Сигнатура для метода доступа `Set`*ИмяСвойства* должна быть следующей.  
  
 `public static void Set` *ИмяСвойства* `(object` `target` `, object` `value` `)`  
  
-   Объект `target` можно указать как более конкретный тип в реализации. Например <xref:System.Windows.Controls.DockPanel.SetDock%2A> метод его тип как <xref:System.Windows.UIElement>, так как вложенное свойство предназначено только для задания на <xref:System.Windows.UIElement> экземпляров.  
  
-   Объект `value` можно указать как более конкретный тип в реализации. Например <xref:System.Windows.Controls.DockPanel.SetDock%2A> метод его тип как <xref:System.Windows.Controls.Dock>, так как значение может быть задано только это перечисление. Помните, что значением этого метода являются входные данные, поступающие от загрузчика XAML, когда он встречает присоединенное свойство в использовании присоединенного свойства в макете. Эти входные данные являются значением, указанным как значение атрибута XAML в разметке. Таким образом, необходимо обеспечить поддержку преобразования типов, сериализатора значений или расширений разметки для используемого типа так, чтобы соответствующий тип можно было создать из значения атрибута (которое, в конечном счете, является просто строкой).  
  
 В следующем примере показано регистрации свойства зависимостей (с помощью <xref:System.Windows.DependencyProperty.RegisterAttached%2A> метод), а также `Get` *PropertyName* и `Set` *PropertyName* методы доступа . В этом примере именем присоединенного свойства является `IsBubbleSource`. Таким образом, методы доступа должны называться `GetIsBubbleSource` и `SetIsBubbleSource`.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### <a name="attached-property-attributes"></a>Атрибуты присоединенного свойства  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет несколько [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], которые предназначены для предоставления сведений о присоединенных свойствах процессам отражения и типичным пользователям отражения и сведений о свойстве, таким как разработчики. Поскольку присоединенные свойства имеют тип неограниченной области, разработчикам необходим способ, который позволит избежать представления пользователям глобального списка всех присоединенных свойств, которые определены в конкретной реализации технологии, использующей XAML. [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)], определяемый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для присоединенных свойств, может использоваться для ситуаций, когда данное присоединенное свойство должно отображаться в окне "Свойства". Эти атрибуты можно также применить для собственных присоединенных свойств. Назначение и синтаксис [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] описаны в соответствующих разделах справочника.  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## <a name="learning-more-about-attached-properties"></a>Дополнительные сведения о присоединенных свойствах  
  
-   Дополнительные сведения о создании присоединенного свойства см. в разделе [Регистрация присоединенного свойства](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   Более сложные сценарии использования свойств зависимостей и присоединенных свойств см. в разделе [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   Свойство можно также зарегистрировать как присоединенное свойство и как свойство зависимостей, но тем не менее предоставить реализации "оболочки". В этом случае свойство можно задать как для данного элемента, так и для любого элемента с помощью синтаксиса подключенных свойств XAML. Пример свойства с соответствующим скриптом для стандартного и вложенного использования является <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.DependencyProperty>  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Регистрация присоединенного свойства](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)
