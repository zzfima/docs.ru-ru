---
title: Получение свойств элементов управления модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 1b82302ff89d2e8407871cbfba6c10e8322ac4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435500"
---
# <a name="get-ui-automation-element-properties"></a>Получение свойств элементов управления модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как получить свойства элемента [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
### <a name="get-a-current-property-value"></a>Получение значения текущего свойства  
  
1. Получите <xref:System.Windows.Automation.AutomationElement>, свойство которого вы хотите получить.  
  
2. Вызовите <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>или извлеките структуру свойств <xref:System.Windows.Automation.AutomationElement.Current%2A> и получите значение от одного из его членов.  
  
### <a name="get-a-cached-property-value"></a>Получение значения кэшированного свойства  
  
1. Получите <xref:System.Windows.Automation.AutomationElement>, свойство которого вы хотите получить. Свойство должно быть указано в <xref:System.Windows.Automation.CacheRequest>.  
  
2. Вызовите <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>или извлеките структуру свойств <xref:System.Windows.Automation.AutomationElement.Cached%2A> и получите значение от одного из его членов.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы получения текущих свойств <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>См. также

- [Свойства автоматизации пользовательского интерфейса для клиентов](ui-automation-properties-for-clients.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
- [Кэширование в клиентах автоматизации пользовательского интерфейса](caching-in-ui-automation-clients.md)
