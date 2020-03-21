---
title: Кэширование в клиентах автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation caching in clients
- caching, UI Automation clients
ms.assetid: 94c15031-4975-43cc-bcd5-c9439ed21c9c
ms.openlocfilehash: 186ed77594aadab9e3f49ef30e559e159aee1b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180278"
---
# <a name="caching-in-ui-automation-clients"></a>Кэширование в клиентах автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе рассматривается кэширование свойств и шаблонов элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]кэширование означает предварительное получение данных. Затем к этим данным можно осуществлять доступ без дальнейшего взаимодействия между процессами. Кэширование обычно используется клиентскими приложениями модели автоматизации пользовательского интерфейса для массового извлечения свойств и шаблонов элементов управления. Затем по мере необходимости информация извлекается из кэша. Приложение периодически обновляет кэш, обычно в ответ на события, указывающие на изменение чего-нибудь в [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] .  
  
 Преимущества кэширования наиболее заметны с помощью элементов управления Windows Presentation Foundation (WPF) и пользовательских элементов управления, которые имеют поставщиков автоматизации пользовательского капитала на стороне сервера. При доступе к поставщикам клиентской стороны, таким как поставщики по умолчанию для элементов управления Win32, выгода меньше.  
  
 Кэширование происходит, когда приложение активирует <xref:System.Windows.Automation.CacheRequest> , а затем использует какой-либо метод или свойство для возврата <xref:System.Windows.Automation.AutomationElement>; например <xref:System.Windows.Automation.AutomationElement.FindFirst%2A>, <xref:System.Windows.Automation.AutomationElement.FindAll%2A>. Исключением являются методы класса <xref:System.Windows.Automation.TreeWalker> ; кэширование выполняется только в том случае, если указан <xref:System.Windows.Automation.CacheRequest> как параметр (например, <xref:System.Windows.Automation.TreeWalker.GetFirstChild%28System.Windows.Automation.AutomationElement%2CSystem.Windows.Automation.CacheRequest%29?displayProperty=nameWithType>.  
  
 Кэширование также происходит, когда вы подписываетесь на событие при активном <xref:System.Windows.Automation.CacheRequest> . Элемент <xref:System.Windows.Automation.AutomationElement> , переданный в обработчик событий как источник события, содержит кэшированные свойства и шаблоны, заданные исходным <xref:System.Windows.Automation.CacheRequest>. Любые изменения, внесенные в <xref:System.Windows.Automation.CacheRequest> после подписки на событие, не действуют.  
  
 Свойства и шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента могут кэшироваться.  
  
<a name="Options_for_Caching"></a>
## <a name="options-for-caching"></a>Параметры кэширования  
 <xref:System.Windows.Automation.CacheRequest> задает следующие параметры кэширования.  
  
<a name="Properties_to_Cache"></a>
### <a name="properties-to-cache"></a>Свойства для кэширования  
 Вы можете указать свойства для кэширования путем вызова метода <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationProperty%29> для каждого свойства перед активацией запроса.  
  
<a name="Control_Patterns_to_Cache"></a>
### <a name="control-patterns-to-cache"></a>Шаблоны элементов управления для кэширования  
 Вы можете указать шаблоны элементов управления для кэширования путем вызова метода <xref:System.Windows.Automation.CacheRequest.Add%28System.Windows.Automation.AutomationPattern%29> для каждого шаблона перед активацией запроса. При кэшировании шаблона его свойства не кэшируются автоматически; вы должны указать свойства, которые хотите кэшировать, с помощью метода <xref:System.Windows.Automation.CacheRequest.Add%2A?displayProperty=nameWithType>.  
  
<a name="Scope_of_the_Caching"></a>
### <a name="scope-and-filtering-of-caching"></a>Область и фильтрация кэширования  
 Вы можете указать элементы, свойства и шаблоны, которые нужно кэшировать, задав свойство <xref:System.Windows.Automation.CacheRequest.TreeScope%2A?displayProperty=nameWithType> перед активацией запроса. Область относится к элементам, которые извлекаются, когда запрос активен. Например, если установить только <xref:System.Windows.Automation.TreeScope.Children>, а затем извлечь <xref:System.Windows.Automation.AutomationElement>, кэшируются свойства и шаблоны потомков этого элемента, но не его собственные. Чтобы кэширование выполнялось для самого полученного элемента, необходимо включить <xref:System.Windows.Automation.TreeScope.Element> в свойство <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> . Невозможно установить в качестве области <xref:System.Windows.Automation.TreeScope.Parent> или <xref:System.Windows.Automation.TreeScope.Ancestors>. Однако родительский элемент может быть кэширован, когда кэшируется дочерний элемент; см. подраздел "Получение кэшированных дочерних и родительских элементов" в этом разделе.  
  
 На объем кэширования также влияет свойство <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A?displayProperty=nameWithType> . По умолчанию кэширование выполняется только для элементов, которые отображаются в представлении элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Однако можно изменить это свойство, чтобы кэширование применялось ко всем элементам или только к элементам, отображаемым в представлении содержимого.  
  
<a name="Strength_of_the_Element_References"></a>
### <a name="strength-of-the-element-references"></a>Эффективность ссылок на элементы  
 При извлечении элемента <xref:System.Windows.Automation.AutomationElement>вы по умолчанию имеете доступ ко всем свойствам и шаблонам этого элемента, включая те, которые не были кэшированы. Однако для повышения эффективности можно указать, что ссылка на элемент относится только к кэшированным данным, задав для свойства <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> элемента <xref:System.Windows.Automation.CacheRequest> значение <xref:System.Windows.Automation.AutomationElementMode.None>. В этом случае вы не будете иметь доступ к тем свойствам и шаблонам извлеченного элемента, которые не были кэшированы. Это означает, что вы не сможете получить доступ к каким-либо свойствам с помощью <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> , или свойства `Current` элемента <xref:System.Windows.Automation.AutomationElement> , или любого шаблона элемента управления; вы также не сможете извлечь шаблон с помощью <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>. В кэшированных шаблонах вы можете вызывать методы, извлекающие свойства массива, такие как <xref:System.Windows.Automation.SelectionPattern.SelectionPatternInformation.GetSelection%2A?displayProperty=nameWithType>, но не методы, выполняющие действия в элементе управления, такие как <xref:System.Windows.Automation.InvokePattern.Invoke%2A?displayProperty=nameWithType>.  
  
 Пример приложения, которому могут не потребоваться полные ссылки на объекты, — средство чтения с экрана; оно сможет предварительно получать свойства <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> и <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> элементов в окне, но ему могут не требоваться сами объекты <xref:System.Windows.Automation.AutomationElement> .  
  
<a name="Activating_the_CacheRequest"></a>
## <a name="activating-the-cacherequest"></a>Активация CacheRequest  
 Кэширование выполняется, только когда объекты <xref:System.Windows.Automation.AutomationElement> извлекаются при активном <xref:System.Windows.Automation.CacheRequest> для текущего потока. Существует два способа активации <xref:System.Windows.Automation.CacheRequest>.  
  
 Обычно вызывается метод <xref:System.Windows.Automation.CacheRequest.Activate%2A>. Этот метод возвращает объект, реализующий <xref:System.IDisposable>. Запрос остается активным, пока объект <xref:System.IDisposable> существует. Самый простой способ контролировать срок службы объекта — `using` приложить вызов `Using` к блоку (C) или (Visual Basic). Это гарантирует, что запрос будет извлекаться из стека, даже если возникнет исключение.  
  
 Другим способом, который подходит, когда требуется вкладывать запросы кэширования, является вызов метода <xref:System.Windows.Automation.CacheRequest.Push%2A>. Этот вызов помещает запрос в стек и активирует его. Запрос остается активным, пока он не будет удален из стека методом <xref:System.Windows.Automation.CacheRequest.Pop%2A>. Запрос становится временно неактивным, если другой запрос помещается в стек; активен только верхний запрос в стеке.  
  
<a name="Retrieving_Cached_Properties"></a>
## <a name="retrieving-cached-properties"></a>Получение кэшированных свойств  
 Вы можете получать кэшированные свойства элемента с помощью следующих методов и свойств.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.Cached%2A>  
  
 Если запрошенное свойство отсутствует в кэше, возникает исключение.  
  
 <xref:System.Windows.Automation.AutomationElement.Cached%2A>, например <xref:System.Windows.Automation.AutomationElement.Current%2A>, предоставляет отдельные свойства как члены структуры. Однако вам не требуется извлекать эту структуру; с отдельными свойствами можно работать напрямую. Например, свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A> можно получить из `element.Cached.Name`, где `element` — <xref:System.Windows.Automation.AutomationElement>.  
  
<a name="Retrieving_Cached_Control_Patterns"></a>
## <a name="retrieving-cached-control-patterns"></a>Получение кэшированных шаблонов элементов управления  
 Вы можете получать кэшированные шаблоны элементов управления элемента с помощью следующих методов и свойств.  
  
- <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A>  
  
 Если шаблон не находится в кэше, <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> вызывает исключение, и метод <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> возвращает значение `false`.  
  
 Кэшированные свойства шаблона элемента управления можно получить с помощью свойства `Cached` объекта шаблона. Вы также можете получать текущие значения с помощью свойства `Current` , но только если при получении <xref:System.Windows.Automation.AutomationElementMode.None> не было указано значение <xref:System.Windows.Automation.AutomationElement> . (По умолчанию используется значение<xref:System.Windows.Automation.AutomationElementMode.Full> , и это позволяет получать доступ к текущим значениям.)  
  
<a name="Retrieving_Cached_Children_and_Parents"></a>
## <a name="retrieving-cached-children-and-parents"></a>Получение кэшированных дочерних и родительских элементов  
 Когда вы извлекаете элемент <xref:System.Windows.Automation.AutomationElement> и запрашиваете кэширование дочерних элементов данного элемента с помощью свойства <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> запроса, далее возможно получать дочерние элементы из свойства <xref:System.Windows.Automation.AutomationElement.CachedChildren%2A> извлеченного элемента.  
  
 Если элемент <xref:System.Windows.Automation.TreeScope.Element> был включен в область запроса кэширования, корневой элемент запроса впоследствии будет доступен из свойства <xref:System.Windows.Automation.AutomationElement.CachedParent%2A> любого из дочерних элементов.  
  
> [!NOTE]
> Нельзя кэшировать родителей или предков корневого элемента запроса.  
  
<a name="Updating_the_Cache"></a>
## <a name="updating-the-cache"></a>Обновление кэша  
 Кэш действителен только при условии, что ничего не изменилось в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Приложение отвечает за обновление кэша, обычно в ответ на события.  
  
 Если вы подписываетесь на событие при активном <xref:System.Windows.Automation.CacheRequest> , то получаете элемент <xref:System.Windows.Automation.AutomationElement> с обновленным кэшем в качестве источника события при каждом вызове делегата обработчика событий. Можно также обновить кэшированные данные для элемента путем вызова метода <xref:System.Windows.Automation.AutomationElement.GetUpdatedCache%2A>. Вы можете передать исходный <xref:System.Windows.Automation.CacheRequest> для обновления всей информации, которая была ранее кэширована.  
  
 Обновление кэша не изменяет свойства существующих ссылок <xref:System.Windows.Automation.AutomationElement> .  
  
## <a name="see-also"></a>См. также раздел

- [События модели автоматизации пользовательского интерфейса для клиентов](ui-automation-events-for-clients.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
- [Пример FetchTimer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771456(v=vs.90))
