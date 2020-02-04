---
title: Модель автоматизации пользовательского интерфейса пользовательского элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], applying UI automation
- accessibility [WPF], applying to custom controls
- custom controls [WPF], improving accessibility
- UI Automation [WPF], using with custom controls
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
ms.openlocfilehash: a370ed2c6b1f3273eca93b4865a032e8299f1cfb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738199"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] предоставляет единый общий интерфейс, который клиенты автоматизации могут использовать для проверки или использования пользовательских интерфейсов различных платформ и инфраструктур. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет как код для проверки качества (тестирования), так и приложения с поддержкой специальных возможностей, например средства чтения с экрана для проверки элементов пользовательского интерфейса и моделирования пользовательского взаимодействия с ними из другого кода. Сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на всех платформах см. в разделе, посвященном специальным возможностям.  
  
 В этом разделе описывается реализация серверного поставщика автоматизации пользовательского интерфейса для пользовательского элемента управления, применяемого в приложении WPF. WPF поддерживает [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] с помощью дерева одноранговых объектов автоматизации, которое сопутствует дереву элементов интерфейса пользователя. Тестовый код и приложения с поддержкой специальных возможностей могут использовать одноранговые объекты автоматизации напрямую (для внутрипроцессного кода) или через универсальный интерфейс, предоставляемый [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Одноранговые классы автоматизации  
 Элементы управления WPF поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] через дерево одноранговых классов, производных от <xref:System.Windows.Automation.Peers.AutomationPeer>. В соответствии с соглашением имена одноранговых классов начинаются с имени класса элемента управления, к которому добавляется строка "AutomationPeer". Например, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> является одноранговым классом для класса элемента управления <xref:System.Windows.Controls.Button>. Одноранговые классы примерно эквивалентны типам элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], но относятся к элементам WPF. Код автоматизации, обращающийся к приложениям WPF через интерфейс [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], не использует одноранговые классы автоматизации напрямую, но код автоматизации в том же пространстве процесса может использовать их напрямую.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Встроенные одноранговые классы автоматизации  
 Элементы реализуют одноранговый класс автоматизации, если они принимают взаимодействие пользователя с интерфейсом или содержат информацию, необходимую пользователям приложений для чтения с экрана. Не все визуальные элементы WPF имеют одноранговые классы автоматизации. Примеры классов, реализующих одноранговые классы автоматизации: <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>и <xref:System.Windows.Controls.Label>. Примерами классов, которые не реализуют одноранговые классы автоматизации, являются классы, производные от <xref:System.Windows.Controls.Decorator>, такие как <xref:System.Windows.Controls.Border>, и классы на основе <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.Canvas>.  
  
 Базовый класс <xref:System.Windows.Controls.Control> не имеет соответствующего однорангового класса. Если требуется, чтобы одноранговый класс соответствовал пользовательскому элементу управления, производному от <xref:System.Windows.Controls.Control>, необходимо создать пользовательский одноранговый класс из <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Вопросы безопасности для производных одноранговых классов  
 Одноранговые классы автоматизации должны работать в среде с частичным доверием. Код в сборке UIAutomationClient не настроен для выполнения в среде с частичным доверием и код однорангового класса автоматизации не должен ссылаться на эту сборку. Вместо этого следует использовать классы в сборке UIAutomationTypes. Например, следует использовать класс <xref:System.Windows.Automation.AutomationElementIdentifiers> из сборки UIAutomationTypes, которая соответствует классу <xref:System.Windows.Automation.AutomationElement> в сборке UIAutomationClient. В коде однорангового класса автоматизации можно безопасно ссылаться на сборку UIAutomationTypes.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Навигация по одноранговым объектам  
 После обнаружения однорангового узла автоматизации внутрипроцессный код может перемещаться по одноранговому дереву, вызывая методы <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> объекта. Переход между элементами WPF внутри элемента управления поддерживается реализацией метода <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> в одноранговых узлах. Система модели автоматизации пользовательского интерфейса вызывает этот метод для построения дерева подэлементов, содержащихся в элементе управления (например, элементов списка в элементе управления "список" (ListBox)). Метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> по умолчанию проходит по визуальному дереву элементов, чтобы создать дерево одноранговых узлов автоматизации. Пользовательские элементы управления переопределяют этот метод для предоставления дочерних элементов клиентам автоматизации, возвращая одноранговые объекты автоматизации элементов, которые передают информацию или разрешают взаимодействие с пользователем.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Настройка производного однорангового класса  
 Все классы, производные от <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement>, содержат защищенный виртуальный метод <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF вызывает <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>, чтобы получить одноранговый объект автоматизации для каждого элемента управления. Код автоматизации может использовать одноранговый объект для получения информации о характеристиках и функциях элемента управления и моделирования интерактивного использования. Пользовательский элемент управления, поддерживающий автоматизацию, должен переопределять <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> и возвращать экземпляр класса, производного от <xref:System.Windows.Automation.Peers.AutomationPeer>. Например, если пользовательский элемент управления является производным от класса <xref:System.Windows.Controls.Primitives.ButtonBase>, то объект, возвращаемый <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>, должен быть производным от <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 При реализации пользовательского элемента управления необходимо переопределить методы "Core" базового однорангового класса автоматизации, которые описывают специфическое поведение пользовательского элемента управления.  
  
