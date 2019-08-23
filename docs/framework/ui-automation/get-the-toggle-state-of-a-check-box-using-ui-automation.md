---
title: Получение состояния флажка с использованием автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, getting toggle states of check boxes
- check boxes, getting toggle states of
- getting, toggle states of check boxes
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
ms.openlocfilehash: b7f519d9c59924ce055027c9e0d98b1d87578df5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968974"
---
# <a name="get-the-toggle-state-of-a-check-box-using-ui-automation"></a>Получение состояния флажка с использованием автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе показано, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] использовать для получения состояния переключения элемента управления.  
  
## <a name="example"></a>Пример  
 В этом примере используется <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> метод <xref:System.Windows.Automation.AutomationElement> класса для получения <xref:System.Windows.Automation.TogglePattern> объекта из элемента управления и возврата его <xref:System.Windows.Automation.ToggleState> свойства.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]
