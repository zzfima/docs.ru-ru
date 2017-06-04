---
title: "Общие сведения об объектах класса Freezable | Microsoft Docs"
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
  - "классы, Freezable"
  - "Freezable - объекты, описание"
  - "отмена фиксации объектов Freezable"
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Общие сведения об объектах класса Freezable
В данном разделе описано, как эффективно использовать и создавать объекты <xref:System.Windows.Freezable>, которые обеспечивают специальные возможности, помогающие повысить производительность приложения.  Примерами объектов класса Freezable являются кисти, перья, преобразования, геометрия объектов и анимация.  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="whatisafreezable"></a>   
## Понятие объекта Freezable  
 <xref:System.Windows.Freezable> представляет сосбой особый тип объекта, имеющий два состояния: фиксированное и нефиксированное.  Незафиксированный объект <xref:System.Windows.Freezable> ведет себя как любой другой объект.  Зафиксированный объект <xref:System.Windows.Freezable> нельзя изменить.  
  
 Класс <xref:System.Windows.Freezable> предоставляет событие <xref:System.Windows.Freezable.Changed> для уведомления наблюдающих объектов обо всех изменениях объекта.  Фиксация объекта <xref:System.Windows.Freezable> может повысить его производительность, поскольку больше не потребуется тратить ресурсы на уведомления об изменениях.  Зафиксированные объекты <xref:System.Windows.Freezable> также могут совместно использоваться потоками, в отличие от незафиксированных <xref:System.Windows.Freezable>.  
  
 Хотя класс <xref:System.Windows.Freezable> имеет много приложений, большинство объектов <xref:System.Windows.Freezable> в приложении [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] связаны с графической подсистемой.  
  
 Класс <xref:System.Windows.Freezable> упрощает использование определенных объектов графических систем и помогает повысить быстродействие приложения.  Примерами типов, наследуемых от класса <xref:System.Windows.Freezable>, являются классы <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform> и <xref:System.Windows.Media.Geometry>.  Так как они содержат неуправляемые ресурсы, система должна отслеживать изменения этих объектов и при наличии изменений исходного объекта обновлять соответствующие им неуправляемые ресурсы.  Даже если объект графической системы на самом деле не изменяется, то система все равно должна потратить ресурсы на наблюдение за объектом, если над ним выполняются некоторые действия.  
  
 Например, при создании кисти <xref:System.Windows.Media.SolidColorBrush> и использовании ее для формирования фона кнопки.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 При прорисовке кнопки графическая подсистема [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует предоставленные пользователем сведения для закраски группы пикселей, чтобы задать внешний вид кнопки.  Хотя пользователь использует заливку сплошным цветом для описания внешнего вида кнопки, фактически не она выполняет закраску.  Графическая система создает быстрые низкоуровневые объекты для кнопки и кисти, и именно эти объекты фактически отображаются на экране.  
  
 При изменении кисти эти низкоуровневые объекты необходимо обновлять.  Именно класс Freezable дает кисти возможность найти соответствующие ей низкоуровневые объекты и обновить их, когда она изменяется.  Если эта возможность включена, кисть считается "незафиксированной".  
  
 Метод Freezable <xref:System.Windows.Freezable.Freeze%2A> позволяет отключить данную возможность самостоятельного обновления.  Этот метод позволяет "зафиксировать" кисть, т.е. сделать ее неизменяемой.  
  
> [!NOTE]
>  Не каждый объект Freezable может быть зафиксирован.  Чтобы избежать возникновения исключения <xref:System.InvalidOperationException>, перед фиксированием объекта необходимо предварительно проверить значение свойства <xref:System.Windows.Freezable.CanFreeze%2A> объекта Freezable, чтобы определить, может ли он быть зафиксирован.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Когда больше не требуется изменять Freezable, фиксирование объекта дает выигрыш в производительности.  Если бы кисть в данном примере была зафиксирована, то графической системе больше не понадобилось бы отслеживать ее изменения.  Графическая система также может выполнять другие виды оптимизации, так как известно, что кисть не будет изменяться.  
  
> [!NOTE]
>  Для удобства объекты Freezable остаются незафиксированными, пока вы не зафиксируете их явным образом.  
  
<a name="frozenfreezables"></a>   
## Использование объектов Freezable  
 Использование незафиксированного объекта Freezable аналогично использованию любого другого типа объектов.  В следующем примере цвет объекта <xref:System.Windows.Media.SolidColorBrush> изменяется с желтого на красный после того, как он используется для закраски фона кнопки.  Графическая система работает в фоновом режиме, чтобы автоматически изменить цвет кнопки с желтого на красный при следующем обновлении экрана.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### Фиксация объекта класса Freezable  
 Чтобы сделать объект <xref:System.Windows.Freezable> неизменяемым, необходимо вызвать его метод <xref:System.Windows.Freezable.Freeze%2A>.  При фиксировании объекта, содержащего объекты Freezable, вложенные объекты также фиксируются.  Например, если зафиксировать объект <xref:System.Windows.Media.PathGeometry>, содержащиеся в нем фигуры и сегменты также будут зафиксированы.  
  
 Freezable **нельзя** зафиксировать при выполнении одного из следующих условий:  
  
-   Объект имеет свойства анимации или привязки данных.  
  
-   У объекта есть свойства, заданные динамическим ресурсом.  Дополнительные сведения о динамических ресурсах см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Он содержит подобъекты <xref:System.Windows.Freezable>, которые нельзя зафиксировать.  
  
 Если не выполняется ни одно из этих условий и не требуется изменять объект <xref:System.Windows.Freezable>, его стоит зафиксировать, чтобы получить описанный выше выигрыш в производительности.  
  
 Объект Freezable не может быть изменен после вызова его метода <xref:System.Windows.Freezable.Freeze%2A>.  При попытке изменения зафиксированного объекта возникает исключение <xref:System.InvalidOperationException>.  Следующий код вызывает исключение, поскольку выполняется попытка изменить кисть после того, как она была зафиксирована.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Чтобы избежать возникновения этого исключения, можно использовать метод <xref:System.Windows.Freezable.IsFrozen%2A>, чтобы определить, зафиксирован ли объект <xref:System.Windows.Freezable>.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 В предыдущем примере кода с помощью метода <xref:System.Windows.Freezable.Clone%2A> была получена изменяемая копия зафиксированного объекта.  В следующем разделе клонирование рассматривается более подробно.  
  
 **Замечание** Поскольку зафиксированный объект Freezable не может быть анимирован, система анимации автоматически создаст изменяемые копии зафиксированных объектов <xref:System.Windows.Freezable> при попытке их анимации с помощью <xref:System.Windows.Media.Animation.Storyboard>.  Чтобы снизить накладные расходы, связанные с клонированием, оставьте объект незафиксированным, если потребуется его анимировать.  Дополнительные сведения об анимации с помощью Storyboard см. в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### Фиксирование объектов из разметки  
 Чтобы зафиксировать объект <xref:System.Windows.Freezable>, объявленный в разметке, используйте атрибут `PresentationOptions:Freeze`.  В следующем примере <xref:System.Windows.Media.SolidColorBrush> объявляется как ресурс страницы и фиксируется.  Затем она используется для задания фона кнопки.  
  
 [!code-xml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Для использования атрибута `Freeze` необходимо сопоставить с параметрами представления пространство имен: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.  `PresentationOptions` является рекомендуемым префиксом для сопоставления пространства имен:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Так как не все средства чтения XAML распознают этот атрибут, рекомендуется использовать [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md), чтобы пометить атрибут `Presentation:Freeze` как некритический:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Дополнительные сведения см. на странице [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).  
  
### Отмена фиксации объекта класса Freezable  
 После фиксации объект <xref:System.Windows.Freezable> нельзя изменить или снять состояние фиксации. Однако можно создать незафиксированную копию с помощью метода <xref:System.Windows.Freezable.Clone%2A> или метода <xref:System.Windows.Freezable.CloneCurrentValue%2A>.  
  
 В следующем примере фон кнопки закрашивается кистью и затем кисть фиксируется.  Незафиксированная копия кисти получается с помощью метода <xref:System.Windows.Freezable.Clone%2A>.  Копия изменяется и используется для изменения фона кнопки с желтого на красный.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Вне зависимости от выбора метода клонирования, анимация никогда не копируется в новый объект <xref:System.Windows.Freezable>.  
  
 Методы <xref:System.Windows.Freezable.Clone%2A> и <xref:System.Windows.Freezable.CloneCurrentValue%2A> создают детальные копии объекта Freezable.  Если объект Freezable содержит другие зафиксированные объекты Freezable, они также копируются и становятся изменяемыми.  Например, если копировать зафиксированный объект <xref:System.Windows.Media.PathGeometry>, чтобы сделать его изменяемым, содержащиеся в этом объекте фигуры и сегменты также копируются и становятся изменяемыми.  
  
<a name="createyourownfreezableclass"></a>   
## Создание собственного класса Freezable  
 Класс, производный от <xref:System.Windows.Freezable>, поддерживает следующие функции:  
  
-   Особые состояния: состояние только для чтения \(фиксированное\) и состояние только для записи.  
  
-   Потокобезопасность: фиксированный объект <xref:System.Windows.Freezable> можно использовать в нескольких потоках.  
  
-   Подробные уведомления об изменениях: в отличие от других объектов <xref:System.Windows.DependencyObject>, объекты Freezable сообщают об изменениях, если изменяются значения вложенных свойств.  
  
-   Удобное клонирование: класс Freezable включает несколько уже реализованных методов, которые обеспечивают большую глубину клонирования.  
  
 <xref:System.Windows.Freezable> представляет собой тип <xref:System.Windows.DependencyObject> и поэтому использует систему свойств зависимости.  Свойства класса не обязательно должны быть свойствами зависимости, но с помощью свойств зависимости объем кода, который нужно написать, сократится, так как класс <xref:System.Windows.Freezable> был разработан с учетом свойств зависимости.  Дополнительные сведения о системе свойств зависимости см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Каждый подкласс <xref:System.Windows.Freezable> должен переопределять метод <xref:System.Windows.Freezable.CreateInstanceCore%2A>.  Если класс использует свойства зависимости для всех своих данных, создание класса завершено.  
  
 Если класс содержит члены данных, не использующие свойство зависимости, необходимо также переопределить следующие методы:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Необходимо также соблюдать следующие правила для доступа и записи членов данных, которые не используют свойства зависимости:  
  
-   В начале любого [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], считывающего члены данных, не использующих свойство зависимости, вызовите метод <xref:System.Windows.Freezable.ReadPreamble%2A>.  
  
-   В начале любого API, записывающего члены данных, не использующие свойство зависимости, вызовите метод <xref:System.Windows.Freezable.WritePreamble%2A>.  \(После вызова <xref:System.Windows.Freezable.WritePreamble%2A> в [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] не требуется дополнительный вызов <xref:System.Windows.Freezable.ReadPreamble%2A>, если также считываются члены данных, не использующие свойство зависимости.\)  
  
-   Вызовите метод <xref:System.Windows.Freezable.WritePostscript%2A> перед выходом из методов, которые записывают члены данных, не использующие свойство зависимости.  
  
 Если класс содержит не поддерживающие свойство зависимости члены данных, являющиеся объектами <xref:System.Windows.DependencyObject>, нужно также вызывать метод <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> при каждом изменении их значений, даже если члену задается значение `null`.  
  
> [!NOTE]
>  Очень важно начинать каждый переопределяемый метод <xref:System.Windows.Freezable> с вызова базовой реализации.  
  
 Пример пользовательского класса <xref:System.Windows.Freezable> см. на веб\-странице [Пример Custom Animation](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## См. также  
 <xref:System.Windows.Freezable>   
 [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981)   
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)