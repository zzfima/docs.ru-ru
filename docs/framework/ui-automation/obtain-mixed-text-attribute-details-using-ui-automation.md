---
title: Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 8b7d3519a9f106a6679a9b2a404ed400bb6ae4a1
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856729"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения сведений об атрибутах текста из текстового диапазона, охватывающего несколько значений атрибутов. Диапазон текста может соответствовать текущему расположению курсора (или пустому выделению) в документе, связанному выделению текста, коллекции разрозненных выделений текста или всему текстовому содержимому документа.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется получение <xref:System.Windows.Automation.TextPattern.FontNameAttribute> из текстового диапазона, где метод <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> возвращает объект <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .  
  
 [!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
 [!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TextPattern> в сочетании с классом <xref:System.Windows.Automation.Text.TextPatternRange> поддерживает базовые текстовые атрибуты, свойства и методы. Для функциональности элемента управления, не поддерживаемой <xref:System.Windows.Automation.TextPattern> или <xref:System.Windows.Automation.Text.TextPatternRange>, класс <xref:System.Windows.Automation.AutomationElement> предоставляет клиенту автоматизации пользовательского интерфейса методы для доступа к соответствующей собственной объектной модели.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)  
 [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Получение атрибутов текста с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/obtain-text-attributes-using-ui-automation.md)
