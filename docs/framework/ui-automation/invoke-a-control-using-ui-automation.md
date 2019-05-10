---
title: Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking controls
- UI Automation, invoking controls
- controls, invoking
ms.assetid: 5ee2de3f-256c-43ec-b64c-62ace91f9983
ms.openlocfilehash: 19087cfaa22d166017bcf4e3ce5e6caf73ae5fe5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624555"
---
# <a name="invoke-a-control-using-ui-automation"></a>Вызов элемента управления с помощью модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом примере показано выполнение следующих задач.  
  
- Поиск элемента управления, который соответствует конкретным условиям свойств путем прохода представления элемента управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] для целевого приложения.  
  
- Создание <xref:System.Windows.Automation.AutomationElement> для каждого элемента управления.  
  
- Получение объекта <xref:System.Windows.Automation.InvokePattern> из любого найденного элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , который поддерживает шаблон элемента управления <xref:System.Windows.Automation.InvokePattern> .  
  
- Использование <xref:System.Windows.Automation.InvokePattern.Invoke%2A> для вызова элемента управления из обработчика событий клиента.  
  
## <a name="example"></a>Пример  
 В этом примере используется метод <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> класса <xref:System.Windows.Automation.AutomationElement> для создания объекта <xref:System.Windows.Automation.InvokePattern> и вызова элемента управления с помощью метода <xref:System.Windows.Automation.InvokePattern.Invoke%2A> .  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
[!code-csharp[InvokePatternApp#1102](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1102)]
[!code-vb[InvokePatternApp#1102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1102)]  
  
## <a name="see-also"></a>См. также

- [Пример TogglePattern, ExpandCollapsePattern и InvokePattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
