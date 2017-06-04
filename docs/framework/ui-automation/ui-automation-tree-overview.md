---
title: "Общие сведения о дереве модели автоматизации пользовательского интерфейса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "дерево автоматизации"
  - "Автоматизация пользовательского интерфейса, дерева"
ms.assetid: 03b98058-bdb3-47a0-8ff7-45e6cdf67166
caps.latest.revision: 25
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 25
---
# Общие сведения о дереве модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Продукты поддержки специальных возможностей и скриптов тестирования использует [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева для сбора сведений о [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] и его элементов.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева является корневым элементом (<xref:System.Windows.Automation.AutomationElement.RootElement%2A>), представляющий текущего рабочего стола и, с дочерними элементами представляют приложения windows. Каждый из этих дочерних элементов может содержать элементы, представляющие части [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] как меню, кнопки, панели инструментов и списки. В свою очередь эти элементы тоже могут содержать элементы, такие как элементы списка.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Дерева не является фиксированной структурой и редко отображается полностью, так как оно может содержать тысячи элементов. Его части создаются по необходимости, и дерево может претерпевать изменения при добавлении, перемещении или удалении элементов.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживают [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева путем реализации навигацию между элементами внутри фрагмента, который состоит из корня (как правило, размещенного в окне) и поддерева. Однако поставщики не интересуются переходами из одного элемента управления в другой. Это осуществляется с помощью [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ядра с помощью сведений из поставщиков окна по умолчанию.  
  
<a name="uiautomation_tree_view"></a>   
## <a name="views-of-the-automation-tree"></a>Представления дерева автоматизации  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Дерева может быть отфильтровано для создания представлений, содержащих только те <xref:System.Windows.Automation.AutomationElement> объекты относятся к конкретному клиенту. Этот подход позволяет клиентам настроить структуру, представленную с помощью [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для их конкретных нужд.  
  
 Клиент может настроить представление двумя способами: определением области и фильтрацией. Определение области — это определение пространства представления, начиная от базового элемента: например, приложению может требоваться найти только прямой дочерний элемент рабочего стола или найти все потомки окна приложения. Фильтрацией является определение типов элементов, которые должны быть включены в представление.  
  
 Поставщики автоматизации пользовательского интерфейса поддерживает фильтрацию с помощью определения свойств элементов, включая <xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty> и <xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty> свойства.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]предоставляет три представления по умолчанию. Эти представления определяются типом выполняемой фильтрации; область любого представления задается приложением. Кроме того, приложение может применять к свойствам другие фильтры; например, чтобы включить только включенные элементы управления в представление элемента управления.  
  
<a name="uiautomation_raw_view"></a>   
### <a name="raw-view"></a>Базовое представление  
 Начальное представление [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] полное дерево из <xref:System.Windows.Automation.AutomationElement> объекты, для которых рабочий стол является корнем. Базовое представление точно следует собственной программной структуре приложения и таким образом является наиболее подробным доступным представлением. Оно также является основой, на которой строятся другие представления дерева. Так как это представление зависит от базовой [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] framework, начальное представление [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] кнопки будут иметь разные начального представления, чем [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] кнопки.  
  
 Начальное представление получается путем поиска элементов без указания свойств или с помощью <xref:System.Windows.Automation.TreeWalker.RawViewWalker> для навигации по дереву.  
  
<a name="uiautomation_control_view"></a>   
### <a name="control-view"></a>Представление элемента управления  
 Представление элемента управления [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева упрощает задачу описания вспомогательных программ [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] для конечного пользователя и помогая ему взаимодействовать с приложением, так как оно тесно сопоставлено [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] структуры воспринимается конечным пользователем.  
  
 Представление элемента управления является подмножеством базового представления. Он включает все [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы из начального представления, которые конечный пользователь понимал бы как интерактивные или участвующие в логической структуре элемента управления в [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Примеры [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементов, которые участвуют в логической структуре из [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], но сами не являются интерактивными, являются элементы контейнеров, такие как заголовки представлений списков, панели инструментов, меню и строки состояния. Неинтерактивные элементы, используемые просто для разметки в декоративных целях, не будут отображаться в представлении элемента управления. В качестве примера можно привести панель, которая используется только для размещения элементов управления в диалоговом окне, но сама не содержит никакой информации. Неинтерактивными элементами, которые будут отображаться в представлении элемента управления, являются графики с данными и статический текст в диалоговом окне. Неинтерактивные элементы, включенные в представление элемента управления, не могут получать фокус клавиатуры.  
  
 Представление элемента управления получается путем поиска для элементов, имеющих <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A> свойству `true`, или с помощью <xref:System.Windows.Automation.TreeWalker.ControlViewWalker> для навигации по дереву.  
  
<a name="uiautomation_content_view"></a>   
### <a name="content-view"></a>Представление содержимого  
 Представление содержимого [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева является подмножеством представления элемента управления. Он содержит [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементов, которые передают достоверную информацию в пользовательский интерфейс, включая [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементы, которые могут получать фокус клавиатуры и текст, который не является метка на [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элемента. Например, значения в раскрывающемся поле со списком будут отображаться в представлении содержимого, так как они представляют информацию конечному пользователю. В представлении содержимого, поле со списком и поле со списком представлены как коллекция [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элементов, где можно выбрать один или несколько, элементов. Тот факт, что один их них всегда открыт, а другой можно развернуть и свернуть, не имеет значения в представлении содержимого, поскольку оно предназначено для отображения данных или содержимого для пользователя.  
  
 Представление содержимого получается путем поиска для элементов, имеющих <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A> свойству `true`, или с помощью <xref:System.Windows.Automation.TreeWalker.ContentViewWalker> для навигации по дереву.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Automation.AutomationElement>   
 [Обзор автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)