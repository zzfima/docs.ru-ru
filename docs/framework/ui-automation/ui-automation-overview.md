---
title: Общие сведения о модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, overview
- user interface, see UI
- accessibility, UI automation
ms.assetid: 65847654-9994-4a9e-b36d-2dd5d998770b
ms.openlocfilehash: 6f938302967e1b519105769717d326e5042a7bce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179921"
---
# <a name="ui-automation-overview"></a>Общие сведения о модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]это новая платформа доступности для Microsoft Windows, доступная для всех операционных систем, которые поддерживают. [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] обеспечивает программный доступ к большинству элементов [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] на рабочем столе, позволяя продуктам с поддержкой специальных возможностей, таким как средства чтения с экрана, предоставлять конечным пользователям сведения о [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] и управлять [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] средствами, отличными от стандартного ввода данных. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] также позволяет скриптам автоматических тестов взаимодействовать с [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не поддерживает взаимодействие между процессами, запущенными разными пользователями с помощью команды **Запуск от имени** .  
  
 Клиентские приложения модели автоматизации пользовательского интерфейса могут быть написаны с гарантией того, что они будут работать в разных средах. Ядро [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] маскирует любые различия в средах, которые лежат в основе отдельных частей [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Например, `Content` свойство [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] кнопки, `Caption` свойство кнопки Win32 `ALT` и свойство HTML-изображения отображаются в одном свойстве, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>в представлении. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]  
  
