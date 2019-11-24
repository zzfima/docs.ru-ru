---
title: Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера
ms.date: 03/30/2017
helpviewer_keywords:
- server-side UI Automation provider implementation
- UI Automation, server-side provider implementation
- provider implementation, UI Automation
ms.assetid: 6acc6d08-bd67-4e2e-915c-9c1d34eb86fe
ms.openlocfilehash: 35754d49bf223e7afcdec32e8b24cfb749f48aa6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446846"
---
# <a name="server-side-ui-automation-provider-implementation"></a>Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе описывается реализация серверного поставщика автоматизации пользовательского интерфейса для пользовательского элемента управления.

The implementation for Windows Presentation Foundation (WPF) elements and non-[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] elements (such as those designed for [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]) is fundamentally different. Элементы[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] обеспечивают поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] с помощью класса, производного от <xref:System.Windows.Automation.Peers.AutomationPeer>. Элементы, отличные от[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] , обеспечивает поддержку с помощью реализаций интерфейсов поставщика.

<a name="Security_Considerations"></a>

## <a name="security-considerations"></a>Вопросы безопасности

Поставщики должны быть написаны так, чтобы они могли работать в среде с частичным доверием. Поскольку библиотека UIAutomationClient.dll не настроена для запуска в режиме частичного доверия, код поставщика не должен ссылаться эту сборку. Если это происходит, код может выполняться в среде с полным доверием, но в среде с частичным доверием произойдет сбой.

В частности, не используйте поля из классов в UIAutomationClient.dll, такие как в <xref:System.Windows.Automation.AutomationElement>. Вместо этого используйте эквивалентные поля из классов в UIAutomationTypes.dll, такие как <xref:System.Windows.Automation.AutomationElementIdentifiers>.

<a name="Provider_Implementation_by_WPF_Elements"></a>

## <a name="provider-implementation-by-windows-presentation-foundation-elements"></a>Реализация поставщика элементами Windows Presentation Foundation

Дополнительные сведения по этой теме см. в разделе [Модель автоматизации пользовательского интерфейса пользовательского элемента управления WPF](../wpf/controls/ui-automation-of-a-wpf-custom-control.md).

<a name="Provider_Implementation_by_non_WPF_Elements"></a>

## <a name="provider-implementation-by-non-wpf-elements"></a>Реализация поставщика элементами, отличными от WPF

Пользовательские элементы управления, которые не являются частью платформы [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] , но написаны в управляемом коде (чаще всего это элементы управления [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] ), обеспечивают поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] за счет реализации интерфейсов. Каждый элемент должен реализовывать по крайней мере один из интерфейсов, перечисленных в первой таблице в следующем разделе. Кроме того, если элемент поддерживает один или несколько шаблонов элементов управления, он должен реализовать соответствующий интерфейс для каждого шаблона элемента управления.

