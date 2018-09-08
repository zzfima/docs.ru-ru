---
title: Общие сведения о дереве модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- automation tree
- UI Automation, tree
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 042f3f82a88e987131145f38c1d8f5ecfa8dc487
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44179040"
---
# <a name="ui-automation-tree-overview"></a>Общие сведения о дереве модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Продуктов поддержки специальных возможностей и скриптов тестирования использует [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева для сбора сведений о [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] и его элементов.  
  
 В рамках [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерево является корневой элемент (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), представляющий текущий рабочий стол и дочерние элементы представляют окна приложений. Каждый из этих дочерних элементов может содержать элементы, представляющие части [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] таких как меню, кнопки, панели инструментов и списки. В свою очередь эти элементы тоже могут содержать элементы, такие как элементы списка.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Дерево не является фиксированной структурой и редко отображается полностью, так как он может содержать тысячи элементов. Его части создаются по необходимости, и дерево может претерпевать изменения при добавлении, перемещении или удалении элементов.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева, реализуя навигацию между элементами внутри фрагмента, который состоит из корня (как правило, размещенного в окне) и поддерева. Однако поставщики не интересуются переходами из одного элемента управления в другой. Это управляется [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] основы, с помощью сведений из поставщиков окна по умолчанию.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Представления дерева автоматизации  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Дерева может быть отфильтровано для создания представления, которые содержат только те <xref:System.Windows.Automation.AutomationElement> объекты, относящиеся к конкретному клиенту. Такой подход позволяет клиентам настроить структуру, представленную с помощью [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для их конкретных нужд.  
  
 Клиент может настроить представление двумя способами: определением области и фильтрацией. Определение области — это определение пространства представления, начиная от базового элемента: например, приложению может требоваться найти только прямой дочерний элемент рабочего стола или найти все потомки окна приложения. Фильтрацией является определение типов элементов, которые должны быть включены в представление.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживают фильтрацию путем определения свойств элементов, включая <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> и <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> свойства.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] предоставляет три представления по умолчанию. Эти представления определяются типом выполняемой фильтрации; область любого представления задается приложением. Кроме того, приложение может применять к свойствам другие фильтры; например, чтобы включить только включенные элементы управления в представление элемента управления.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Базовое представление  
 Базовое представление [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] полное дерево из <xref:System.Windows.Automation.AutomationElement> объектов, для которых является корневой рабочий стол. Базовое представление точно следует собственной программной структуре приложения и таким образом является наиболее подробным доступным представлением. Оно также является основой, на которой строятся другие представления дерева. Так как это представление зависит от базовой [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] framework, базовое представление [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] кнопки будут иметь разные представления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] кнопки.  
  
 Базовое представление получается путем поиска элементов без указания свойств или с помощью <xref:System.Windows.Automation.TreeWalker.RawViewWalker> для навигации по дереву.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Представление элемента управления  
 Представление элемента управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева упрощает задачу продукта поддержки специальных возможностей описания [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для конечного пользователя и помогая ему взаимодействовать с приложением, так как оно точно сопоставлено [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] структуры распознанный конечным пользователем.  
  
 Представление элемента управления является подмножеством базового представления. Она включает все [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы из начального представления, которые конечный пользователь будет воспринимать как интерактивные или участвующие в логической структуре элемента управления в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Примеры [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы, которые участвуют в логической структуре из [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], но сами не являются интерактивными, — это контейнеры элементов, таких как заголовки представлений списков, панели инструментов, меню и строки состояния. Неинтерактивные элементы, используемые просто для разметки в декоративных целях, не будут отображаться в представлении элемента управления. В качестве примера можно привести панель, которая используется только для размещения элементов управления в диалоговом окне, но сама не содержит никакой информации. Неинтерактивными элементами, которые будут отображаться в представлении элемента управления, являются графики с данными и статический текст в диалоговом окне. Неинтерактивные элементы, включенные в представление элемента управления, не могут получать фокус клавиатуры.  
  
 Представление элемента управления можно получить путем поиска для элементов, имеющих <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> свойство значение `true`, или с помощью <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> для навигации по дереву.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Представление содержимого  
 Представление содержимого [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерево является подмножеством представления элемента управления. Он содержит [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы, которые передают достоверную информацию в пользовательский интерфейс, включая [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы, которые могут получать фокус клавиатуры и текст, который не является меткой на [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элемента. Например, значения в раскрывающемся поле со списком будут отображаться в представлении содержимого, так как они представляют информацию конечному пользователю. В представлении содержимого поле со списком и поле со списком представлены как коллекция [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементов, где можно выбрать один или несколько, элементов. Тот факт, что один их них всегда открыт, а другой можно развернуть и свернуть, не имеет значения в представлении содержимого, поскольку оно предназначено для отображения данных или содержимого для пользователя.  
  
 Представление содержимого можно получить путем поиска для элементов, имеющих <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> свойство значение `true`, или с помощью <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> для навигации по дереву.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Automation.AutomationElement>  
 [Общие сведения о модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)
