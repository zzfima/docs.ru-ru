---
title: "Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
caps.latest.revision: "16"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 40e1c1357637678456bcee0fbbeb41ecff2766d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a>Включение навигации в поставщике фрагментов автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе содержится пример кода, демонстрирующий включение навигации в поставщике автоматизации пользовательского интерфейса для элемента, который находится в пределах фрагмента.  
  
## <a name="example"></a>Пример  
 В следующем примере кода реализуется метод <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> для элемента списка в списке. Родительский элемент является элементом списка, и одноуровневые элементы являются элементами в коллекции списка. Этот метод возвращает `null` (`Nothing` в Visual Basic) для направлений, которые не являются допустимыми; в данном случае <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> и <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, поскольку элемент не имеет дочерних элементов.  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о поставщиках автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Реализация поставщика автоматизации пользовательского интерфейса на стороне сервера](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
