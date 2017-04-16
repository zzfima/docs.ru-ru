---
title: "Use the AutomationID Property | Microsoft Docs"
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
  - "AutomationId property"
  - "UI Automation, AutomationId property"
  - "properties, AutomationId"
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
caps.latest.revision: 21
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 21
---
# Use the AutomationID Property
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержатся сценарии и примеры кода, которые показывают, как и когда можно использовать <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> для поиска элемента в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> уникально идентифицирует элемент модели автоматизации пользовательского интерфейса среди элементов того же уровня. Дополнительные сведения об идентификаторах свойств, связанных с идентификацией элементов управления, см. в разделе [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
> [!NOTE]
>  <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> не гарантирует уникальную идентификацию по всему дереву; обычно для его использования требуются сведения о контейнере и области. Например, приложение может содержать элемент управления "Меню" с несколькими пунктами меню верхнего уровня, которые в свою очередь имеют несколько дочерних пунктов меню. Эти пункты меню второго уровня могут идентифицироваться по универсальной схеме, такой как "элемент1", "элемент2" и т. д., что допускает повторяющиеся идентификаторы дочерних элементов в разных пунктах меню верхнего уровня.  
  
## Сценарии  
 Были определены три основных сценария клиентского приложения модели автоматизации пользовательского интерфейса, в которых необходимо использовать <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> для получения точных и согласованных результатов при поиске элементов.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> поддерживается всеми элементами модели автоматизации пользовательского интерфейса в представлении элемента управления, за исключением окон приложений верхнего уровня, элементов модели автоматизации пользовательского интерфейса, производных от элементов управления [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], не имеющих идентификатора или x:Uid, и элементов модели автоматизации пользовательского интерфейса, производных от элементов управления [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], не имеющих идентификатора элемента управления.  
  
#### Для поиска определенного элемента в дереве модели автоматизации пользовательского интерфейса используйте уникальный и обнаруживаемый AutomationID.  
  
-   Используйте такой инструмент, как [!INCLUDE[TLA#tla_uispy](../../../includes/tlasharptla-uispy-md.md)], чтобы сообщить о <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> интересующего элемента [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]. Затем это значение можно скопировать и вставить в клиентское приложение, такое как тестовый скрипт для последующего автоматического тестирования. Такой подход сокращает и упрощает код, необходимый для идентификации и обнаружения элементов во время выполнения.  
  
> [!CAUTION]
>  В целом вы должны пытаться получить только прямые потомки <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Поиск потомков может выполнять итерацию по сотням или даже тысячам элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### Использование постоянного пути для возврата к ранее идентифицированному AutomationElement  
  
-   Клиентским приложениям, от простых тестовых скриптов до до надежных программ записи и воспроизведения, может потребоваться доступ к элементам, в текущий момент не реализованным, таким как диалоговое окно открытия файла или пункт меню, и поэтому не существующим в дереве модели автоматизации пользовательского интерфейса. Эти элементы могут быть созданы только воспроизведением определенной последовательности действий [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] с помощью свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], таких как AutomationID, шаблонов элементов управления и прослушивателей событий. Пример, в котором с помощью [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] создаются тестовые скрипты на основе взаимодействия пользователя с [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], см. в разделе [Test Script Generator Sample](http://msdn.microsoft.com/ru-ru/028467fd-2980-4691-9522-0131dcef23a0).  
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### Использование относительного пути для возврата к ранее идентифицированному AutomationElement  
  
-   В некоторых случаях несколько элементов в дереве модели автоматизации пользовательского интерфейса могут иметь одинаковые значения свойств AutomationID, поскольку AutomationID гарантированно уникален только среди элементов того же уровня. В этих случаях элементы можно однозначно идентифицировать на основе родителя и при необходимости прародителя. Например, разработчик может создать строку меню с несколькими пунктами меню, каждый из которых имеет несколько дочерних пунктов меню, где дочерние пункты идентифицируются с помощью последовательных идентификаторов AutomationID, например Item1, Item2 и т. д. Каждый пункт меню может затем быть однозначно идентифицирован по его идентификатору AutomationID вместе с AutomationID его родителя и при необходимости его прародителя.  
  
## См. также  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>   
 [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Find a UI Automation Element Based on a Property Condition](../../../docs/framework/ui-automation/find-a-ui-automation-element-based-on-a-property-condition.md)