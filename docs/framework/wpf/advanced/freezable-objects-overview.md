---
title: Общие сведения об объектах класса Freezable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: d3b9f6f7af22b2a846f4ee34e8d4d00bb032fd69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548474"
---
# <a name="freezable-objects-overview"></a>Общие сведения об объектах класса Freezable
Описывается, как эффективно использовать и создавать <xref:System.Windows.Freezable> объекты, которые обеспечивают специальные возможности, которые могут помочь повысить производительность приложения. Объекты freezable примеры кисти, перья, преобразования, геометрии и анимации.  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a>Что такое Freezable?  
 Объект <xref:System.Windows.Freezable> — это специальный тип объекта, имеющего два состояния: зафиксирована и фиксации. Незафиксированный <xref:System.Windows.Freezable> ведет себя как любой другой объект. Зафиксированный <xref:System.Windows.Freezable> не может быть изменен.  
  
 Объект <xref:System.Windows.Freezable> предоставляет <xref:System.Windows.Freezable.Changed> событие для уведомления наблюдателей об каких-либо изменений объекта. Замораживание <xref:System.Windows.Freezable> может повысить производительность, поскольку больше не требуется тратить ресурсы на уведомления об изменениях. Зафиксированный <xref:System.Windows.Freezable> также могут совместно использоваться потоками, в отличие от незафиксированных <xref:System.Windows.Freezable> невозможно.  
  
 Несмотря на то что <xref:System.Windows.Freezable> класс имеет множество применений наиболее <xref:System.Windows.Freezable> объекты в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] связаны с графической подсистемы.  
  
 <xref:System.Windows.Freezable> Класс упрощает использование определенных объектов графических систем и способствует повышению производительности приложения. Примеры типов, которые наследуют от <xref:System.Windows.Freezable> включают <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, и <xref:System.Windows.Media.Geometry> классы. Так как они содержат неуправляемые ресурсы, система должна отслеживать изменения этих объектов и обновлять соответствующие им неуправляемые ресурсы при наличии изменений в исходный объект. Даже если вы не меняете фактически объект графической системы, системы необходимо по-прежнему тратить некоторые ресурсы наблюдения за объектом, в случае, если вы изменяете его.  
  
 Например, предположим, вы создаете <xref:System.Windows.Media.SolidColorBrush> кисти и использовать его в качестве фона кнопки.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 При отображении кнопки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] графическая подсистема использует сведения, предоставленные закраски группы пикселей, чтобы задать внешний вид кнопки. Несмотря на то, что вы использовали Одноцветная кисть для описания того, как должен быть окрашен кнопки, сплошной цвет кисти фактически не выполняет заливку. Графическая система создает быстрые низкоуровневые объекты для кнопки и кисти, а именно эти объекты, которые отображаются на экране.  
  
 В случае изменения кисти эти низкоуровневые объекты придется повторно создать. Класс freezable является то, что дает возможность найти его соответствующий низкоуровневые объекты и обновить их, когда она изменяет кисти. Если эта возможность включена, кисть считается «незафиксированной».  
  
 Freezable <xref:System.Windows.Freezable.Freeze%2A> метод позволяет отключить данную возможность самостоятельного обновления. Этот метод можно использовать для кисть «зафиксированной», и неизменяемым.  
  
> [!NOTE]
>  Не каждый объект Freezable может быть зафиксирован. Чтобы избежать возникновения <xref:System.InvalidOperationException>, проверьте значение объект Freezable <xref:System.Windows.Freezable.CanFreeze%2A> свойства, чтобы определить, является ли он быть зафиксирован перед фиксированием.  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 Когда больше не требуется изменять freezable, фиксирование объекта дает выигрыш в производительности. Если закрепить кисти в этом примере, графической системе больше не потребуется отслеживать ее изменения. Графической системе также можно сделать другие виды оптимизации, так как известно, что кисть не будет изменяться.  
  