### <a name="override-oncreateautomationpeer"></a>Переопределение метода OnCreateAutomationPeer  
 Переопределите метод <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> для пользовательского элемента управления таким образом, чтобы он возвращал объект поставщика, который должен прямо или косвенно наследоваться от <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Переопределение метода GetPattern  
 Одноранговые классы автоматизации упрощают некоторые аспекты реализации поставщиков [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на стороне сервера, но одноранговые классы автоматизации пользовательских элементов управления по-прежнему должны обрабатывать интерфейсы шаблонов. Как и поставщики, отличные от WPF, одноранговые элементы поддерживают шаблоны элементов управления, предоставляя реализации интерфейсов в пространстве имен <xref:System.Windows.Automation.Provider?displayProperty=nameWithType>, например <xref:System.Windows.Automation.Provider.IInvokeProvider>. Интерфейсы шаблонов элементов управления могут быть реализованы самим одноранговым классом или другим объектом. Реализация <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> однорангового узла возвращает объект, который поддерживает указанный шаблон. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] код вызывает метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> и задает значение перечисления <xref:System.Windows.Automation.Peers.PatternInterface>. Переопределение <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> должно возвращать объект, реализующий указанный шаблон. Если у элемента управления нет пользовательской реализации шаблона, можно вызвать реализацию <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> базового типа для получения его реализации или значение null, если шаблон не поддерживается для этого типа элемента управления. Например, пользовательскому элементу управления NumericUpDown можно присвоить значение в пределах диапазона, поэтому [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] однорангового узла будет реализовывать интерфейс <xref:System.Windows.Automation.Provider.IRangeValueProvider>. В следующем примере показано, как метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> однорангового узла переопределяется для реагирования на <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> значение.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод может также указывать вложенный элемент в качестве поставщика шаблонов. В следующем коде показано, как <xref:System.Windows.Controls.ItemsControl> передает обработку шаблона прокрутки однорангу внутреннего элемента управления <xref:System.Windows.Controls.ScrollViewer>.  
  
```csharp  
public override object GetPattern(PatternInterface patternInterface)  
{  
    if (patternInterface == PatternInterface.Scroll)  
    {  
        ItemsControl owner = (ItemsControl) base.Owner;  
  
        // ScrollHost is internal to the ItemsControl class  
        if (owner.ScrollHost != null)  
        {  
            AutomationPeer peer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost);  
            if ((peer != null) && (peer is IScrollProvider))  
            {  
                peer.EventsSource = this;  
                return (IScrollProvider) peer;  
            }  
        }  
    }  
    return base.GetPattern(patternInterface);  
}  
```  
  
```vb  
Public Class Class1  
    Public Overrides Function GetPattern(ByVal patternInterface__1 As PatternInterface) As Object  
        If patternInterface1 = PatternInterface.Scroll Then  
            Dim owner As ItemsControl = DirectCast(MyBase.Owner, ItemsControl)  
  
            ' ScrollHost is internal to the ItemsControl class  
            If owner.ScrollHost IsNot Nothing Then  
                Dim peer As AutomationPeer = UIElementAutomationPeer.CreatePeerForElement(owner.ScrollHost)  
                If (peer IsNot Nothing) AndAlso (TypeOf peer Is IScrollProvider) Then  
                    peer.EventsSource = Me  
                    Return DirectCast(peer, IScrollProvider)  
                End If  
            End If  
        End If  
        Return MyBase.GetPattern(patternInterface1)  
    End Function  
End Class  
```  
  
 Чтобы указать вложенный элемент для обработки шаблона, этот код получает объект подэлемента, создает одноранговый узел с помощью метода <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A>, устанавливает свойство <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> нового однорангового узла в текущий одноранговый узел и возвращает новый одноранговый узел. Установка <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> для подэлемента предотвращает отображение вложенного элемента в одноранговых деревьях службы автоматизации и обозначает все события, вызываемые вложенным элементом из элемента управления, указанного в <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. Элемент управления <xref:System.Windows.Controls.ScrollViewer> не отображается в дереве автоматизации, и события прокрутки, которые он создает, поступают из объекта <xref:System.Windows.Controls.ItemsControl>.  
  
