---
title: Общие сведения о дереве модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
ms.openlocfilehash: 7dd799b32d51c7e24e6717561aab549e7e7f1fbe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69954011"
---
# <a name="ui-automation-tree-overview"></a>Общие сведения о дереве модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 Продукты и скрипты тестов специальных возможностей выполняют навигацию по дереву [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для сбора сведений о [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] и его элементах.  
  
 В дереве находится корневой элемент (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), представляющий текущий рабочий стол, чьи дочерние элементы представляют окна приложения. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Каждый из этих дочерних элементов может содержать элементы, представляющие части [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], такие как меню, кнопки, панели инструментов и списки. В свою очередь эти элементы тоже могут содержать элементы, такие как элементы списка.  
  
 Дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] не является фиксированной структурой и редко отображается полностью, так как оно может содержать тысячи элементов. Его части создаются по необходимости, и дерево может претерпевать изменения при добавлении, перемещении или удалении элементов.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживают дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], реализуя навигацию между элементами внутри фрагмента, который состоит из корня (как правило, размещенного в окне) и поддерева. Однако поставщики не интересуются переходами из одного элемента управления в другой. Такие переходы управляются ядром [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] с помощью сведений из поставщиков окна по умолчанию.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Представления дерева автоматизации  
 Дерево [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] может быть отфильтровано для создания представлений, содержащих только те объекты <xref:System.Windows.Automation.AutomationElement>, которые соответствуют конкретному клиенту. Такой подход позволяет клиентам настроить структуру, представленную с помощью [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], для их конкретных нужд.  
  
 Клиент может настроить представление двумя способами: определением области и фильтрацией. Определение области — это определение пространства представления, начиная от базового элемента: например, приложению может требоваться найти только прямой дочерний элемент рабочего стола или найти все потомки окна приложения. Фильтрацией является определение типов элементов, которые должны быть включены в представление.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживают фильтрацию путем определения свойств элементов, включая свойства <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> и <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет три представления по умолчанию. Эти представления определяются типом выполняемой фильтрации; область любого представления задается приложением. Кроме того, приложение может применять к свойствам другие фильтры; например, чтобы включить только включенные элементы управления в представление элемента управления.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Базовое представление  
 Базовое представление дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — это полное дерево объектов <xref:System.Windows.Automation.AutomationElement>, для которого корнем является рабочий стол. Базовое представление точно следует собственной программной структуре приложения и таким образом является наиболее подробным доступным представлением. Оно также является основой, на которой строятся другие представления дерева. Поскольку это представление зависит от базовой инфраструктуры [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], базовое представление кнопки [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] будет отличаться от базового представления кнопки [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)].  
  
 Базовое представление можно получить путем поиска элементов без указания свойств или с помощью <xref:System.Windows.Automation.TreeWalker.RawViewWalker> для навигации по дереву.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Представление элемента управления  
 Представление элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева упрощает задачу продукта поддержки специальных возможностей по описанию [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] и помощи ему по взаимодействию с приложением, поскольку оно точно сопоставлено со структурой [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], воспринимаемой конечным пользователем.  
  
 Представление элемента управления является подмножеством базового представления. Оно содержит все элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы из базового представления, которые конечный пользователь будет воспринимать как интерактивные или участвующие в логической структуре элемента управления в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Примеры элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], которые участвуют в логической структуре [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], но сами не являются интерактивными, — это контейнеры элементов, такие как заголовки представлений списков, панели инструментов, меню и строки состояния. Неинтерактивные элементы, используемые просто для разметки в декоративных целях, не будут отображаться в представлении элемента управления. В качестве примера можно привести панель, которая используется только для размещения элементов управления в диалоговом окне, но сама не содержит никакой информации. Неинтерактивными элементами, которые будут отображаться в представлении элемента управления, являются графики с данными и статический текст в диалоговом окне. Неинтерактивные элементы, включенные в представление элемента управления, не могут получать фокус клавиатуры.  
  
 Представление элемента управления можно получить путем поиска элементов, свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> которых имеет значение `true`, или используя <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> для навигации по дереву.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Представление содержимого  
 Представление содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] является подмножеством представления элемента управления. Оно содержит элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], которые передают достоверную информацию в пользовательский интерфейс, включая элементы [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], которые могут получать фокус клавиатуры, и текст, который не является меткой элемента [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Например, значения в раскрывающемся поле со списком будут отображаться в представлении содержимого, так как они представляют информацию конечному пользователю. В представлении содержимого поле со списком и список представляются в виде коллекции элементов [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], в которой можно выбрать один или несколько элементов. Тот факт, что один их них всегда открыт, а другой можно развернуть и свернуть, не имеет значения в представлении содержимого, поскольку оно предназначено для отображения данных или содержимого для пользователя.  
  
 Представление содержимого можно получить путем поиска элементов, свойство <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> которых имеет значение `true`, или используя <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> для навигации по дереву.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.AutomationElement>
- [Общие сведения о модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)
