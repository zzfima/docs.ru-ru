---
title: Автоматизация пользовательского пользовательского системы пользовательского контроля
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
ms.openlocfilehash: 9c33d0e5da70820041ba2a2881082d9f7d179fc5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187499"
---
# <a name="ui-automation-of-a-wpf-custom-control"></a>Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)] предоставляет единый общий интерфейс, который клиенты автоматизации могут использовать для проверки или использования пользовательских интерфейсов различных платформ и инфраструктур. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет как код для проверки качества (тестирования), так и приложения с поддержкой специальных возможностей, например средства чтения с экрана для проверки элементов пользовательского интерфейса и моделирования пользовательского взаимодействия с ними из другого кода. Сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на всех платформах см. в разделе, посвященном специальным возможностям.  
  
 В этом разделе описывается реализация серверного поставщика автоматизации пользовательского интерфейса для пользовательского элемента управления, применяемого в приложении WPF. WPF поддерживает [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] с помощью дерева одноранговых объектов автоматизации, которое сопутствует дереву элементов интерфейса пользователя. Тестовый код и приложения с поддержкой специальных возможностей могут использовать одноранговые объекты автоматизации напрямую (для внутрипроцессного кода) или через универсальный интерфейс, предоставляемый [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  

<a name="AutomationPeerClasses"></a>
## <a name="automation-peer-classes"></a>Одноранговые классы автоматизации  
 WPF контролирует [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] поддержку через дерево одноранговых классов, которые вытекают из <xref:System.Windows.Automation.Peers.AutomationPeer>. В соответствии с соглашением имена одноранговых классов начинаются с имени класса элемента управления, к которому добавляется строка "AutomationPeer". Например, <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> это класс одноранговых узлов для класса <xref:System.Windows.Controls.Button> управления. Классовые занятия примерно [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] эквивалентны типам управления, но специфичны для элементов WPF. Код автоматизации, обращающийся к приложениям WPF через интерфейс [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], не использует одноранговые классы автоматизации напрямую, но код автоматизации в том же пространстве процесса может использовать их напрямую.  
  
<a name="BuiltInAutomationPeerClasses"></a>
## <a name="built-in-automation-peer-classes"></a>Встроенные одноранговые классы автоматизации  
 Элементы реализуют одноранговый класс автоматизации, если они принимают взаимодействие пользователя с интерфейсом или содержат информацию, необходимую пользователям приложений для чтения с экрана. Не все визуальные элементы WPF имеют одноранговые классы автоматизации. Примеры классов, которые <xref:System.Windows.Controls.Button>реализуют аналогов автоматизации, <xref:System.Windows.Controls.TextBox>и <xref:System.Windows.Controls.Label>. Примерами классов, которые не реализуют <xref:System.Windows.Controls.Decorator>узлов автоматизации, являются классы, которые вытекают <xref:System.Windows.Controls.Border>из таких, как, и классы, основанные на, <xref:System.Windows.Controls.Panel>таких как <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.Canvas>.  
  
 Базовый <xref:System.Windows.Controls.Control> класс не имеет соответствующего класса одноранговых узлов. Если вам нужен одноранговый класс, чтобы <xref:System.Windows.Controls.Control>соответствовать пользовательскому элементу <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>управления, который вытекает из, вы должны получить пользовательский одноранговый класс из.  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations-for-derived-peers"></a>Вопросы безопасности для производных одноранговых классов  
 Одноранговые классы автоматизации должны работать в среде с частичным доверием. Код в сборке UIAutomationClient не настроен для выполнения в среде с частичным доверием и код однорангового класса автоматизации не должен ссылаться на эту сборку. Вместо этого следует использовать классы в сборке UIAutomationTypes. Например, следует использовать <xref:System.Windows.Automation.AutomationElementIdentifiers> класс из сборки UIAutomationTypes, <xref:System.Windows.Automation.AutomationElement> который соответствует классу в сборке UIAutomationClient. В коде однорангового класса автоматизации можно безопасно ссылаться на сборку UIAutomationTypes.  
  
<a name="PeerNavigation"></a>
## <a name="peer-navigation"></a>Навигация по одноранговым объектам  
 После обнаружения одноранговой системы код в процессе процесса может <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> перемещаться по дереву сверстников, вызывая объект и <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> методы. Навигация между элементами WPF в элементах управления <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> поддерживается реализацией метода одноранговой системы. Система модели автоматизации пользовательского интерфейса вызывает этот метод для построения дерева подэлементов, содержащихся в элементе управления (например, элементов списка в элементе управления "список" (ListBox)). Метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=nameWithType> по умолчанию пересекает визуальное дерево элементов для построения дерева узлов автоматизации. Пользовательские элементы управления переопределяют этот метод для предоставления дочерних элементов клиентам автоматизации, возвращая одноранговые объекты автоматизации элементов, которые передают информацию или разрешают взаимодействие с пользователем.  
  
<a name="Customizations"></a>
## <a name="customizations-in-a-derived-peer"></a>Настройка производного однорангового класса  
 Все классы, <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> которые вытекают <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>из защищенного виртуального метода и содержат их. WPF <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> призывает получить объект управления автоматизации для каждого элемента управления. Код автоматизации может использовать одноранговый объект для получения информации о характеристиках и функциях элемента управления и моделирования интерактивного использования. Пользовательский элемент управления, поддерживающий автоматизацию, должен <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> переопределить <xref:System.Windows.Automation.Peers.AutomationPeer>и вернуть экземпляр класса, который происходит от . Например, если пользовательский элемент <xref:System.Windows.Controls.Primitives.ButtonBase> управления происходит от класса, то объект, возвращенный, <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> должен вытекать из <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 При реализации пользовательского элемента управления необходимо переопределить методы "Core" базового однорангового класса автоматизации, которые описывают специфическое поведение пользовательского элемента управления.  
  
### <a name="override-oncreateautomationpeer"></a>Переопределение метода OnCreateAutomationPeer  
 Переопределить <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> метод для пользовательского управления так, что он возвращает ваш объект <xref:System.Windows.Automation.Peers.AutomationPeer>поставщика, который должен получить прямо или косвенно от .  
  
### <a name="override-getpattern"></a>Переопределение метода GetPattern  
 Одноранговые классы автоматизации упрощают некоторые аспекты реализации поставщиков [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на стороне сервера, но одноранговые классы автоматизации пользовательских элементов управления по-прежнему должны обрабатывать интерфейсы шаблонов. Как и не-поставщики WPF, узлы поддерживают шаблоны управления, предоставляя реализации интерфейсов в пространстве <xref:System.Windows.Automation.Provider?displayProperty=nameWithType> имен, такие как <xref:System.Windows.Automation.Provider.IInvokeProvider>. Интерфейсы шаблонов элементов управления могут быть реализованы самим одноранговым классом или другим объектом. Реализация одноранговой <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> реализации возвращает объект, поддерживающий указанный шаблон. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]код вызывает <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод и определяет <xref:System.Windows.Automation.Peers.PatternInterface> значение перечисления. Переопределение <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> должно вернуть объект, реализуемый в указанном шаблоне. Если элемент управления не имеет пользовательской реализации шаблона, можно вызвать реализацию базового <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> типа, чтобы получить его реализацию или свести на нет, если шаблон не поддерживается для этого типа управления. Например, пользовательский элемент управления NumericUpDown может быть установлен [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на значение <xref:System.Windows.Automation.Provider.IRangeValueProvider> в диапазоне, так что его одноранговый элемент будет реализовывать интерфейс. Следующий пример показывает, как <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод узла переопределяется, чтобы ответить на <xref:System.Windows.Automation.Peers.PatternInterface.RangeValue?displayProperty=nameWithType> значение.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> может также указать подэлемент в качестве поставщика шаблонов. Следующий код <xref:System.Windows.Controls.ItemsControl> показывает, как передача обработки <xref:System.Windows.Controls.ScrollViewer> шаблона прокрутки в одноранговой элемент его внутреннего управления.  
  
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
  
 Чтобы указать подэлемент для обработки шаблонов, этот код получает <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> объект подэлемента, создает одноранговый метод, устанавливает <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> свойство нового однорангового элемента к текущему шаблону и возвращает новый одноранговый узл. Установка <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> на подэлемент предотвращает появление подэлемента в дереве зародыша автоматизации и определяет все события, <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>поднятые подэлементом, как исходящие из элемента, указанного в. Элемент <xref:System.Windows.Controls.ScrollViewer> управления не отображается в дереве автоматизации, и события прокрутки, которые он генерирует, по-видимому, происходят от <xref:System.Windows.Controls.ItemsControl> объекта.  
  
### <a name="override-core-methods"></a>Переопределение методов "Core"  
 Код автоматизации получает информацию о вашем элементе управления, вызывая открытые методы однорангового класса. Чтобы предоставить информацию о своем элементе управления, переопределите все методы, имена которых заканчиваются на "Core", если ваша реализация элемента управления отличается от той, которая имеется в базовом одноранговом классе автоматизации. Как минимум, ваш элемент <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> управления <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> должен реализовать и методы, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Реализация <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> описывает ваш контроль, <xref:System.Windows.Automation.ControlType> возвращая значение. Хотя вы <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType>можете вернуться, вы должны вернуть один из более конкретных типов управления, если он точно описывает ваш контроль. Возвратное <xref:System.Windows.Automation.ControlType.Custom?displayProperty=nameWithType> значение требует дополнительной работы [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]для [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] поставщика для реализации, и клиентские продукты не могут предвидеть структуру управления, взаимодействие клавиатуры и возможные шаблоны управления.  
  
 Реализация <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> методы, чтобы указать, содержит ли ваш элемент управления содержимое данных или выполняет интерактивную роль в пользовательском интерфейсе (или и то, и другое). По умолчанию оба метода возвращают значение `true`. Эти параметры повышают удобство использования средств автоматизации (например, средств чтения с экрана), которые могут использовать эти методы для фильтрации дерева автоматизации. Если <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> метод передает обработку шаблона в одноранговый <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> узла подэлемента, метод узла подэлемента может вернуться ложным, чтобы скрыть одноранговый элемент подэлемента от дерева автоматизации. Например, прокрутка <xref:System.Windows.Controls.ListBox> в <xref:System.Windows.Controls.ScrollViewer>ампирирована, а <xref:System.Windows.Automation.Peers.PatternInterface.Scroll?displayProperty=nameWithType> узловая <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> автоматизация <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> возвращается методом, связанным с <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Таким <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> образом, метод <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> `false`возврата , <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> так что не появляется в дерево автоматизации.  
  
 Одноранговый класс автоматизации должен предоставлять необходимые значения по умолчанию для вашего элемента управления. Обратите внимание, что XAML, который ссылается на элемент управления, <xref:System.Windows.Automation.AutomationProperties> может переопределить одноранговые реализации основных методов, включив атрибуты. Например, следующий код XAML создает кнопку, которая имеет два настраиваемых свойства [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
```xaml  
<Button AutomationProperties.Name="Special"
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Реализация поставщиков шаблонов  
 Интерфейсы, реализованные пользовательским поставщиком, прямо заявляются, если <xref:System.Windows.Controls.Control>элемент владения вытекает непосредственно из . Например, следующий код объявляет одноранговый для значения <xref:System.Windows.Controls.Control> диапазона.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Если элемент управления является результатом определенного типа <xref:System.Windows.Controls.Primitives.RangeBase>управления, такого как, уравновештый элемент может быть получен из эквивалентного производного однорангового класса. В этом случае, одноранговой будет вытекать <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer> <xref:System.Windows.Automation.Provider.IRangeValueProvider>из , который поставляет базовую реализацию . В следующем коде показано объявление такого однорангового класса.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
Например, в реализации см. исходный код [C-](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp) или [Visual Basic,](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic) который реализует и потребляет пользовательский элемент управления NumericUpDown.  
  
### <a name="raise-events"></a>Создание событий  
 Клиенты автоматизации могут подписаться на события автоматизации. Пользовательские элементы управления должны сообщать <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> об изменениях в состоянии управления, вызывая метод. Аналогичным образом, при изменении <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> значения свойства позвоните в метод. В приведенном ниже коде показано, как получить одноранговый объект из кода элемента управления и вызвать метод для создания события. В качестве меры оптимизации код также определяет, имеются ли прослушиватели для этого типа событий. Создание событий только при наличии соответствующих прослушивателей позволяет избежать лишней нагрузки и помогает сохранять должную скорость отклика элемента управления.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о модели автоматизации пользовательского интерфейса](../../ui-automation/ui-automation-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../ui-automation/server-side-ui-automation-provider-implementation.md)
- [Пользовательский контроль NumericUpDown на GitHub](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp)  
- [Пользовательский контроль NumericUpDown (Visual Basic) на GitHub](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic)
