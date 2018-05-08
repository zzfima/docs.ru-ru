---
title: Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF
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
ms.openlocfilehash: fbd19591c260b0ad160339b45fd762e7a87bbc74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] предоставляет единый общий интерфейс, который клиенты автоматизации могут использовать для проверки или использования пользовательских интерфейсов различных платформ и инфраструктур. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет как код для проверки качества (тестирования), так и приложения с поддержкой специальных возможностей, например средства чтения с экрана для проверки элементов пользовательского интерфейса и моделирования пользовательского взаимодействия с ними из другого кода. Сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на всех платформах см. в разделе, посвященном специальным возможностям.  
  
 В этом разделе описывается реализация серверного поставщика автоматизации пользовательского интерфейса для пользовательского элемента управления, применяемого в приложении WPF. WPF поддерживает [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] с помощью дерева одноранговых объектов автоматизации, которое сопутствует дереву элементов интерфейса пользователя. Тестовый код и приложения с поддержкой специальных возможностей могут использовать одноранговые объекты автоматизации напрямую (для внутрипроцессного кода) или через универсальный интерфейс, предоставляемый [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Одноранговые классы автоматизации  
 Элементы управления WPF поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] по дереву одноранговых классов, производных от <xref:System.Windows.Automation.Peers.AutomationPeer>. В соответствии с соглашением имена одноранговых классов начинаются с имени класса элемента управления, к которому добавляется строка "AutomationPeer". Например <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> является одноранговым классом для <xref:System.Windows.Controls.Button> класса элемента управления. Одноранговые классы примерно похожи на типы элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], но относятся к элементам [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Код автоматизации, обращающийся к приложениям WPF через интерфейс [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], не использует одноранговые классы автоматизации напрямую, но код автоматизации в том же пространстве процесса может использовать их напрямую.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Встроенные одноранговые классы автоматизации  
 Элементы реализуют одноранговый класс автоматизации, если они принимают взаимодействие пользователя с интерфейсом или содержат информацию, необходимую пользователям приложений для чтения с экрана. Не все визуальные элементы WPF имеют одноранговые классы автоматизации. Примеры классов, реализующих одноранговые автоматизации <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.Label>. Примеры классов, не реализующих одноранговые автоматизации являются классы, производные от <xref:System.Windows.Controls.Decorator>, такие как <xref:System.Windows.Controls.Border>и классов на основе <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.Canvas>.  
  
 Базовый <xref:System.Windows.Controls.Control> класс не имеет соответствующего однорангового класса. Если вам требуется однорангового класса в пользовательский элемент управления, производный от <xref:System.Windows.Controls.Control>, необходимо создать производный класс одноранговый из <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Вопросы безопасности для производных одноранговых классов  
 Одноранговые классы автоматизации должны работать в среде с частичным доверием. Код в сборке UIAutomationClient не настроен для выполнения в среде с частичным доверием и код однорангового класса автоматизации не должен ссылаться на эту сборку. Вместо этого следует использовать классы в сборке UIAutomationTypes. Например, следует использовать <xref:System.Windows.Automation.AutomationElementIdentifiers> класса из UIAutomationTypes сборки, который соответствует <xref:System.Windows.Automation.AutomationElement> класса в сборке UIAutomationClient. В коде однорангового класса автоматизации можно безопасно ссылаться на сборку UIAutomationTypes.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Навигация по одноранговым объектам  
 После нахождения одноранговый элемент автоматизации, внутрипроцессный код может перемещаться по дереву одноранговых путем вызова объекта <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> методы. Перемещение между [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] элементы внутри элемента управления поддерживается реализацией однорангового узла <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> метод. Система модели автоматизации пользовательского интерфейса вызывает этот метод для построения дерева подэлементов, содержащихся в элементе управления (например, элементов списка в элементе управления "список" (ListBox)). Значение по умолчанию <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> метод обходит визуального дерева элементов для построения дерева одноранговых классов автоматизации. Пользовательские элементы управления переопределяют этот метод для предоставления дочерних элементов клиентам автоматизации, возвращая одноранговые объекты автоматизации элементов, которые передают информацию или разрешают взаимодействие с пользователем.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Настройка производного однорангового класса  
 Все классы, производные от <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> содержат защищенный виртуальный метод <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF вызывает <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> для получения объекта автоматизации однорангового узла для каждого элемента управления. Код автоматизации может использовать одноранговый объект для получения информации о характеристиках и функциях элемента управления и моделирования интерактивного использования. Пользовательский элемент управления, поддерживающий автоматизацию необходимо переопределить <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> и возвратить экземпляр класса, производного от <xref:System.Windows.Automation.Peers.AutomationPeer>. Например, если пользовательский элемент управления является производным от <xref:System.Windows.Controls.Primitives.ButtonBase> класса, то объект, возвращаемый <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> должен быть производным от <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 При реализации пользовательского элемента управления необходимо переопределить методы "Core" базового однорангового класса автоматизации, которые описывают специфическое поведение пользовательского элемента управления.  
  
### <a name="override-oncreateautomationpeer"></a>Переопределение метода OnCreateAutomationPeer  
 Переопределить <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> метод для пользовательского элемента управления, возвращающее объект поставщика, который должен быть производным прямо или косвенно от <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Переопределение метода GetPattern  
 Одноранговые классы автоматизации упрощают некоторые аспекты реализации поставщиков [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на стороне сервера, но одноранговые классы автоматизации пользовательских элементов управления по-прежнему должны обрабатывать интерфейсы шаблонов. Как и поставщиков, отличных от WPF, одноранговые узлы поддерживают шаблоны элементов управления путем предоставления реализаций интерфейсов в <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> пространства имен, такие как <xref:System.Windows.Automation.Provider.IInvokeProvider>. Интерфейсы шаблонов элементов управления могут быть реализованы самим одноранговым классом или другим объектом. Реализация однорангового узла <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> возвращает объект, который поддерживает указанный шаблон. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] код вызывает метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод и указывает <xref:System.Windows.Automation.Peers.PatternInterface> значение перечисления. Переопределенный <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> должен возвращать объект, реализующий указанный шаблон. Если элемент управления не имеет пользовательскую реализацию шаблона, можно вызвать реализацию базового типа <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> для извлечения его реализации или значение null, если шаблон не поддерживается для этого типа элемента управления. Например, пользовательский элемент управления NumericUpDown может быть присвоено значение в диапазоне, поэтому его [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] одноранговых будет реализовывать <xref:System.Windows.Automation.Provider.IRangeValueProvider> интерфейса. В следующем примере показан способ однорангового узла <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод переопределяется, чтобы реагировать на <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> значение.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Объект <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод также можно указывать подэлемент в качестве поставщика шаблона. В следующем коде показано, как <xref:System.Windows.Controls.ItemsControl> передает обработку шаблона для однорангового узла из своих внутренних прокрутки <xref:System.Windows.Controls.ScrollViewer> элемента управления.  
  
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
  
 Чтобы указать подэлемент для обработки шаблона, этот код возвращает объект подэлемента, создает одноранговый узел с помощью <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> задает метод, <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> свойство новый одноранговый узел для текущего однорангового узла и возвращает новый одноранговый узел. Установка <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> подэлементу подэлемент будут отображаться в дереве модели автоматизации одноранговых и обозначает все события, вызванные подэлемент инициировавшему элемент управления, указанный в <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. <xref:System.Windows.Controls.ScrollViewer> Управления не отображается в дереве модели автоматизации и событий прокрутки, которые он создает, фигурирует <xref:System.Windows.Controls.ItemsControl> объекта.  
  
### <a name="override-core-methods"></a>Переопределение методов "Core"  
 Код автоматизации получает информацию о вашем элементе управления, вызывая открытые методы однорангового класса. Чтобы предоставить информацию о своем элементе управления, переопределите все методы, имена которых заканчиваются на "Core", если ваша реализация элемента управления отличается от той, которая имеется в базовом одноранговом классе автоматизации. Как минимум, элемент управления должен реализовать <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> методов, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Реализация <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> описывает элемент управления, возвращая <xref:System.Windows.Automation.ControlType> значение. Несмотря на то, что можно возвращать <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>, вы должны возвращать один более конкретные типы элементов управления, если точно описывает элемент управления. Возвращаемое значение <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> требует дополнительной работы поставщика, чтобы реализовать [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], и [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] клиенты не могут предвидеть структуру элемента управления, взаимодействие с клавиатурой и возможные шаблоны элементов управления.  
  
 Реализуйте <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> методов, чтобы указать ли элемент управления содержимым данных или выполняет интерактивную роль в интерфейсе пользователя (или оба). По умолчанию оба метода возвращают значение `true`. Эти параметры повышают удобство использования средств автоматизации (например, средств чтения с экрана), которые могут использовать эти методы для фильтрации дерева автоматизации. Если ваш <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> метод передает обработку шаблона в дочерний элемент однорангового узла, дочерний элемент узла <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> метод может возвращать значение false, чтобы скрыть дочерний элемент однорангового узла в дереве автоматизации. Например, прокрутка в <xref:System.Windows.Controls.ListBox> обрабатывается <xref:System.Windows.Controls.ScrollViewer>и одноранговый элемент автоматизации для <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> возвращается <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> метод <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> , связанный с <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Таким образом <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> метод <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> возвращает `false`, после чего <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> не отображается в дереве автоматизации.  
  
 Одноранговый класс автоматизации должен предоставлять необходимые значения по умолчанию для вашего элемента управления. Обратите внимание, что XAML, который ссылается на элемент управления можно переопределить реализации одноранговых классов базовых методов, включая <xref:System.Windows.Automation.AutomationProperties> атрибуты. Например, следующий код XAML создает кнопку, которая имеет два настраиваемых свойства [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Реализация поставщиков шаблонов  
 Интерфейсы, реализованные с помощью пользовательского поставщика объявлены явно, если владелец-элемент наследует непосредственно от <xref:System.Windows.Controls.Control>. Например, в следующем коде объявляется одноранговым узлом для <xref:System.Windows.Controls.Control> , реализующий значение диапазона.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Владелец-элемент управления, производного от определенного типа элемента управления, такие как <xref:System.Windows.Controls.Primitives.RangeBase>, однорангового узла, которые могут быть производными от эквивалентного производного однорангового класса. В этом случае одноранговый узел будет наследовать от класса <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, который предоставляет базовую реализацию <xref:System.Windows.Automation.Provider.IRangeValueProvider>. В следующем коде показано объявление такого однорангового класса.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Пример реализации см. в разделе [Пример пользовательского элемента управления NumericUpDown с темой и поддержкой модели автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025).  
  
### <a name="raise-events"></a>Создание событий  
 Клиенты автоматизации могут подписаться на события автоматизации. Пользовательские элементы управления должен передавать изменения, чтобы управлять состоянием посредством вызова <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> метод. Аналогично, при изменении значения свойства вызывать <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> метод. В приведенном ниже коде показано, как получить одноранговый объект из кода элемента управления и вызвать метод для создания события. В качестве меры оптимизации код также определяет, имеются ли прослушиватели для этого типа событий. Создание событий только при наличии соответствующих прослушивателей позволяет избежать лишней нагрузки и помогает сохранять должную скорость отклика элемента управления.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о модели автоматизации пользовательского интерфейса](../../../../docs/framework/ui-automation/ui-automation-overview.md)  
 [Пользовательского элемента управления NumericUpDown с темой и пример Поддержка модели автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025)  
 [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