UI Automation предоставляет полную функциональность на поддерживаемых операционных системах Windows под управлением .NET Framework [(см. требования системы .NET Framework](../get-started/system-requirements.md) или версии .NET Core, начиная с .NET Core 3.0.  
  
 Поставщики uI Automation предлагают некоторую поддержку клиентским приложениям Microsoft Active Accessibility через встроенную услугу преодоления.  
  
<a name="Providers_and_Clients"></a>
## <a name="providers-and-clients"></a>Поставщики и клиенты  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] состоит из четырех основных компонентов, как показано в следующей таблице.  
  
|Компонент|Описание|  
|---------------|-----------------|  
|API-провайдера (UIAutomationProvider.dll и UIAutomationTypes.dll)|Набор определений интерфейса, которые реализуются поставщиками автоматизации пользовательского интерфейса, объектами, предоставляющими сведения об элементах [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] и реагирующими на ввод данных программными средствами.|  
|API клиента (UIAutomationClient.dll и UIAutomationTypes.dll)|Набор типов для управляемого кода, который позволяет клиентским приложениям модели автоматизации пользовательского интерфейса получать сведения о [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] и отправлять входные данные в элементы управления.|  
|UiAutomationCore.dll|Базовый код (иногда называемый ядром [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ), который обрабатывает взаимодействие между поставщиками и клиентами.|  
|UIAutomationClientsideProviders.dll|Набор поставщиков автоматизации пользовательского интерфейса для стандартных элементов управления прежних версий. (элементы[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]имеют родную поддержку .) Эта поддержка автоматически доступна для клиентских приложений.|  
  
 С точки зрения разработчика программного обеспечения существует два способа использования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: создание поддержки пользовательских элементов управления (с помощью API поставщика) и создание приложений, использующих ядро [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для взаимодействия с элементами [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] (с помощью API клиента). В зависимости от ключевых целей вы должны обращаться к разным частям документации. В следующих разделах вы можете подробнее ознакомиться с основными понятиями и получить практические знания.  
  
|Section|Предмет рассмотрения|Аудитория|  
|-------------|--------------------|--------------|  
|[Основы автоматизации uI](index.md) (этот раздел)|Расширенный обзор основных понятий.|Все.|  
|[Поставщики автоматизации пользовательского интерфейса для управляемого кода](ui-automation-providers-for-managed-code.md)|Обзоры и практические руководства, помогающие использовать API поставщика.|Разработчики элементов управления.|  
|[Клиенты автоматизации пользовательского интерфейса для управляемого кода](ui-automation-clients-for-managed-code.md)|Обзоры и практические руководства, помогающие использовать API клиента.|Разработчики клиентских приложений.|  
|[Шаблоны модели автоматизации пользовательского интерфейса](ui-automation-control-patterns.md)|Сведения о порядке реализации поставщиками шаблонов элементов управления и о функциональных возможностях, доступных для клиентов.|Все.|  
|[Шаблон текста модели автоматизации пользовательского интерфейса](ui-automation-text-pattern.md)|Сведения о порядке реализации поставщиками шаблонов элементов управления Text и о функциональных возможностях, доступных для клиентов.|Все.|  
|[Типы элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types.md)|Сведения о свойствах и шаблонах элементов управления, поддерживаемых разными типами элементов управления.|Все.|  
  
 В следующей таблице перечислены пространства имен [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , библиотеки DLL, которые их содержат, и использующая их аудитория.  
  
|Пространство имен|Указанные DLL|Аудитория|  
|---------------|---------------------|--------------|  
|<xref:System.Windows.Automation>|UIAutomationClientUIAutomationTypes|Разработчики клиентов автоматизации пользовательского интерфейса; используется для поиска объектов <xref:System.Windows.Automation.AutomationElement> , регистрации для событий [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и работы с шаблонами элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.Provider>|UIAutomationProviderUIAutomationTypes|Разработчики поставщиков автоматизации пользовательского интерфейса для платформ, отличных от [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Windows.Automation.Text>|UIAutomationClientUIAutomationTypes|Разработчики поставщиков автоматизации пользовательского интерфейса для платформ, отличных от [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]; используется для реализации шаблона элемента управления TextPattern.|  
|<xref:System.Windows.Automation.Peers>|PresentationFramework|Разработчики поставщиков автоматизации пользовательского интерфейса для [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
  
<a name="UI_Automation_Model"></a>
## <a name="ui-automation-model"></a>Модель автоматизации пользовательского интерфейса  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет клиентским приложениям каждый фрагмент [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] как <xref:System.Windows.Automation.AutomationElement>. Элементы содержатся в древовидной структуре с рабочим столом в качестве корневого элемента. Клиенты могут фильтровать базовое представление дерева как представление элемента управления или представление содержимого. Приложения также могут создавать настраиваемые представления.  
  
 Объекты<xref:System.Windows.Automation.AutomationElement> предоставляют общие свойства элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , которые они представляют. Одно из этих свойств — это тип элемента управления, который определяет его базовый внешний вид и функциональность как единую распознаваемую сущность, например кнопку или флажок.  
  
 Кроме того, элементы предоставляют шаблоны элементов управления, которые обеспечивают свойства, относящиеся к типам их элементов управления. Шаблоны элементов управления также предоставляют методы, позволяющие клиентам получать дополнительные сведения об элементе и обеспечивать входные данные.  
  
> [!NOTE]
> Однозначного соответствия между типами элементов управления и шаблонами элементов управления не существует. Шаблон элемента управления может поддерживаться несколькими типами элементов управления, и элемент управления может поддерживать несколько шаблонов элементов управления, каждый из которых представляет различные аспекты его поведения. Например, поле со списком имеет по крайней мере два шаблона элементов управления: один представляет его возможность разворачиваться и сворачиваться, а другой представляет механизм выбора. Особенности см. в разделе [UI Automation Control Types](ui-automation-control-types.md).  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] также предоставляет клиентским приложениям сведения с помощью событий. В отличие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] от WinEvents, события не основаны на механизме вещания. Клиенты[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] регистрируются для конкретных уведомлений о событиях и могут запрашивать, чтобы конкретные свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] и сведения о шаблонах элементов управления передавались в их обработчики событий. Кроме того, событие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] содержит ссылку на породивший его элемент. Поставщики могут повысить производительность, вызывая события выборочно, в зависимости от того, являются ли клиенты прослушивающими.  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Общие сведения о свойствах автоматизированного пользовательского интерфейса](ui-automation-properties-overview.md)
- [Обзор событий автоматизации пользовательского интерфейса](ui-automation-events-overview.md)
- [Общие сведения о безопасности модели автоматизации пользовательского интерфейса](ui-automation-security-overview.md)