### <a name="override-core-methods"></a>Переопределение методов "Core"  
 Код автоматизации получает информацию о вашем элементе управления, вызывая открытые методы однорангового класса. Чтобы предоставить информацию о своем элементе управления, переопределите все методы, имена которых заканчиваются на "Core", если ваша реализация элемента управления отличается от той, которая имеется в базовом одноранговом классе автоматизации. Как минимум, элемент управления должен реализовывать методы <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A>, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Ваша реализация <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> описывает элемент управления, возвращая <xref:System.Windows.Automation.ControlType> значение. Хотя можно возвращать <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, следует возвращать один из более конкретных типов элементов управления, если он точно описывает ваш элемент управления. Возвращаемое значение <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> требует дополнительной работы поставщика для реализации [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], а [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] клиентские продукты не могут предвидеть структуру управления, взаимодействие с клавиатурой и возможные шаблоны элементов управления.  
  
 Реализуйте методы <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A>, чтобы указать, содержит ли элемент управления содержимое данных, или выполняет интерактивную роль в пользовательском интерфейсе (или в обоих случаях). По умолчанию оба метода возвращают значение `true`. Эти параметры повышают удобство использования средств автоматизации (например, средств чтения с экрана), которые могут использовать эти методы для фильтрации дерева автоматизации. Если метод <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> передает обработку шаблона в одноранговый узел подэлемента, метод <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> однорангового узла может вернуть значение false, чтобы скрыть одноэлементный узел из дерева автоматизации. Например, прокрутка в <xref:System.Windows.Controls.ListBox> обрабатывается <xref:System.Windows.Controls.ScrollViewer>, а одноранговый узел автоматизации для <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> возвращается методом <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer>, связанным с <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Таким образом, метод <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> возвращает `false`, чтобы <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> не отображались в дереве автоматизации.  
  
 Одноранговый класс автоматизации должен предоставлять необходимые значения по умолчанию для вашего элемента управления. Обратите внимание, что XAML, который ссылается на ваш элемент управления, может переопределять одноранговые реализации основных методов, включая атрибуты <xref:System.Windows.Automation.AutomationProperties>. Например, следующий код XAML создает кнопку, которая имеет два настраиваемых свойства [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Реализация поставщиков шаблонов  
 Интерфейсы, реализованные настраиваемым поставщиком, объявляются явно, если элемент-владелец наследуется непосредственно от <xref:System.Windows.Controls.Control>. Например, следующий код объявляет одноранговый узел для <xref:System.Windows.Controls.Control>, который реализует значение диапазона.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Если элемент управления-владелец является производным от определенного типа элемента управления, например <xref:System.Windows.Controls.Primitives.RangeBase>, одноранговый узел может быть производным от эквивалентного производного однорангового класса. В этом случае одноранговый узел будет производным от <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, который предоставляет базовую реализацию <xref:System.Windows.Automation.Provider.IRangeValueProvider>. В следующем коде показано объявление такого однорангового класса.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Пример реализации см. в [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) разделе или [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) исходном коде, который реализует и использует пользовательский элемент управления NumericUpDown.  
  
### <a name="raise-events"></a>Создание событий  
 Клиенты автоматизации могут подписаться на события автоматизации. Пользовательские элементы управления должны передавать изменения в состояние управления, вызывая метод <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A>. Аналогичным образом при изменении значения свойства вызовите метод <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A>. В приведенном ниже коде показано, как получить одноранговый объект из кода элемента управления и вызвать метод для создания события. В качестве меры оптимизации код также определяет, имеются ли прослушиватели для этого типа событий. Создание событий только при наличии соответствующих прослушивателей позволяет избежать лишней нагрузки и помогает сохранять должную скорость отклика элемента управления.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о модели автоматизации пользовательского интерфейса](../../ui-automation/ui-automation-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [Пользовательский элемент управления NumericUpDownC#() на GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Пользовательский элемент управления NumericUpDown (Visual Basic) на GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
