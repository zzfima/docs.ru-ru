---
title: Использование свойства AutomationID
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutomationId property
- UI Automation, AutomationId property
- properties, AutomationId
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
ms.openlocfilehash: 43a67a8dd73931172a6fa729c054ad494b29134e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800302"
---
# <a name="use-the-automationid-property"></a>Использование свойства AutomationID
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сценарии и примеры кода, которые показывают, как и когда можно использовать <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> для поиска элемента в дереве [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> уникально идентифицирует элемент модели автоматизации пользовательского интерфейса среди элементов того же уровня. Дополнительные сведения об идентификаторах свойств, связанных с идентификацией элементов управления, см. в разделе [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> не гарантирует уникальную идентификацию по всему дереву; обычно для его использования требуются сведения о контейнере и области. Например, приложение может содержать элемент управления меню с несколькими пунктами меню верхнего уровня, которые, в свою очередь, имеют несколько дочерних пунктов меню. Эти пункты меню второго уровня могут идентифицироваться по универсальной схеме, такой как "элемент1", "элемент2" и т. д., что допускает повторяющиеся идентификаторы дочерних элементов в разных пунктах меню верхнего уровня.  
  
## <a name="scenarios"></a>Сценарии  
 Были определены три основных сценария клиентского приложения модели автоматизации пользовательского интерфейса, в которых необходимо использовать <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> для получения точных и согласованных результатов при поиске элементов.  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> поддерживается всеми элементами модели автоматизации пользовательского интерфейса в представлении элемента управления, за исключением окон приложений верхнего уровня, элементов модели автоматизации пользовательского интерфейса, производных от элементов управления [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , не имеющих идентификатора или x:Uid, и элементов модели автоматизации пользовательского интерфейса, производных от элементов управления [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] , не имеющих идентификатора элемента управления.  
  
#### <a name="use-a-unique-and-discoverable-automationid-to-locate-a-specific-element-in-the-ui-automation-tree"></a>Для поиска определенного элемента в дереве модели автоматизации пользовательского интерфейса используйте уникальный и обнаруживаемый AutomationID.  
  
- Используйте такой инструмент, как UI Spy, чтобы сообщить <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] элемента, представляющего интерес. Затем это значение можно скопировать и вставить в клиентское приложение, такое как тестовый скрипт для последующего автоматического тестирования. Такой подход сокращает и упрощает код, необходимый для идентификации и обнаружения элементов во время выполнения.  
  
> [!CAUTION]
> В целом вы должны пытаться получить только прямые потомки <xref:System.Windows.Automation.AutomationElement.RootElement%2A>. Поиск потомков может выполнять итерацию по сотням или даже тысячам элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### <a name="use-a-persistent-path-to-return-to-a-previously-identified-automationelement"></a>Использование постоянного пути для возврата к ранее идентифицированному AutomationElement  
  
- Клиентским приложениям, от простых тестовых скриптов до до надежных программ записи и воспроизведения, может потребоваться доступ к элементам, в текущий момент не реализованным, таким как диалоговое окно открытия файла или пункт меню, и поэтому не существующим в дереве модели автоматизации пользовательского интерфейса. Экземпляры этих элементов можно создавать только путем повторного воспроизведения, или "воспроизведением", определенной последовательности действий пользовательского интерфейса с помощью свойств модели автоматизации пользовательского интерфейса, таких как AutomationID, шаблоны элементов управления и прослушиватели событий.
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### <a name="use-a-relative-path-to-return-to-a-previously-identified-automationelement"></a>Использование относительного пути для возврата к ранее идентифицированному AutomationElement  
  
- В некоторых случаях несколько элементов в дереве модели автоматизации пользовательского интерфейса могут иметь одинаковые значения свойств AutomationID, поскольку AutomationID гарантированно уникален только среди элементов того же уровня. В этих случаях элементы можно однозначно идентифицировать на основе родителя и при необходимости прародителя. Например, разработчик может создать строку меню с несколькими пунктами меню, каждый из которых имеет несколько дочерних пунктов меню, где дочерние пункты идентифицируются с помощью последовательных идентификаторов AutomationID, например Item1, Item2 и т. д. Каждый пункт меню может затем быть однозначно идентифицирован по его идентификатору AutomationID вместе с AutomationID его родителя и при необходимости его прародителя.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Нахождение элемента модели автоматизации пользовательского интерфейса в зависимости от состояния свойства](find-a-ui-automation-element-based-on-a-property-condition.md)
