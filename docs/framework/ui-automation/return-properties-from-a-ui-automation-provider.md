---
title: Возврат свойств от поставщика автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 7a637f759c952751c0472c51afa42a2c67c58624
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969104"
---
# <a name="return-properties-from-a-ui-automation-provider"></a>Возврат свойств от поставщика автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе содержится пример кода, показывающий, как поставщик автоматизации пользовательского интерфейса может возвращать свойства элемента клиентским приложениям.  
  
 Для любого свойства, которое этот поставщик не поддерживает явным образом, он должен возвращать `null` (`Nothing` в Visual Basic). Это гарантирует, что [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] будет пытаться получить свойство из другого источника, такого как поставщик основного окна.  
  
## <a name="example"></a>Пример  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о поставщиках автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
