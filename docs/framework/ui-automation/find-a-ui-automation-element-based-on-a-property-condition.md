---
title: Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 536a71532f02782f9e84bb2bd086af212a77c0da
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043669"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе содержится пример кода, в котором показано, как можно наыскать элемент в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дереве на основе конкретного свойства или свойств.  
  
## <a name="example"></a>Пример  
 В следующем примере задается набор условий свойства, которые определяют определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дереве. Затем выполняется поиск всех соответствующих элементов с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метода, включающего <xref:System.Windows.Automation.AndCondition> ряд логических операций для ограничения количества совпадающих элементов.  
  
> [!NOTE]
> При поиске из <xref:System.Windows.Automation.AutomationElement.RootElement%2A>необходимо попытаться получить только прямые дочерние элементы. Поиск потомков может осуществлять итерацию сотен или даже тысяч элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>См. также

- [Пример пункта меню InvokePattern и ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Получение элементов модели автоматизации пользовательского интерфейса](obtaining-ui-automation-elements.md)
- [Использование свойства AutomationID](use-the-automationid-property.md)
