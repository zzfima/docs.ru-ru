---
title: Использование кэширования в модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
ms.openlocfilehash: 679192b611a423e095ee9acc956d247364940edf
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74800806"
---
# <a name="use-caching-in-ui-automation"></a>Использование кэширования в модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как реализовать кэширование шаблонов элементов управления и свойств <xref:System.Windows.Automation.AutomationElement> .  
  
### <a name="activate-a-cache-request"></a>Активация запроса кэша  
  
1. Создайте <xref:System.Windows.Automation.CacheRequest>.  
  
2. Укажите свойства и шаблоны для кэширования с помощью <xref:System.Windows.Automation.CacheRequest.Add%2A>.  
  
3. Укажите область кэширования, установив свойство <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> .  
  
4. Укажите представление поддерева, установив свойство <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> .  
  
5. Задайте для свойства <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> значение <xref:System.Windows.Automation.AutomationElementMode.None> , если хотите повысить эффективность, не получая полную ссылку на объекты. (Это сделает невозможным получение текущих значений из этих объектов.)  
  
6. Активируйте запрос с помощью <xref:System.Windows.Automation.CacheRequest.Activate%2A> в блоке `using` (`Using` в Microsoft Visual Basic .NET).  
  
 После получения объекта <xref:System.Windows.Automation.AutomationElement> или подписки на события деактивируйте запрос с помощью <xref:System.Windows.Automation.CacheRequest.Pop%2A> (если использовался <xref:System.Windows.Automation.CacheRequest.Push%2A> ) или удалив объект, созданный <xref:System.Windows.Automation.CacheRequest.Activate%2A>. (Используйте <xref:System.Windows.Automation.CacheRequest.Activate%2A> в блоке `using` (`Using` в Microsoft Visual Basic .NET).  
  
### <a name="cache-automationelement-properties"></a>Кэширование свойств AutomationElement  
  
1. Когда <xref:System.Windows.Automation.CacheRequest> активен, получите объекты <xref:System.Windows.Automation.AutomationElement> с помощью метода <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> или <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; или получите <xref:System.Windows.Automation.AutomationElement> как источник события, для которого вы зарегистрировались, когда был активен <xref:System.Windows.Automation.CacheRequest> . (Можно также создать кэш, передав <xref:System.Windows.Automation.CacheRequest> в GetUpdatedCache или в один из методов <xref:System.Windows.Automation.TreeWalker> .)  
  
2. Используйте <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> или получите свойство из свойства <xref:System.Windows.Automation.AutomationElement.Cached%2A> элемента <xref:System.Windows.Automation.AutomationElement>.  
  
### <a name="obtain-cached-patterns-and-their-properties"></a>Получение кэшированных шаблонов и их свойств  
  
1. Когда <xref:System.Windows.Automation.CacheRequest> активен, получите объекты <xref:System.Windows.Automation.AutomationElement> с помощью метода <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> или <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; или получите <xref:System.Windows.Automation.AutomationElement> как источник события, для которого вы зарегистрировались, когда был активен <xref:System.Windows.Automation.CacheRequest> . (Можно также создать кэш, передав <xref:System.Windows.Automation.CacheRequest> в GetUpdatedCache или в один из методов <xref:System.Windows.Automation.TreeWalker> .)  
  
2. Используйте метод <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> или <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> для получения кэшированного шаблона.  
  
3. Получите значения свойства из свойства `Cached` шаблона элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показаны различные аспекты кэширования при использовании метода <xref:System.Windows.Automation.CacheRequest.Activate%2A> для активации <xref:System.Windows.Automation.CacheRequest>.  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода показаны различные аспекты кэширования при использовании метода <xref:System.Windows.Automation.CacheRequest.Push%2A> для активации <xref:System.Windows.Automation.CacheRequest>. За исключением случая, когда вы хотите вкладывать запросы кэширования, предпочтительнее использовать метод <xref:System.Windows.Automation.CacheRequest.Activate%2A>.  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a>См. также:

- [Кэширование в клиентах автоматизации пользовательского интерфейса](caching-in-ui-automation-clients.md)
