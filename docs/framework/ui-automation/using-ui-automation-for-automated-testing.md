---
title: Использование Автоматизации Пользовательского Интерфейса для автоматизированного тестирования
ms.date: 03/30/2017
helpviewer_keywords:
- automated testing
- testing, UI Automation
- UI Automation, automated testing
ms.assetid: 3a0435c0-a791-4ad7-ba92-a4c1d1231fde
ms.openlocfilehash: 5668e14cd0aed33a29fd43661363131879419e61
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793923"
---
# <a name="using-ui-automation-for-automated-testing"></a>Использование Автоматизации Пользовательского Интерфейса для автоматизированного тестирования
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом обзоре описывается, как можно использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] в качестве платформы для программного доступа в скриптах автоматического тестирования.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет унифицированную объектную модель, поддерживающую все платформы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] для представления сложных и широких функциональных возможностей доступным и легко автоматизируемым образом.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] был разработан в качестве последователей для Active Accessibility Майкрософт. Active Accessibility — это существующая платформа, предназначенная для обеспечения доступа к элементам управления и приложениям. Active Accessibility не была разработана с учетом автоматизации тестирования, несмотря на то, что она была изменена в этой роли из-за очень похожих требований к доступности и автоматизации. Помимо предоставления более качественных решений для специальных возможностей, модель[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]также специально разрабатывалась в целях предоставления надежной функциональности для автоматического тестирования. Например, Active Accessibility полагается на один интерфейс, чтобы предоставить сведения о пользовательском интерфейсе и получить сведения, необходимые для продуктов. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] разделяет две модели.  
  
 Чтобы модель [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] можно было использовать в качестве средства автоматических тестов, для ее реализации требуется как клиент, так и поставщик. Поставщики автоматизации пользовательского интерфейса — это приложения, такие как Microsoft Word, Excel и другие сторонние приложения или элементы управления, основанные на операционной системе Microsoft Windows. Клиенты автоматизации пользовательского интерфейса включают скрипты автоматических тестов приложения и приложения специальных возможностей.  
  
