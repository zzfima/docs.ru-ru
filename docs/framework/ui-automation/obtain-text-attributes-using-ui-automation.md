---
title: Получение атрибутов текста с помощью UI Automation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5f1e5cfbf72ebce605c7f08ae944dc3d235dcf7a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44183110"
---
# <a name="obtain-text-attributes-using-ui-automation"></a>Получение атрибутов текста с помощью UI Automation
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения атрибутов текста из диапазона текста. Диапазон текста может соответствовать текущему расположению курсора (или пустому выделению) в документе, связанному выделению текста, коллекции разрозненных выделений текста или всему текстовому содержимому документа.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано получение <xref:System.Windows.Automation.TextPattern.FontNameAttribute> из диапазона текста.  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TextPattern> в сочетании с классом <xref:System.Windows.Automation.Text.TextPatternRange> поддерживает базовые текстовые атрибуты, свойства и методы. Для функциональности элемента управления, не поддерживаемой <xref:System.Windows.Automation.TextPattern> или <xref:System.Windows.Automation.Text.TextPatternRange> , класс <xref:System.Windows.Automation.AutomationElement>предоставляет клиенту автоматизации пользовательского интерфейса методы для доступа к соответствующей собственной объектной модели.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/obtain-mixed-text-attribute-details-using-ui-automation.md)
