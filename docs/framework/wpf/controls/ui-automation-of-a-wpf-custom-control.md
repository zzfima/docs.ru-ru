---
title: "Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "пользовательские элементы управления [WPF] применение автоматизации пользовательского интерфейса"
  - "Применение к пользовательским элементам управления специальные возможности [WPF]"
  - "пользовательские элементы управления [WPF] повышение доступности"
  - "При помощи пользовательских элементов управления автоматизации пользовательского интерфейса [WPF]"
ms.assetid: 47b310fc-fbd5-4ce2-a606-22d04c6d4911
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF
[!INCLUDE[TLA#tla_uiautomation](../../../../includes/tlasharptla-uiautomation-md.md)]предоставляет единый, общий интерфейс, который клиенты могут использовать для проверки или работы интерфейсов пользователей различных платформ и структур автоматизации. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]обеспечивает проверку качества (тестирование) кода и приложениями со специальными возможностями, например экрана, для проверки элементов пользовательского интерфейса и моделирования взаимодействия с ним пользователя из другого кода. Сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] на всех платформах, см.  
  
 В этом разделе описывается реализация серверный поставщик автоматизации пользовательского интерфейса для пользовательского элемента управления, работающего в приложении WPF. WPF поддерживает [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] посредством дерева одноранговых объектов автоматизации, которое копирует дерево элементов интерфейса пользователя. Тестовый код и приложения, которые предоставляют специальные возможности могут использовать одноранговые объекты автоматизации напрямую (для внутрипроцессного кода) или через общий интерфейс, предоставляемый [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 
  
<a name="AutomationPeerClasses"></a>   
## <a name="automation-peer-classes"></a>Одноранговые классы автоматизации  
 Элементы управления WPF поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] через дерево одноранговых классов, производных от <xref:System.Windows.Automation.Peers.AutomationPeer>. В соответствии с соглашением имена одноранговых классов начинаются с имени класса элемента управления и заканчивается на «AutomationPeer». Например <xref:System.Windows.Automation.Peers.ButtonAutomationPeer> является одноранговым классом для <xref:System.Windows.Controls.Button> класса элемента управления. Одноранговые классы примерно эквивалентны [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] типов элементов управления, но относящиеся к [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] элементы. Код автоматизации, обращающийся к приложениям WPF через [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] интерфейс не использовать напрямую, но код автоматизации в том же пространстве процесса может их использовать напрямую.  
  
<a name="BuiltInAutomationPeerClasses"></a>   
## <a name="built-in-automation-peer-classes"></a>Встроенные одноранговые классы автоматизации  
 Элементы реализуют одноранговый класс автоматизации, если они принимают действие интерфейса от пользователя или содержат сведения, требуемые пользователю приложений чтения с экрана. Не все визуальные элементы WPF имеют одноранговые автоматизации. Являются примерами классов, реализующих одноранговые автоматизации <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.TextBox>, и <xref:System.Windows.Controls.Label>. Примерами классов, не реализующих одноранговые автоматизации являются классами, производными от <xref:System.Windows.Controls.Decorator>, такие как <xref:System.Windows.Controls.Border>и классы, основанные на <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Controls.Canvas>.  
  
 Базовый <xref:System.Windows.Controls.Control> класс не имеет соответствующего однорангового класса. Если требуется, чтобы одноранговый класс соответствовал пользовательскому элементу управления, который является производным от <xref:System.Windows.Controls.Control>, необходимо создать производный класс пользовательского однорангового из <xref:System.Windows.Automation.Peers.FrameworkElementAutomationPeer>.  
  
<a name="SecurityConsiderations"></a>   
## <a name="security-considerations-for-derived-peers"></a>Вопросы безопасности для производных одноранговых классов  
 Одноранговые автоматизации должна выполняться в среде с частичным доверием. Код в сборке UIAutomationClient не настроен для выполнения в среде с частичным доверием и коде однорангового класса автоматизации не должен ссылаться на эту сборку. Вместо этого следует использовать классы в сборке UIAutomationTypes. Например, следует использовать <xref:System.Windows.Automation.AutomationElementIdentifiers> класса из сборки UIAutomationTypes, который соответствует <xref:System.Windows.Automation.AutomationElement> класса в сборке UIAutomationClient. Безопасно для ссылки на Uiautomationtypes в коде однорангового класса автоматизации.  
  
<a name="PeerNavigation"></a>   
## <a name="peer-navigation"></a>Навигация между одноранговыми классами  
 После обнаружения однорангового класса автоматизации, внутрипроцессный код может перемещаться по одноранговому дереву путем вызова объекта <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildren%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetParent%2A> методы. Перемещение между [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] элементы внутри элемента управления поддерживается реализацией однорангового узла <xref:System.Windows.Automation.Peers.AutomationPeer.GetChildrenCore%2A> метод. Система модели автоматизации пользовательского интерфейса вызывает этот метод для построения дерева подэлементов, содержащихся в элементе управления; например элементы списка в поле со списком. Значение по умолчанию <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetChildrenCore%2A?displayProperty=fullName> метод обходит визуального дерева элементов для построения дерева одноранговых классов автоматизации. Пользовательские элементы управления переопределяют этот метод для предоставления дочерних элементов клиентам автоматизации, возвращая одноранговые классы автоматизации элементов, которые передают сведения или разрешают взаимодействие с пользователем.  
  
<a name="Customizations"></a>   
## <a name="customizations-in-a-derived-peer"></a>Настройки в производном одноранговый узел  
 Все классы, производные от <xref:System.Windows.UIElement> и <xref:System.Windows.ContentElement> содержат защищенный виртуальный метод <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A>. WPF вызывает <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> для получения одноранговый объект автоматизации для каждого элемента управления. Код автоматизации можно использовать узел для получения информации о характеристиках и возможностях элемента управления и смоделировать интерактивное использование. Пользовательский элемент управления, поддерживающий автоматизацию необходимо переопределить <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> и возвратить экземпляр класса, производного от <xref:System.Windows.Automation.Peers.AutomationPeer>. Например, если пользовательский элемент управления является производным от <xref:System.Windows.Controls.Primitives.ButtonBase> класса, то объект, возвращаемый <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> должен быть производным от <xref:System.Windows.Automation.Peers.ButtonBaseAutomationPeer>.  
  
 При реализации пользовательского элемента управления, необходимо переопределить методы «Core» из базового однорангового класса автоматизации, описывающие поведение уникальны и используются только для пользовательского элемента управления.  
  
### <a name="override-oncreateautomationpeer"></a>Переопределение OnCreateAutomationPeer  
 Переопределение <xref:System.Windows.UIElement.OnCreateAutomationPeer%2A> метод для пользовательского элемента управления, чтобы он возвращал объект поставщика, который должен быть производным непосредственно или косвенно от <xref:System.Windows.Automation.Peers.AutomationPeer>.  
  
### <a name="override-getpattern"></a>Переопределение GetPattern  
 Одноранговые классы автоматизации упрощают некоторые аспекты реализации на стороне сервера [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] поставщики, но одноранговые автоматизации пользовательского элемента управления по-прежнему должны обрабатывать интерфейсы шаблонов. Как поставщики не WPF коллег поддержка шаблонов элементов управления, предоставляя реализации интерфейсов в <xref:System.Windows.Automation.Provider?displayProperty=fullName> пространства имен, таких как <xref:System.Windows.Automation.Provider.IInvokeProvider>. Можно реализовать интерфейсы шаблонов элементов управления, самим одноранговым классом или другим объектом. Реализация однорангового узла <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> возвращает объект, который поддерживает указанный шаблон. [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)]код вызывает метод <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод и указывает <xref:System.Windows.Automation.Peers.PatternInterface> значение перечисления. Переопределение метода <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> должен возвращать объект, который реализует указанный шаблон. Если элемент управления не имеет пользовательскую реализацию шаблона, можно вызвать реализацию базового типа <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> для извлечения его реализации или значение null, если шаблон не поддерживается для данного типа элемента управления. Например, пользовательский элемент управления NumericUpDown может быть присвоено значение в диапазоне, поэтому его [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] реализовать одноранговых <xref:System.Windows.Automation.Provider.IRangeValueProvider> интерфейса. В следующем примере показан способ однорангового узла <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод переопределяется, чтобы отвечать на <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> значение.  
  
 [!code-csharp[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#getpattern)]
 [!code-vb[CustomControlNumericUpDown#GetPattern](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#getpattern)]  
  
 Объект <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.GetPattern%2A> метод также можно указывать подэлемент в качестве поставщика шаблона. В следующем коде показано, как <xref:System.Windows.Controls.ItemsControl> передает обработку шаблона в одноранговый узел из своих внутренних прокрутки <xref:System.Windows.Controls.ScrollViewer> элемента управления.  
  
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
  
 Чтобы указать подэлемент для обработки шаблона, этот код возвращает объект подэлемента, создает одноранговый узел с помощью <xref:System.Windows.Automation.Peers.UIElementAutomationPeer.CreatePeerForElement%2A> задает метод, <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> свойство новый одноранговый узел для текущего однорангового узла и возвращает новый одноранговый узел. Установка <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A> на подэлемент не подэлемент будут отображаться в дереве одноранговых классов автоматизации и определяет все события, вызываемые подэлемент как исходящие из элемента управления, указанного в <xref:System.Windows.Automation.Peers.AutomationPeer.EventsSource%2A>. <xref:System.Windows.Controls.ScrollViewer> управления не отображается в дереве модели автоматизации и событий прокрутки, которые он создает, фигурирует <xref:System.Windows.Controls.ItemsControl> объекта.  
  
### <a name="override-core-methods"></a>Переопределение методов «Core»  
 Код автоматизации возвращает сведения об элементе управления посредством вызова открытых методов однорангового класса. Чтобы предоставить сведения об элементе управления, переопределите каждый метод, имена которых заканчиваются на «Базовых» при реализации элемента управления отличается от того, что предоставляемые базовый одноранговый класс автоматизации. Как минимум, необходимо реализовать <xref:System.Windows.Automation.Peers.AutomationPeer.GetClassNameCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> методов, как показано в следующем примере.  
  
 [!code-csharp[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#coreoverrides)]
 [!code-vb[CustomControlNumericUpDown#CoreOverrides](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#coreoverrides)]  
  
 Реализация <xref:System.Windows.Automation.Peers.AutomationPeer.GetAutomationControlTypeCore%2A> описывает элемент управления, возвращая <xref:System.Windows.Automation.ControlType> значение. Хотя можно вернуть <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName>, необходимо вернуть один более конкретные типы элементов управления, если это точно описывает элемент управления. Возвращаемое значение <xref:System.Windows.Automation.ControlType.Custom?displayProperty=fullName> требует дополнительной работы поставщика, чтобы реализовать [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)], и [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] клиенты не могут предвидеть структуру элемента управления, взаимодействие с клавиатурой и возможные шаблоны элементов управления.  
  
 Реализуйте <xref:System.Windows.Automation.Peers.AutomationPeer.IsContentElementCore%2A> и <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> методов ли элемент управления содержимым данных или выполняет интерактивную роль в интерфейсе пользователя (или оба). По умолчанию оба метода возвращают `true`. Эти параметры повысить удобство использования средств автоматизации, таких как программы чтения с экрана, которые могут использовать эти методы для фильтрации дерева автоматизации. Если ваш <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> метод передает обработку шаблона в подэлемент однорангового узла, одноранговых подэлемент <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> метод может возвращать значение false, чтобы скрыть одноранговых подэлемент в дереве автоматизации. Например, прокрутка в <xref:System.Windows.Controls.ListBox> обрабатывается <xref:System.Windows.Controls.ScrollViewer>и одноранговый элемент автоматизации для <xref:System.Windows.Automation.Peers.PatternInterface?displayProperty=fullName> возвращается <xref:System.Windows.Automation.Peers.AutomationPeer.GetPattern%2A> метод <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> , связанный с <xref:System.Windows.Automation.Peers.ListBoxAutomationPeer>. Таким образом <xref:System.Windows.Automation.Peers.AutomationPeer.IsControlElementCore%2A> метод <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> возвращает `false`, так что <xref:System.Windows.Automation.Peers.ScrollViewerAutomationPeer> не отображается в дереве модели автоматизации.  
  
 Одноранговый класс автоматизации должен предоставить соответствующие значения по умолчанию для элемента управления. Обратите внимание, что XAML, который ссылается на элемент управления можно переопределить реализации одноранговых классов базовых методов, включая <xref:System.Windows.Automation.AutomationProperties> атрибуты. Например, следующий код XAML создает кнопку, которая имеет два настраиваемых [!INCLUDE[TLA2#tla_uiautomation](../../../../includes/tla2sharptla-uiautomation-md.md)] свойства.  
  
```xaml  
<Button AutomationProperties.Name="Special"   
    AutomationProperties.HelpText="This is a special button."/>  
```  
  
### <a name="implement-pattern-providers"></a>Реализация поставщиков шаблонов  
 Интерфейсы, реализованные с помощью пользовательского поставщика объявлены явно, если владелец-элемент наследует непосредственно от <xref:System.Windows.Controls.Control>. Например, следующий код объявляет одноранговый узел для <xref:System.Windows.Controls.Control> , реализующий значение диапазона.  
  
```csharp  
public class RangePeer1 : FrameworkElementAutomationPeer, IRangeValueProvider { }  
```  
  
```vb  
Public Class RangePeer1  
    Inherits FrameworkElementAutomationPeer  
    Implements IRangeValueProvider  
End Class  
```  
  
 Если владелец-элемент управления является производным от определенного типа элемента управления например <xref:System.Windows.Controls.Primitives.RangeBase>, одноранговый узел может быть производным от эквивалентного производного однорангового класса. В этом случае одноранговый узел будет наследовать от класса <xref:System.Windows.Automation.Peers.RangeBaseAutomationPeer>, который предоставляет базовую реализацию <xref:System.Windows.Automation.Provider.IRangeValueProvider>. Ниже показано объявление такого однорангового узла.  
  
```csharp  
public class RangePeer2 : RangeBaseAutomationPeer { }  
```  
  
```vb  
Public Class RangePeer2  
    Inherits RangeBaseAutomationPeer  
End Class  
```  
  
 Пример реализации, в разделе [пользовательский элемент управления NumericUpDown, темы и пример поддержки автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025).  
  
### <a name="raise-events"></a>Создание событий  
 Клиенты автоматизации можно подписаться на события модели автоматизации. Пользовательские элементы управления должны сообщать об изменениях для контроля состояния путем вызова <xref:System.Windows.Automation.Peers.AutomationPeer.RaiseAutomationEvent%2A> метод. Аналогично, при изменении значения свойства вызывать <xref:System.Windows.Automation.Peers.AutomationPeer.RaisePropertyChangedEvent%2A> метод. Ниже показано, как вернуть одноранговый объект из кода элемента управления и вызвать метод для вызова события. Для оптимизации кода определяет, имеются ли прослушиватель для этого типа событий. События только при наличии прослушивателя позволяет избежать лишней нагрузки и помогает реагировало элемента управления.  
  
 [!code-csharp[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CustomControlNumericUpDown/CSharp/CustomControlLibrary/NumericUpDown.cs#raiseeventfromcontrol)]
 [!code-vb[CustomControlNumericUpDown#RaiseEventFromControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CustomControlNumericUpDown/visualbasic/customcontrollibrary/numericupdown.vb#raiseeventfromcontrol)]  
  
## <a name="see-also"></a>См. также  
 [Обзор автоматизации пользовательского интерфейса](../../../../docs/framework/ui-automation/ui-automation-overview.md)   
 [Пользовательского элемента управления NumericUpDown темы и пример поддержки автоматизации пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=160025)   
 [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)