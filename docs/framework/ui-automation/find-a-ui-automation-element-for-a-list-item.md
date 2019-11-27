---
title: Нахождение элемента автоматизации пользовательского интерфейса для элемента списка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items, finding elements for
- elements, finding for list items
- UI Automation, finding elements for List items
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
ms.openlocfilehash: 63181de26f7d8efda99d5b5d71b006cde44823a3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433548"
---
# <a name="find-a-ui-automation-element-for-a-list-item"></a>Нахождение элемента автоматизации пользовательского интерфейса для элемента списка
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе показано, как получить <xref:System.Windows.Automation.AutomationElement> для элемента в списке, если известен индекс элемента.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два способа получения указанного элемента из списка, один из которых использует <xref:System.Windows.Automation.TreeWalker>, а другой — с помощью <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 Первый метод, как правило, быстрее подходит для [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] элементов управления, но второй — быстрее для элементов управления Windows Presentation Foundation (WPF).  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## <a name="see-also"></a>См. также:

- [Получение элементов модели автоматизации пользовательского интерфейса](obtaining-ui-automation-elements.md)