> [!NOTE]
> Цель этого обзора заключается в том, чтобы показать новые и улучшенные возможности автоматического тестирования [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. В данном обзоре не предполагается предоставлять сведения о специальных возможностях, и тема доступности будет затрагиваться только там, где это необходимо.  
  
## <a name="ui-automation-in-a-provider"></a>Модель автоматизации пользовательского интерфейса в поставщике  
 Для автоматизации [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] разработчик приложения или элемента управления должен рассмотреть, какие действия может выполнять конечный пользователь в объекте [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , используя стандартное взаимодействие с помощью клавиатуры и мыши.  
  
 После определения этих ключевых действий в элементе управления необходимо реализовать соответствующие шаблоны элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (то есть шаблоны элементов управления, отражающие функциональность и поведение элемента [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ). Например, взаимодействие пользователя с элементом управления "поле со списком" (таким как диалоговое окно запуска) обычно включает развертывание и свертывание поля со списком для отображения или скрытия списка элементов, выбор элемента из списка или добавление нового значения путем ввода с клавиатуры.  
  
> [!NOTE]
> В других моделях специальных возможностей разработчики должны собирать сведения непосредственно из отдельных кнопок, меню и других элементов управления. К несчастью, каждый тип элемента управления поставляется в десятках вспомогательных вариантов. Другими словами, даже если десять вариантов кнопки работают одинаково и выполняют ту же функцию, все они должны рассматриваться как отдельные элементы управления. Нет способа узнать, что эти элементы управления функционально эквивалентны. Шаблоны элементов управления были разработаны для представления такого общего поведения элементов управления. Для получения дополнительной информации см. [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
### <a name="implementing-ui-automation"></a>Реализация автоматизации пользовательского интерфейса  
 Как упоминалось ранее, без единой модели, предоставляемой [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], средствам тестирования и разработчикам необходимо знать информацию о среде, чтобы представлять свойства и поведение элементов управления в этой среде. Поскольку в любой момент времени в операционных системах Windows можно использовать несколько различных платформ пользовательского интерфейса, включая Win32, Windows Forms и Windows Presentation Foundation (WPF), это может оказаться сложной задачей для тестирования нескольких приложений с помощью элементов управления, которые похоже на. Например, в следующей таблице перечислены относящиеся к конкретной инфраструктуре имена свойств, необходимые для извлечения имени (или текста), связанного с элементом управления "Кнопка", и приведено единственное эквивалентное свойство [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
|Тип элемента управления модели автоматизации пользовательского интерфейса|Инфраструктура пользовательского интерфейса|Свойство инфраструктуры|Свойство модели автоматизации пользовательского интерфейса|  
|--------------------------------|------------------|---------------------------------|----------------------------|  
|Кнопка|Windows Presentation Foundation (WPF)|Content|NameProperty|  
|Кнопка|Win32|Подпись|NameProperty|  
|Изображение|HTML|alt|NameProperty|  
  
 Поставщики автоматизации пользовательского интерфейса отвечают за сопоставление свойств элементов управления, относящихся к инфраструктуре, с эквивалентными свойствами [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Сведения о реализации [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] в поставщике см. в разделе [UI Automation Providers for Managed Code](ui-automation-providers-for-managed-code.md). Сведения о реализации шаблонов элементов управления см. в разделах [UI Automation Control Patterns](ui-automation-control-patterns.md) и [UI Automation Text Pattern](ui-automation-text-pattern.md).  
  
## <a name="ui-automation-in-a-client"></a>Модель автоматизации пользовательского интерфейса в клиенте  
 Цель многих средств и сценариев автоматического тестирования состоит в согласованной и воспроизводимой обработке пользовательского интерфейса. Это может включать модульное тестирование определенных элементов управления с помощью записи и воспроизведения скриптов тестирования, которые выполняют итерацию по ряду универсальных действий в группе элементов управления.  
  
 Осложнение, вытекающее из автоматических приложений, заключается в трудности синхронизации тестирования с динамической целью. Например, элемент управления "Список", такой как в диспетчере задач Windows, отображает список запущенных приложений. Поскольку элементы в этом списке динамически обновляются независимо от тестового приложения, невозможно повторять выбор определенного элемента в списке с каким-либо постоянством. Аналогичные проблемы также могут возникнуть при попытке повторить простые изменения фокуса в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , который находится вне рамок влияния тестового приложения.  
  
### <a name="programmatic-access"></a>Программный доступ  
 Программный доступ предоставляет возможность имитировать через код любое взаимодействие, обеспечиваемое традиционным вводом с помощью мыши и клавиатуры. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] обеспечивает программный доступ с помощью пяти следующих компонентов.  
  
- Дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] упрощает навигацию по структуре [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Это дерево строится из коллекции hWnd. Дополнительные сведения см. в разделе [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
- Элементы автоматизации — это отдельные компоненты в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Часто они могут быть более детализированы, чем hWnd. Для получения дополнительной информации см. [UI Automation Control Types Overview](ui-automation-control-types-overview.md).  
  
- Свойства автоматизации предоставляют определенные сведения об элементах [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Дополнительные сведения см. в разделе [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
- Шаблоны элементов управления задают определенный аспект функциональности элемента управления; они могут состоять из свойств, методов, событий и сведений о структуре. Для получения дополнительной информации см. [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
- События автоматизации обеспечивают уведомления и информацию. Для получения дополнительной информации см. [UI Automation Events Overview](ui-automation-events-overview.md).  
  
### <a name="key-properties-for-test-automation"></a>Ключевые свойства для автоматизации тестирования  
 Возможность уникально идентифицировать и затем находить любой элемент управления в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] служит основой для работы приложений автоматизированного тестирования в этом [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Существует несколько свойств [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , используемых клиентами и поставщиками, которые помогают в этом.  
  
#### <a name="automationid"></a>AutomationId  
 Уникально идентифицирует элемент автоматизации среди элементов того же уровня. Элемент<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> не локализован, в отличие от свойства, такого как <xref:System.Windows.Automation.AutomationElement.NameProperty> , которое обычно локализуется, если продукт поставляется на нескольких языках. См. раздел [Use the AutomationID Property](use-the-automationid-property.md).  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> не гарантирует уникальную идентификацию по всему дереву автоматизации. Например, приложение может содержать элемент управления меню с несколькими пунктами меню верхнего уровня, которые, в свою очередь, имеют несколько дочерних пунктов меню. Эти пункты меню второго уровня могут идентифицироваться по универсальной схеме, такой как "элемент1, элемент2, элемент3 и т. д.", что допускает повторяющиеся идентификаторы дочерних элементов в разных пунктах меню верхнего уровня.  
  
#### <a name="controltype"></a>ControlType  
 Определяет тип элемента управления, представленного элементом автоматизации. Из знания типа элемента управления могут быть получены важные сведения. См. раздел [UI Automation Control Types Overview](ui-automation-control-types-overview.md).  
  
#### <a name="nameproperty"></a>NameProperty  
 Это текстовая строка, которая определяет или описывает элемент управления. Свойство<xref:System.Windows.Automation.AutomationElement.NameProperty> следует использовать с осторожностью, поскольку оно может быть локализовано. См. раздел [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
### <a name="implementing-ui-automation-in-a-test-application"></a>Реализация автоматизации пользовательского интерфейса в тестовом приложении  
  
|||  
|-|-|  
|Добавление ссылок для автоматизации пользовательского интерфейса.|Ниже перечислены библиотеки DLL [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , необходимые для клиентов автоматизации пользовательского интерфейса.<br /><br /> -UIAutomationClient. dll предоставляет доступ к [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API на стороне клиента.<br />-Уиаутоматионклиентсидепровидер. dll предоставляет возможность автоматизации элементов управления Win32. См. раздел [UI Automation Support for Standard Controls](ui-automation-support-for-standard-controls.md).<br />-UIAutomationTypes. dll предоставляет доступ к определенным типам, определенным в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].|  
|Добавление пространства имен <xref:System.Windows.Automation>|Это пространство имен содержит все клиенты автоматизации пользовательского интерфейса, необходимые для использования возможностей [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , за исключением обработки текста.|  
|Добавление пространства имен <xref:System.Windows.Automation.Text>|Это пространство имен содержит все клиенты автоматизации пользовательского интерфейса, необходимые для использования возможностей [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] обработки текста.|  
|Поиск нужных элементов управления|Скрипты автоматических тестов находят элементы автоматизации пользовательского интерфейса, представляющие нужные элементы управления в дереве автоматизации.<br /><br /> Существует несколько способов получения элементов автоматизации пользовательского интерфейса с помощью кода.<br /><br /> — Запрос [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] с помощью инструкции <xref:System.Windows.Automation.Condition>. Обычно здесь используется не зависящее от языка свойство <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> . **Примечание.**  <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> можно получить с помощью такого средства, как проверка. exe, который способен детализировать свойства [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента управления. <br /><br /> — Используйте класс <xref:System.Windows.Automation.TreeWalker> для прохода по всему дереву [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] или подмножеству.<br />— Отслеживание фокуса.<br />— Используйте hWnd элемента управления.<br />— Используйте место на экране, например расположение курсора мыши.<br /><br /> См. раздел [Obtaining UI Automation Elements](obtaining-ui-automation-elements.md).|  
|Получение шаблонов элементов управления|Шаблоны элементов управления предоставляют общие расширения функциональности для функциональных возможностей схожих элементов управления.<br /><br /> После нахождения элемента управления, требующего проверки, скрипты автоматических тестов получают интересующие шаблоны элементов управления из этих элементов автоматизации пользовательского интерфейса. Например, шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> для типичной функциональности кнопки или шаблон элемента управления <xref:System.Windows.Automation.WindowPattern> для функциональности окна.<br /><br /> См. раздел [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).|  
|Автоматизация пользовательского интерфейса|Скрипты автоматических тестов теперь могут управлять любым интересующим [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] в платформе [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] , используя сведения и функциональные возможности, предоставляемые шаблонами элементов управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
## <a name="related-tools-and-technologies"></a>Связанные инструменты и технологии  
 Существует множество связанных инструментов и технологий, которые поддерживают автоматическое тестирование с помощью [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
- Средство проверки. exe — это приложение графического пользовательского интерфейса, которое можно использовать для сбора [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] сведений о разработке и отладке поставщика и клиента. Программа проверки. exe включена в Windows SDK.  
  
- Мсаабридже предоставляет сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для Active Accessibility клиентов. Основная цель моста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] к Active Accessibility — разрешить существующим клиентам Active Accessibility возможность взаимодействия с любой платформой, реализованной [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
## <a name="security"></a>по безопасности  
 Сведения о безопасности см. в разделе [UI Automation Security Overview](ui-automation-security-overview.md).  
  
## <a name="see-also"></a>См. также:

- [Основы модели автоматизации пользовательского интерфейса](index.md)
