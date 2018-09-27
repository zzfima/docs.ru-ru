---
title: Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 6e10b0e38e80bad1f322e32324db862691432b8e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47236243"
---
# <a name="ui-automation-control-patterns-for-clients"></a>Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом обзоре представлены шаблоны элементов управления для клиентов автоматизации пользовательского интерфейса. Он содержит сведения о том, как клиент автоматизации пользовательского интерфейса может использовать шаблоны элементов управления для доступа к сведениям о [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 Шаблоны элементов управления позволяют классифицировать и предоставлять функции элемента управления независимо от типа или внешнего вида элемента управления. Клиенты автоматизации пользовательского интерфейса могут проверять <xref:System.Windows.Automation.AutomationElement> , чтобы определить, какие шаблоны элементов управления поддерживаются и какое поведение элемента управления будет применяться.  
  
 Полный список шаблонов элементов управления см. в разделе [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a>Получение шаблонов элементов управления  
 Клиенты получают шаблон элемента управления из <xref:System.Windows.Automation.AutomationElement>, вызывая <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> или <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 Клиенты могут использовать метод <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> или отдельное свойство `IsPatternAvailable` (например, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>), чтобы определить, поддерживается ли шаблон или группа шаблонов в <xref:System.Windows.Automation.AutomationElement>. Однако более эффективно будет попытаться получить шаблон элемента управления и проверить его на наличие ссылки `null`, чем проверить поддерживаемые свойства и получить шаблон элемента управления, поскольку это приводит к меньшим числом вызовов между процессами.  
  
 В следующем примере показано, как получить шаблон элемента управления <xref:System.Windows.Automation.TextPattern> из объекта <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a>Получение свойств в шаблонах элементов управления  
 Клиенты могут получать значения свойств в шаблонах элементов управления, вызывая <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> или <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> и преобразуя возвращаемый объекта в соответствующий тип. Дополнительные сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] свойства, см. в разделе [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
 В дополнение к `GetPropertyValue` методам, значения свойств можно извлечь с помощью методов доступа [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] для получения свойств [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] шаблона.  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a>Элементы управления с переменными шаблонами  
 Некоторые типы элементов управления поддерживают различные шаблоны в зависимости от их состояния или способа использования элемента управления. Примеры элементов управления, которые могут иметь переменные шаблоны: представления списков (эскизы, плитки, значки, список, подробные сведения), диаграммы [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] (круговые, графики, линейчатые, значение ячейки с формулой) область документа [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)](обычный, веб-макет, структура, разметка страницы, предварительный просмотр) и обложки [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] .  
  
 Элементы управления, реализующие настраиваемые типы элементов управления, могут содержать любой набор шаблонов элементов управления, необходимых для представления их возможностей.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)  
 [Шаблон текста модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)  
 [Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [Получение состояния флажка с использованием модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [TextPattern Insert Text Sample](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [TextPattern поиска и выбора](https://msdn.microsoft.com/library/0a3bca57-8b72-489d-a57c-da85b7a22c7f)  
 [InvokePattern и образец элемента меню ExpandCollapsePattern](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
