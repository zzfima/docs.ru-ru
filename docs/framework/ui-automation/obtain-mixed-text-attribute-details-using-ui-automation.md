---
title: Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d0e4c005-abd1-42bb-92a4-5faf87097311
ms.openlocfilehash: 13ebc6aefe925ecefe48a9b0fa8cf7a6ecd3c454
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042956"
---
# <a name="obtain-mixed-text-attribute-details-using-ui-automation"></a>Получение сведений об атрибутах смешанного текста с помощью модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API службы автоматизации Windows: Модель автоматизации](https://go.microsoft.com/fwlink/?LinkID=156746)пользовательского интерфейса.  
  
 В этом разделе показано, как использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для получения сведений об атрибутах текста из текстового диапазона, охватывающего несколько значений атрибутов. Диапазон текста может соответствовать текущему расположению курсора (или пустому выделению) в документе, связанному выделению текста, коллекции разрозненных выделений текста или всему текстовому содержимому документа.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется получение <xref:System.Windows.Automation.TextPattern.FontNameAttribute> из текстового диапазона, где метод <xref:System.Windows.Automation.Text.TextPatternRange.GetAttributeValue%2A> возвращает объект <xref:System.Windows.Automation.TextPattern.MixedAttributeValue> .  
  
[!code-csharp[FindText#RetrieveMixedAttributes](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#retrievemixedattributes)]
[!code-vb[FindText#RetrieveMixedAttributes](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#retrievemixedattributes)]  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TextPattern> в сочетании с классом <xref:System.Windows.Automation.Text.TextPatternRange> поддерживает базовые текстовые атрибуты, свойства и методы. Для функциональности элемента управления, не поддерживаемой <xref:System.Windows.Automation.TextPattern> или <xref:System.Windows.Automation.Text.TextPatternRange>, класс <xref:System.Windows.Automation.AutomationElement> предоставляет клиенту автоматизации пользовательского интерфейса методы для доступа к соответствующей собственной объектной модели.  
  
## <a name="see-also"></a>См. также

- [Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса](ui-automation-textpattern-overview.md)
- [Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса](add-content-to-a-text-box-using-ui-automation.md)
- [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](find-and-highlight-text-using-ui-automation.md)
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Получение атрибутов текста с помощью модели автоматизации пользовательского интерфейса](obtain-text-attributes-using-ui-automation.md)
