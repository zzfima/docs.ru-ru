---
title: Получение элементов автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, obtaining elements
- elements, UI Automation, obtaining
ms.assetid: c2caaf45-e59c-42a1-bc9b-77a6de520171
ms.openlocfilehash: 0ae4694e2efb6f6c51b279adf2851baf38785c8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446887"
---
# <a name="obtaining-ui-automation-elements"></a>Получение элементов автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе описываются различные способы получения объектов <xref:System.Windows.Automation.AutomationElement> для элементов [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .  
  
> [!CAUTION]
> Если клиентское приложение может пытаться искать элементы в собственном пользовательском интерфейсе, вы должны выполнять все вызовы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в отдельном потоке. Для получения дополнительной информации см. [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
<a name="The_Root_Element"></a>   
## <a name="root-element"></a>Элемент Root  
 Любой поиск объектов <xref:System.Windows.Automation.AutomationElement> должен иметь отправную точку. Это может быть любой элемент, включая рабочий стол, окно приложения или элемент управления.  
  
 Корневой элемент для рабочего стола, все элементы из которого являются потомками, получается из статического свойства <xref:System.Windows.Automation.AutomationElement.RootElement%2A?displayProperty=nameWithType> .  
  
> [!CAUTION]
> В целом вы должны пытаться получить только прямые потомки <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Поиск потомков может выполнять итерацию по сотням или даже тысячам элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
<a name="Using_Conditions"></a>   
## <a name="conditions"></a>Состояния  
 В большинстве методик, которые можно использовать для получения элементов [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , вы должны указывать объект <xref:System.Windows.Automation.Condition>, представляющий собой набор условий, определяющих, какие элементы нужно получить.  
  
 Простейшим условием является <xref:System.Windows.Automation.Condition.TrueCondition>, предопределенный объект, указывающий, что должны быть возвращены все элементы в области поиска. Условие<xref:System.Windows.Automation.Condition.FalseCondition>, противоположное <xref:System.Windows.Automation.Condition.TrueCondition>, менее целесообразно, так как может помешать поиску каких-либо элементов.  
  
 Три прочих предопределенных условия можно использовать отдельно или в сочетании с другими условиями: <xref:System.Windows.Automation.Automation.ContentViewCondition>, <xref:System.Windows.Automation.Automation.ControlViewCondition>и <xref:System.Windows.Automation.Automation.RawViewCondition>. Условие<xref:System.Windows.Automation.Automation.RawViewCondition>, используемое само по себе, эквивалентно <xref:System.Windows.Automation.Condition.TrueCondition>, так как оно не фильтрует элементы по их свойству <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> или <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> .  
  
 Прочие условия создаются из одного или нескольких объектов <xref:System.Windows.Automation.PropertyCondition> , каждый из которых задает значение свойства. Например, <xref:System.Windows.Automation.PropertyCondition> может указывать, что элемент включен или что он поддерживает определенный шаблон элемента управления.  
  
 Условия могут объединяться с помощью булевой логики для формирования объектов типов <xref:System.Windows.Automation.AndCondition>, <xref:System.Windows.Automation.OrCondition>и <xref:System.Windows.Automation.NotCondition>.  
  
<a name="Search_Scope"></a>   
## <a name="search-scope"></a>Область поиска  
 Поиск, выполняемый с помощью метода <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> или <xref:System.Windows.Automation.AutomationElement.FindAll%2A> , должен иметь область, а также отправную точку.  
  
 Область определяет пространство вокруг отправной точки, в котором производится поиск. Область может включать сам элемент, элементы того же уровня, его родительский элемент, его предки, его непосредственные дочерние элементы и его потомки.  
  
 Область поиска определяется побитовым сочетанием значений из перечисления <xref:System.Windows.Automation.TreeScope> .  
  
<a name="Finding_a_Known_Element"></a>   
## <a name="finding-a-known-element"></a>Поиск известного элемента  
 Чтобы найти известный элемент, определяемый по его свойству <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>или некоторому другому свойству или сочетанию свойств, проще всего использовать метод <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> . Если искомый элемент — окно приложения, отправной точкой поиска может быть <xref:System.Windows.Automation.AutomationElement.RootElement%2A>.  
  
 Этот способ поиска элементов [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] особенно целесообразен в скриптах автоматических тестов.  
  
<a name="Finding_Elements_in_a_Subtree"></a>   
## <a name="finding-elements-in-a-subtree"></a>Поиск элементов в поддереве  
 Чтобы найти все элементы, удовлетворяющие определенным условиям, относящиеся к известному элементу, можно использовать метод <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. Например, этот метод можно использовать для извлечения элементов списка или элементов меню из списка или меню, а также для поиска всех элементов управления в диалоговом окне.  
  
<a name="Walking_a_Subtree"></a>   
## <a name="walking-a-subtree"></a>Обход поддерева  
 Если нет предварительных сведений о приложениях, с которыми может использоваться ваш клиент, вы можете построить поддерево всех интересующих элементов с помощью класса <xref:System.Windows.Automation.TreeWalker> . Приложение может сделать это в ответ на событие изменения фокуса; т. е. когда приложение или элемент управления получает фокус ввода, клиент автоматизации пользовательского интерфейса проверяет дочерние элементы и, возможно, все потомки элемента, получившего фокус.  
  
 Кроме того, <xref:System.Windows.Automation.TreeWalker> может использоваться для определения предков элемента. Например, обходя дерево, можно определить родительское окно элемента управления.  
  
 Вы можете использовать <xref:System.Windows.Automation.TreeWalker> либо создавая объект класса (определяющий интересующие элементы, передавая <xref:System.Windows.Automation.Condition>), либо используя один из следующих предопределенных объектов, которые заданы как поля <xref:System.Windows.Automation.TreeWalker>.  
  
|||  
|-|-|  
|<xref:System.Windows.Automation.TreeWalker.ContentViewWalker>|Поиск только тех элементов, свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> которых имеет значение `true`.|  
|<xref:System.Windows.Automation.TreeWalker.ControlViewWalker>|Поиск только тех элементов, свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> которых имеет значение `true`.|  
|<xref:System.Windows.Automation.TreeWalker.RawViewWalker>|Поиск всех элементов.|  
  
 После получения объекта <xref:System.Windows.Automation.TreeWalker>использовать его несложно. Просто вызывайте методы `Get` для навигации по элементам поддерева.  
  
 Метод <xref:System.Windows.Automation.TreeWalker.Normalize%2A> может использоваться для перехода к элементу в поддереве из другого элемента, который не является частью представления. Предположим, что вы создали представление поддерева с помощью <xref:System.Windows.Automation.TreeWalker.ContentViewWalker>. Далее ваше приложение получает уведомление, что полоса прокрутки получила фокус ввода. Поскольку полоса прокрутки не является элементом содержимого, она отсутствует в представлении поддерева. Однако вы можете передать элемент <xref:System.Windows.Automation.AutomationElement> , представляющий полосу прокрутки, в метод <xref:System.Windows.Automation.TreeWalker.Normalize%2A> и получить его ближайшего предка, который находится в представлении содержимого.  
  
<a name="Other_Ways_to_Retrieve_an_Element"></a>   
## <a name="other-ways-to-retrieve-an-element"></a>Другие способы получения элемента  
 В дополнение к поиску и навигации вы можете получать элемент <xref:System.Windows.Automation.AutomationElement> следующими способами.  
  
### <a name="from-an-event"></a>Из события  
 Когда приложение получает событие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , в качестве исходного объекта в обработчик событий передается <xref:System.Windows.Automation.AutomationElement>. Например, если вы подписаны на события изменения фокуса, в качестве исходного объекта в ваш <xref:System.Windows.Automation.AutomationFocusChangedEventHandler> передается элемент, который получил фокус.  
  
 Дополнительные сведения см. в разделе [Subscribe to UI Automation Events](subscribe-to-ui-automation-events.md).  
  
### <a name="from-a-point"></a>Из точки  
 Если имеются координаты экрана (например, позиция курсора), можно получить <xref:System.Windows.Automation.AutomationElement> с помощью статического метода <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> .  
  
### <a name="from-a-window-handle"></a>Из дескриптора окна  
 Для получения <xref:System.Windows.Automation.AutomationElement> из HWND используйте статический метод <xref:System.Windows.Automation.AutomationElement.FromHandle%2A> .  
  
### <a name="from-the-focused-control"></a>Из элемента управления с фокусом  
 Вы можете получить <xref:System.Windows.Automation.AutomationElement> , представляющий элемент управления с фокусом, из статического свойства <xref:System.Windows.Automation.AutomationElement.FocusedElement%2A> .  
  
## <a name="see-also"></a>См. также:

- [Нахождение элемента модели автоматизации пользовательского интерфейса в зависимости от состояния свойства](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Навигация между элементами модели автоматизации пользовательского интерфейса с помощью TreeWalker](navigate-among-ui-automation-elements-with-treewalker.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