> [!NOTE]
>  Для удобства объекты freezable остаются незафиксированными, пока вы явным образом зафиксировать их.  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a>С помощью объектов Freezable  
 Использование незафиксированного объекта freezable аналогично использованию любого другого типа объекта. В следующем примере цвет <xref:System.Windows.Media.SolidColorBrush> изменяется с желтого на красный после его использования в качестве фона кнопки. Графическая система работает в фоновом для автоматического изменения кнопки с желтого на красный при очередном обновлении экрана.  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a>Замораживание Freezable  
 Чтобы сделать <xref:System.Windows.Freezable> неизменяемым, необходимо вызвать его <xref:System.Windows.Freezable.Freeze%2A> метод. Объект, содержащий объекты freezable замораживается, эти объекты также фиксируются. Например, если зафиксировать <xref:System.Windows.Media.PathGeometry>, фигуры и сегменты также будут зафиксированы.  
  
 Freezable **нельзя** зафиксировать при любой из следующих:  
  
-   Объект имеет анимированные или свойства с привязкой к данным.  
  
-   Он имеет свойства, заданные на динамический ресурс. (См. [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) Дополнительные сведения о динамических ресурсах.)  
  
-   Он содержит <xref:System.Windows.Freezable> подчиненных объектах, которые нельзя зафиксировать.  
  
 Если эти условия имеют значение false, а не требуется изменять <xref:System.Windows.Freezable>, то стоит зафиксировать, чтобы получить выигрыш в производительности, описанных ранее.  
  
 При вызове метода freezable <xref:System.Windows.Freezable.Freeze%2A> метода, не может быть изменен. Предпринимается попытка изменить зафиксированного объекта возникает <xref:System.InvalidOperationException> исключение. Следующий код создает исключение, так как выполняется попытка изменить кисть после была зафиксирована.  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 Чтобы избежать возникновения этого исключения, можно использовать <xref:System.Windows.Freezable.IsFrozen%2A> метод, чтобы определить, является ли <xref:System.Windows.Freezable> заморожен.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 В предыдущем примере был сделан изменяемой копии зафиксированного объекта с помощью <xref:System.Windows.Freezable.Clone%2A> метод. В следующем разделе описываются более подробно клонирования.  
  
 **Примечание** из-за замороженный невозможно анимировать freezable, анимация система автоматически создает изменяемые клоны замороженный <xref:System.Windows.Freezable> объектов при попытке их с помощью анимации <xref:System.Windows.Media.Animation.Storyboard>. Чтобы снизить накладные расходы, вызванные клонирования, оставьте объект незафиксированным, если для его анимации. Дополнительные сведения об анимации с помощью Storyboard см. в разделе [Общие](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
### <a name="freezing-from-markup"></a>Фиксирование объектов из разметки  
 Чтобы закрепить <xref:System.Windows.Freezable> объявленный в разметке, используется `PresentationOptions:Freeze` атрибута. В следующем примере <xref:System.Windows.Media.SolidColorBrush> объявляется как ресурс страницы и фиксации. Затем используется для задания фона кнопки.  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 Для использования `Freeze` атрибут, необходимо сопоставить с параметрами представления пространство имен: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`. `PresentationOptions` — Это рекомендуемый префикс для сопоставления данного пространства имен:  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 Так как не все средства чтения XAML распознают этот атрибут, рекомендуется использовать [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) пометить `Presentation:Freeze` атрибута игнорируемый:  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 Дополнительные сведения см. в разделе [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) страницы.  
  
### <a name="unfreezing-a-freezable"></a>«Размораживание» Freezable  
 После фиксации <xref:System.Windows.Freezable> никогда не может быть изменен или разморозить; Однако можно создать с помощью незафиксированную копию <xref:System.Windows.Freezable.Clone%2A> или <xref:System.Windows.Freezable.CloneCurrentValue%2A> метод.  
  
 В следующем примере задаются кисть фона кнопки и затем, кисть фиксируется. Незафиксированная копия кисти с использованием <xref:System.Windows.Freezable.Clone%2A> метод. Копия изменяется и используется для изменения фона кнопки с желтого на красный.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  Независимо от используемого метода клона анимации не копируются в новый <xref:System.Windows.Freezable>.  
  
 <xref:System.Windows.Freezable.Clone%2A> И <xref:System.Windows.Freezable.CloneCurrentValue%2A> методы создания глубокой копии объекта freezable. Если объект freezable содержит другие зафиксированные объекты freezable, они также клонируются и становятся изменяемыми. Например, если копировать зафиксированный <xref:System.Windows.Media.PathGeometry> чтобы сделать его изменяемым фигуры и сегменты также копируются и становятся изменяемыми.  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a>Создание собственного класса Freezable  
 Класс, производный от <xref:System.Windows.Freezable> поддерживает следующие функции.  
  
-   Особые состояния: только для чтения (зафиксирован) и состояние для записи.  
  
-   Потокобезопасность: зафиксированный <xref:System.Windows.Freezable> может использоваться несколькими потоками.  
  
-   Подробные уведомления об изменениях: в отличие от других <xref:System.Windows.DependencyObject>, объекты Freezable предоставляет уведомления об изменении при изменении значений вложенных свойств.  
  
-   Удобное клонирование: класс Freezable уже реализован несколько методов, которые обеспечивают большую глубину клонирования.  
  
 Объект <xref:System.Windows.Freezable> — это тип <xref:System.Windows.DependencyObject>и поэтому используется в системе свойств зависимостей. Свойства класса не обязательно должны быть свойств зависимостей, но с использованием свойств зависимостей позволяет снизить объем кода, необходимо написать, так как <xref:System.Windows.Freezable> класс был разработан с учетом свойств зависимостей. Дополнительные сведения о системе свойств зависимостей см. в разделе [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 Каждый <xref:System.Windows.Freezable> необходимо переопределить подкласс <xref:System.Windows.Freezable.CreateInstanceCore%2A> метод. Если ваш класс использует свойства зависимостей для своих данных, все готово.  
  
 Если класс содержит члены данных, не относящихся к зависимостям свойство, необходимо также переопределить следующие методы:  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 Также необходимо соблюдать следующие правила для доступа и записи элементов данных, которые не являются свойствами зависимости.  
  
-   В начале любого [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] , осуществляющий чтение членов данных свойств не относящихся к зависимостям, вызовите метод <xref:System.Windows.Freezable.ReadPreamble%2A> метод.  
  
-   В начале любого API, который записывает членов данных свойств не относящихся к зависимостям, вызовите <xref:System.Windows.Freezable.WritePreamble%2A> метод. (После вызова <xref:System.Windows.Freezable.WritePreamble%2A> в [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], не требуется дополнительный вызов к <xref:System.Windows.Freezable.ReadPreamble%2A> также считывать членов данных свойств не относящихся к зависимостям.)  
  
-   Вызовите <xref:System.Windows.Freezable.WritePostscript%2A> метод перед выходом из методов, которые записывают членов данных свойств не относящихся к зависимостям.  
  
 Если класс содержит элементы данных зависимостей свойства, которые являются <xref:System.Windows.DependencyObject> объектов, необходимо также вызвать <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> метод каждый раз при изменении на их значений, даже если устанавливаемое члена `null`.  
  
> [!NOTE]
>  Очень важно запускать каждую <xref:System.Windows.Freezable> метода переопределения с помощью вызова к базовой реализации.  
  
 Пример настраиваемого <xref:System.Windows.Freezable> см. в описании [пример пользовательского](http://go.microsoft.com/fwlink/?LinkID=159981).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable>  
 [Пример пользовательской анимации](http://go.microsoft.com/fwlink/?LinkID=159981)  
 [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Пользовательские свойства зависимостей](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
