---
title: Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
ms.openlocfilehash: 1200ebd42884220d2611729b87f4bf51e7a903a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446830"
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a>Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса

> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).

В этом разделе показано, как реализовать один или несколько шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса, чтобы клиентские приложения могли работать с элементами управления и получать данные из них.

## <a name="support-control-patterns"></a>Поддержка шаблонов элементов управления

1. Реализуйте соответствующие интерфейсы для шаблонов элементов управления, которые должен поддерживать элемент, таких как <xref:System.Windows.Automation.Provider.IInvokeProvider> для <xref:System.Windows.Automation.InvokePattern>.

2. Получите объект, содержащий вашу реализацию каждого интерфейса элемента управления в реализации <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>

## <a name="example"></a>Пример

В следующем примере показана реализация <xref:System.Windows.Automation.Provider.ISelectionProvider> для пользовательского списка с поддержкой единственного выбора. Он возвращает три свойства и получает текущий выбранный элемент.

[!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
[!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]

## <a name="example"></a>Пример

В следующем примере показана реализация метода <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> , который возвращает класс, реализующий <xref:System.Windows.Automation.Provider.ISelectionProvider>. Большинство элементов управления "список" также поддерживают другие шаблоны, но в этом примере для всех других идентификаторов шаблонов возвращается пустая ссылка (`Nothing` в Microsoft Visual Basic .NET).

[!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
[!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]

## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](ui-automation-providers-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](server-side-ui-automation-provider-implementation.md)
