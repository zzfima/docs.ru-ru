---
title: Свойства автоматизации пользовательского интерфейса для клиентов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, UI Automation clients
- UI Automation, client properties
ms.assetid: 255905af-0b17-485c-93d4-8a2db2a6524b
ms.openlocfilehash: 3ef1e7c6e21f30c5bdea096003f192c38059ab2e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441359"
---
# <a name="ui-automation-properties-for-clients"></a>Свойства автоматизации пользовательского интерфейса для клиентов
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом обзоре даются общие сведения о свойствах [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , предоставляемых клиентским приложениям модели автоматизации пользовательского интерфейса.  
  
 Свойства в объектах <xref:System.Windows.Automation.AutomationElement> содержат информацию об элементах [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , обычно об элементах управления. Свойства <xref:System.Windows.Automation.AutomationElement> являются универсальными, т. е. не относящимися только к определенному типу элемента управления. Многие из этих свойств представлены в структуре <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation> .  
  
 Шаблоны элементов управления также обладают свойствами. Свойства шаблонов элементов управления относятся к конкретному шаблону. Например, <xref:System.Windows.Automation.ScrollPattern> имеет свойства, которые позволяют клиентскому приложению обнаружить, является ли окно горизонтально или вертикально прокручиваемым, а также размеры текущего представления и позиции прокрутки. Шаблоны элементов управления предоставляют все свои свойства через структуру; например <xref:System.Windows.Automation.ScrollPattern.ScrollPatternInformation>.  
  
 Свойства[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предназначены только для чтения. Чтобы задать свойства элемента управления, вы должны использовать методы соответствующего шаблона элемента управления. Например, используйте метод <xref:System.Windows.Automation.ScrollPattern.Scroll%2A> для изменения значений позиции прокручиваемого окна.  
  
 Для повышения производительности значения свойств и шаблоны элементов управления могут кэшироваться при получении объектов <xref:System.Windows.Automation.AutomationElement> . For more information, see [Caching in UI Automation Clients](caching-in-ui-automation-clients.md).  
  
## <a name="property-ids"></a>Идентификаторы свойств  
 Property identifiers (IDs) are unique, constant values that are encapsulated in <xref:System.Windows.Automation.AutomationProperty> objects. UI Automation client applications get these IDs from the <xref:System.Windows.Automation.AutomationElement> class or from the appropriate control pattern class, such as <xref:System.Windows.Automation.ScrollPattern>. Поставщики автоматизации пользовательского интерфейса получают их из <xref:System.Windows.Automation.AutomationElementIdentifiers> или из одного из классов идентификаторов шаблонов элементов управления, такого как <xref:System.Windows.Automation.ScrollPatternIdentifiers>.  
  
 Числовой <xref:System.Windows.Automation.AutomationIdentifier.Id%2A> объекта <xref:System.Windows.Automation.AutomationProperty> используется поставщиками для идентификации свойств, которые запрашиваются в методе <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A?displayProperty=nameWithType> . В общем случае клиентским приложениям не требуется проверять <xref:System.Windows.Automation.AutomationIdentifier.Id%2A>. <xref:System.Windows.Automation.AutomationIdentifier.ProgrammaticName%2A> используется только для целей отладки и диагностики.  
  
## <a name="property-conditions"></a>Условия свойств  
 The property IDs are used in constructing <xref:System.Windows.Automation.PropertyCondition> objects used to find <xref:System.Windows.Automation.AutomationElement> objects. Например, может потребоваться найти <xref:System.Windows.Automation.AutomationElement> с определенным именем или все включенные элементы управления. Каждое <xref:System.Windows.Automation.PropertyCondition> определяет идентификатор <xref:System.Windows.Automation.AutomationProperty> и значение, которому свойство должно соответствовать.  
  
 Дополнительные сведения см. в следующих справочных разделах.  
  
- <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.FindAll%2A>  
  
- <xref:System.Windows.Automation.TreeWalker.Condition%2A>  
  
## <a name="retrieving-properties"></a>Получение свойств  
 Некоторые свойства <xref:System.Windows.Automation.AutomationElement> и все свойства класса шаблонов элементов управления представляются как вложенные свойства `Current` или свойство `Cached` элемента <xref:System.Windows.Automation.AutomationElement> или объекта шаблона элемента управления.  
  
 Кроме того, любое свойство <xref:System.Windows.Automation.AutomationElement> или шаблона элемента управления, включая свойство, недоступное в структуре <xref:System.Windows.Automation.AutomationElement.Cached%2A> или <xref:System.Windows.Automation.AutomationElement.Current%2A> , можно получить с помощью одного из следующих методов.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>  
  
 Эти методы обеспечивают несколько улучшенную производительность, а также доступ к полному набору свойств.  
  
 В следующем примере кода показаны два способа получения свойства в <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#121](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#121)]
 [!code-vb[UIAClient_snip#121](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#121)]  
  
 Для получения свойств шаблонов элементов управления, поддерживаемых <xref:System.Windows.Automation.AutomationElement>, вам не нужно получать объект шаблона элемента управления. Просто передайте один из идентификаторов свойств шаблона в метод.  
  
 В следующем примере кода показаны два способа получения свойства в шаблоне элемента управления.  
  
 [!code-csharp[UIAClient_snip#122](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#122)]
 [!code-vb[UIAClient_snip#122](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#122)]  
  
 Методы `Get` возвращают <xref:System.Object>. Прежде чем использовать это значение, приложение должно привести возвращенный объект к соответствующему типу.  
  
## <a name="default-property-values"></a>Значения свойств по умолчанию  
 Если поставщик автоматизации пользовательского интерфейса не реализует свойство, система [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может предоставить значение по умолчанию. Например, если поставщик для элемента управления не поддерживает свойство, идентифицируемое <xref:System.Windows.Automation.AutomationElement.HelpTextProperty>, то [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] возвращает пустую строку. Аналогично, если поставщик не поддерживает свойство, идентифицируемое <xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] возвращает значение `false`.  
  
 Это поведение можно изменить с помощью перегрузок метода <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> и <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> . При указании `true` в качестве второго параметра [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не возвращает значение по умолчанию, но вместо этого возвращает специальное значение <xref:System.Windows.Automation.AutomationElement.NotSupported>.  
  
 В следующем примере код пытается извлечь свойство из элемента, и если это свойство не поддерживается, вместо него используется значение, определенное приложением.  
  
 [!code-csharp[UIAClient_snip#123](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#123)]
 [!code-vb[UIAClient_snip#123](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#123)]  
  
 Чтобы определить, какие свойства поддерживаются элементом, используйте метод <xref:System.Windows.Automation.AutomationElement.GetSupportedProperties%2A>. Он возвращает массив идентификаторов <xref:System.Windows.Automation.AutomationProperty> .  
  
## <a name="property-changed-events"></a>События изменения свойств  
 При изменении значения свойства в <xref:System.Windows.Automation.AutomationElement> или в шаблоне элемента управления вызывается событие. Приложения может подписаться на такие события путем вызова метода <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>, предоставив массив идентификаторов <xref:System.Windows.Automation.AutomationProperty> в качестве последнего параметра, чтобы указать интересующие свойства.  
  
 В <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>можно обнаружить свойство, которое было изменено, проверив член <xref:System.Windows.Automation.AutomationPropertyChangedEventArgs.Property%2A> аргументов события. Эти аргументы также содержат старое и новое значения измененного свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Эти значения имеют тип <xref:System.Object> , и перед использованием их необходимо привести к правильному типу.  
  
## <a name="additional-automationelement-properties"></a>Дополнительные свойства AutomationElement  
 Помимо структур свойств <xref:System.Windows.Automation.AutomationElement.Current%2A> и <xref:System.Windows.Automation.AutomationElement.Cached%2A> , <xref:System.Windows.Automation.AutomationElement> имеет следующие свойства, которые можно получить с помощью простых методов доступа к свойствам.  
  
|свойство;|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Automation.AutomationElement.CachedChildren%2A>|Коллекция дочерних объектов <xref:System.Windows.Automation.AutomationElement> , находящихся в кэше.|  
|<xref:System.Windows.Automation.AutomationElement.CachedParent%2A>|Родительский объект <xref:System.Windows.Automation.AutomationElement> , находящийся в кэше.|  
|<xref:System.Windows.Automation.AutomationElement.FocusedElement%2A>|(Статическое свойство) <xref:System.Windows.Automation.AutomationElement> , имеющий фокус ввода.|  
|<xref:System.Windows.Automation.AutomationElement.RootElement%2A>|(Статическое свойство) Корневой <xref:System.Windows.Automation.AutomationElement>, имеющий фокус ввода.|  
  
## <a name="see-also"></a>См. также

- [Кэширование в клиентах автоматизации пользовательского интерфейса](caching-in-ui-automation-clients.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
- [Подписка на события модели автоматизации пользовательского интерфейса](subscribe-to-ui-automation-events.md)