Проект поставщика [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должен содержать ссылки на следующие сборки:

- UIAutomationProviders.dll

- UIAutomationTypes.dll

- WindowsBase.dll

<a name="Provider_Interfaces"></a>

### <a name="provider-interfaces"></a>Интерфейсы поставщика

Каждый поставщик [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должен реализовывать один из следующих интерфейсов.

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderSimple>|Предоставляет функциональные возможности для простого элемента управления, размещенного в окне, включая поддержку для шаблонов и свойств элементов управления.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragment>|Наследует от <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>. Добавляет функциональные возможности для элемента в сложном элементе управления, включая навигацию внутри фрагмента, установку фокуса и возврат ограничивающего прямоугольника элемента.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>|Наследует от <xref:System.Windows.Automation.Provider.IRawElementProviderFragment>. Добавляет функциональные возможности для корневого элемента в сложном элементе управления, включая поиск дочернего элемента по указанным координатам и установку состояния фокуса для всего элемента управления.|

Следующие интерфейсы поддерживают добавленные функциональные возможности, но необязательно должны быть реализованы.

|Интерфейс|Описание|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|Позволяет поставщику отслеживать запросы событий.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride>|Позволяет изменять положение элементов на основе окна в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] фрагмента.|

Все другие интерфейсы в пространстве имен <xref:System.Windows.Automation.Provider> используются для поддержки шаблона элемента управления.

<a name="Requirements_for_Non_WPF_Providers"></a>

### <a name="requirements-for-non-wpf-providers"></a>Требования для поставщиков, отличных от WPF

Для взаимодействия с [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]элемент управления должен реализовать следующие основные функциональные области:

|Функция|Реализация|
|-------------------|--------------------|
|Предоставление поставщика для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|В ответ на сообщение WM_GETOBJECT, отправленное окну элемента управления, возвращается объект, реализующий <xref:System.Windows.Automation.Provider.IRawElementProviderSimple> (или производный интерфейс). Для фрагментов это должен быть поставщик для корневого фрагмента.|
|Указание значений свойств|Реализуйте <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A> для предоставления или переопределения значений.|
|Включение клиента для взаимодействия с элементом управления|Реализуйте интерфейсы, поддерживающие шаблоны элементов управления, такие как <xref:System.Windows.Automation.Provider.IInvokeProvider>. Верните эти поставщики шаблонов в реализации <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A>.|
|Создание событий|Вызовите один из статических методов <xref:System.Windows.Automation.Provider.AutomationInteropProvider> , чтобы создать событие, которое клиент может прослушивать.|
|Включение навигации и установка фокуса внутри фрагмента|Реализуйте <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> для каждого элемента в фрагменте. (Необязательно для элементов, которые не являются частью фрагмента.)|
|Включение установки фокуса и поиска дочерних элементов в фрагменте|Реализуйте расширение <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>. (Необязательно для корневых элементов фрагмента.)|

<a name="Property_Values_in_Non_WPF_Providers"></a>

### <a name="property-values-in-non-wpf-providers"></a>Значения свойств в поставщиках, отличных от WPF

Поставщики[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для пользовательских элементов управления должны поддерживать определенные свойства, которые могут использовать система автоматизации и клиентские приложения. Для элементов, которые располагаются в окнах (HWND), [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может получить некоторые свойства от поставщика окна по умолчанию, но другие необходимо получить от пользовательского поставщика.

Поставщикам для элементов управления на основе HWND обычно не требуется предоставлять следующие свойства (определяется значениями полей):

- <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ProcessIdProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClassNameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.HasKeyboardFocusProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty>

> [!NOTE]
> Простой элемент <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty> или корневой элемент фрагмента, размещенного в окне, извлекается из окна. Однако элементам фрагмента ниже корневого элемента (например, элементы списка в поле со списком) необходимо предоставлять собственные идентификаторы. Для получения дополнительной информации см. <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.GetRuntimeId%2A>.
>
> Для поставщиков, размещенных в элементе управления <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty> , должен возвращаться [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] . В этом случае поставщику окна по умолчанию может не удастся получить правильное значение.
>
> <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> обычно предоставляется поставщиком главного окна. Например, если пользовательский элемент управления является производным от <xref:System.Windows.Forms.Control>, имя будет производным от свойства `Text` элемента управления.

Пример кода см. в разделе [Return Properties from a UI Automation Provider](return-properties-from-a-ui-automation-provider.md).

<a name="Events_in_Non_WPF_Providers"></a>

### <a name="events-in-non-wpf-providers"></a>События в поставщиках, отличных от WPF

Поставщики[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] должны вызывать события, чтобы уведомлять клиентские приложения об изменениях состояния пользовательского интерфейса. Для создания событий используются следующие методы.

|Метод|Описание|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationEvent%2A>|Создает различные события, включая события, вызываемые шаблонами элементов управления.|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationPropertyChangedEvent%2A>|Вызывает событие при изменении свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseStructureChangedEvent%2A>|Вызывает событие при изменении структуры дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , например при удалении или добавлении элемента.|

Событие предназначено для уведомления клиента о каких-то действиях, происходящих в [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], независимо от того, инициируется ли действие самой системой [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Например, событие, обозначенное <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> , должно инициироваться при каждом вызове элемента управления, например когда пользователь вводит данные или клиентское приложение вызывает <xref:System.Windows.Automation.InvokePattern.Invoke%2A>.

Для оптимизации производительности поставщик можно выборочно вызывать события или вообще не создавать события, если отсутствует клиентское приложение, зарегистрированное для их получения. Для оптимизации используются следующие методы.

|Метод|Описание|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A>|Это статическое свойство указывает, подписано ли какое-либо клиентское приложение на события [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|Реализация поставщика этого интерфейса в корневом элементе фрагмента позволяет ему знать, когда клиенты регистрируют и отменяют регистрацию обработчиков событий для событий в фрагменте.|

<a name="Non_WPF_Provider_Navigation"></a>

### <a name="non-wpf-provider-navigation"></a>Навигация в поставщике, отличном от WPF

Поставщики простых элементов управления, таких как пользовательская кнопка, размещенная в окне (HWND), не требуется поддерживать навигацию в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Переход между элемент обрабатывается поставщиком по умолчанию для главного окна, который указывается в реализации <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>. Однако при реализации поставщика сложного пользовательского элемента управления необходимо поддерживать навигацию между корневым узлом фрагмента и его потомками, а также между одноуровневыми узлами.

> [!NOTE]
> Элементы фрагмента, отличные от корневого, должны возвращать ссылку `null` из <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>, так как они размещаются не непосредственно в окне, а никакой поставщик по умолчанию не может поддерживать переходы между ними.

Структура фрагмента определяется реализацией <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A>. Для каждого возможного направления из каждого фрагмента этот метод возвращает объект поставщика для элемента в указанном направлении. Если в этом направлении нет элемента, метод возвращает ссылку `null` .

Корневой элемент фрагмента поддерживает переход только к дочерним элементам. Например, поле со списком возвращает первый элемент в списке, если задано направление <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild>, и последний элемент, если задано направление <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>. Корневой элемент фрагмента не поддерживает переход к родительскому элементу или одноуровневым элементам. Этим управляет поставщик главного окна.

Элементы фрагмента, отличные от корневого, должны поддерживать переходы к родительскому элементу, а также любым одноуровневым и дочерним элементам.

<a name="Non_WPF_Provider_Reparenting"></a>

### <a name="non-wpf-provider-reparenting"></a>Переподчинение поставщика, отличного от WPF

Всплывающие окна — это фактически окна верхнего уровня, поэтому по умолчанию они отображаются в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] как дочерние элементы рабочего стола. Однако во многих случаях всплывающие окна логически являются потомками других элементов управления. Например, раскрывающийся список поля со списком логически является дочерним элементом поля со списком. Аналогичным образом всплывающее окно меню логически является дочерним элементом меню. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] обеспечивает поддержку переподчинения всплывающих окон, чтобы они отображались как дочерние элементы связанного элемента управления.

Переподчинение всплывающего окна:

1. Создайте поставщик для всплывающего окна. Для этого класс всплывающего окна должен быть известен заранее.

2. Реализуйте все свойства и шаблоны для всплывающего окна так, будто бы оно является элементом управления.

3. Реализуйте свойство <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A> , возвращающее значение, полученное от <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>, где параметр — это дескриптор всплывающего окна.

4. Реализуйте <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> для всплывающего окна и его родительского элемента, чтобы переход от логического родительского элемента к логическим дочерних элементов, а также между одноуровневыми потомками обрабатывался правильно.

Когда модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] обнаруживает всплывающее окно, она распознает, что навигация по умолчанию переопределена, и пропускает всплывающее окно, если оно обнаружено как дочерний элемент рабочего стола. Вместо этого узел будет доступен только через фрагмент.

Переподчинение не подходит для случаев, когда в элементе управления может разместиться окно любого класса. Например, главная панель может содержать любой тип HWND в своей зоне. Для обработки таких случаев [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] поддерживает альтернативную форму перемещения HWND, как описано в следующем разделе.

<a name="Non_WPF_Provider_Repositioning"></a>

### <a name="non-wpf-provider-repositioning"></a>Изменение положения поставщика, отличного от WPF

Фрагменты[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] могут содержать два или более элементов, каждый из которых размещается в окне (HWND). Так как у каждого HWND есть собственный поставщик по умолчанию, который рассматривает HWND как дочерний элемент содержащего его HWND, дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] по умолчанию будет отображать HWND в фрагменте как дочерний элемент родительского окна. В большинстве случаев это желательное поведение, но иногда оно может привести к путанице, поскольку не соответствует логической структуре [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].

Хорошим примером служит элемент управления главной панели. Элемент управления главной панели содержит зоны, каждая из которых в свою очередь может содержать элемент управления на основе HWND, например панель инструментов, текстовое поле или поле со списком. Поставщик окна по умолчанию для HWND главной панели видит дескрипторы HWND элемента управления зоны как дочерние элементы, а поставщик главной панели видит эти зоны как дочерние элементы. Поскольку поставщик HWND и поставщик главной панели работают совместно и объединяют свои дочерние элементы, зоны и элементы управления HWND отображаются как дочерние элементы главной панели. Но логически только зоны должны отображаться в качестве дочерних элементов главной панели, а каждый поставщик зоны должен быть связан с поставщиком HWND по умолчанию для элемента управления, который он содержит.

Для этого поставщик корневого элемента фрагмента главной панели предоставляет набор дочерних элементов, представляющих зоны. У каждой зоны один поставщик, который может предоставлять свойства и шаблоны. В своей реализации <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>поставщик зоны возвращает поставщика окна по умолчанию для HWND элемента управления, который он получает путем вызова <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>, передавая дескриптор окна элемента управления. Наконец, поставщик корневого элемента фрагмента главной панели реализует интерфейс <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride> и в своей реализации <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride.GetOverrideProviderForHwnd%2A> возвращает соответствующий внешний поставщик для элемента управления, размещенного в указанном HWND.

## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](ui-automation-providers-overview.md)
- [Предоставление серверного поставщика автоматизации пользовательского интерфейса](expose-a-server-side-ui-automation-provider.md)
- [Возврат свойств от поставщика автоматизации пользовательского интерфейса](return-properties-from-a-ui-automation-provider.md)
- [Вызов событий из поставщика автоматизации пользовательского интерфейса](raise-events-from-a-ui-automation-provider.md)
- [Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса](enable-navigation-in-a-ui-automation-fragment-provider.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
