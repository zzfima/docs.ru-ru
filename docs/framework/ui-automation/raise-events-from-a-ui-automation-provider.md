---
title: Вызов событий из поставщика автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 3deb4c6716d83af4b05e15b5b8a4b89e28317406
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906611"
---
# <a name="raise-events-from-a-ui-automation-provider"></a>Вызов событий из поставщика автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержится пример кода, демонстрирующий вызов события из поставщика автоматизации пользовательского интерфейса.  
  
## <a name="example"></a>Пример  
 В следующем примере событие [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] вызывается в реализации пользовательского элемента управления "Кнопка". Эта реализация позволяет клиентскому приложению модели автоматизации пользовательского интерфейса имитировать нажатие кнопки.  
  
 Для исключения излишней обработки в этом примере проверяется <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> , чтобы увидеть, должны ли вызываться события.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
