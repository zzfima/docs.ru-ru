---
title: Реализация шаблона элемента управления преобразованиями модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Transform
- Transform control pattern
- UI Automation, Transform control pattern
ms.assetid: 5f49d843-5845-4800-9d9c-56ce0d146844
ms.openlocfilehash: 1b26662b710b089349b921c7d6517cd86fe6d933
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57673110"
---
# <a name="implementing-the-ui-automation-transform-control-pattern"></a>Реализация шаблона элемента управления преобразованиями модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.ITransformProvider>, включая сведения о свойствах, методах и событиях. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.TransformPattern> используется для поддержки элементов управления, которые можно перемещать, поворачивать или изменять их размер в двумерном пространстве. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Transform обратите внимание на следующие правила и соглашения.  
  
-   Поддержка этого шаблона элемента управления не ограничена объектами на рабочем столе. Этот шаблон элемента управления также должен поддерживаться дочерними элементами объекта контейнера, если эти дочерние элементы можно перемещать, изменять их размер или свободно поворачивать в пределах контейнера.  
  
-   Объект нельзя перемещать, изменять его размер или поворачивать таким образом, что его итоговое положение на экране окажется полностью вне координат своего контейнера и поэтому он станет недоступным для клавиатуры или мыши (например, когда окно верхнего уровня перемещается за пределы экрана или дочерний объект перемещается за пределы границ окна просмотра контейнера). В этих случаях объект помещается максимально близко к запрошенным экранным координатам с переопределением верхней или левой координаты, чтобы они находились в границах контейнера.  
  
-   Для систем с несколькими мониторами при перемещении объекта, изменении его размера или повороте полностью за пределами координат объединенного рабочего стола объект помещается на основном мониторе максимально близко к запрошенным координатам.  
  
-   Все параметры и значения свойств являются абсолютными и не зависят от языка и региональных параметров.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-itransformprovider"></a>Обязательные члены для ITransformProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.ITransformProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanMove%2A>|Свойство.|Нет|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanResize%2A>|Свойство.|Нет|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.CanRotate%2A>|Свойство.|Нет|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A>|Метод|Нет|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Move%2A><br /><br /> Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanMoveProperty> имеет значение false.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Resize%2A><br /><br /> Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanResizeProperty> имеет значение false.|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.ITransformProvider.Rotate%2A><br /><br /> Если <xref:System.Windows.Automation.TransformPatternIdentifiers.CanRotateProperty> имеет значение false.|  
  
## <a name="see-also"></a>См. также
- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
