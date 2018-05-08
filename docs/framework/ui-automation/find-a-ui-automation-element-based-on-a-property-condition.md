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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: da455b10425c9e0b20a644679358dde469ed92e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Нахождение Элемента Автоматизации Пользовательского Интерфейса в Зависимости от Состояния Свойства
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержится пример кода, демонстрирующий способы поиска элемента в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] дерева на основе конкретного свойства или свойств.  
  
## <a name="example"></a>Пример  
 В следующем примере набор состояний свойства указаны, которые задают определенный элемент (или элементы), представляющие интерес в <xref:System.Windows.Automation.AutomationElement> дерева. Затем выполняется поиск всех соответствующих элементов с <xref:System.Windows.Automation.AutomationElement.FindAll%2A> метод, который включает ряд <xref:System.Windows.Automation.AndCondition> логические операции, чтобы ограничить число соответствующих элементов.  
  
> [!NOTE]
>  При поиске с <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, вы должны пытаться получить только прямые потомки. Поиск потомков может выполнить итерацию по сотням или даже тысячам элементов, что может привести к переполнению стека. Если вы пытаетесь получить определенный элемент на более низком уровне, необходимо запустить поиск из окна приложения или из контейнера на более низком уровне.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>См. также  
 [InvokePattern и образец элемента меню ExpandCollapsePattern](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [Получение элементов модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [Использование свойства AutomationID](../../../docs/framework/ui-automation/use-the-automationid-property.md)
