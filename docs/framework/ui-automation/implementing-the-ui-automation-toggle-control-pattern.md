---
title: Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle
ms.date: 03/30/2017
helpviewer_keywords:
- Toggle control pattern
- control patterns, Toggle
- UI Automation, Toggle control pattern
ms.assetid: 3cfe875f-b0c0-413d-9703-5f14e6a1a30e
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 3d9ab6de0c398f466efb5535f34553b78a715c8e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394482"
---
# <a name="implementing-the-ui-automation-toggle-control-pattern"></a>Реализация шаблона элементов управления модели автоматизации пользовательского интерфейса Toggle
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>, включая сведения о методах и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 <xref:System.Windows.Automation.TogglePattern> Шаблон элемента управления используется для поддержки элементов управления, которые можно переключать между разными состояниями и поддерживать состояние после установки. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Toggle обратите внимание на следующие правила и соглашения.  
  
-   Элементы управления, которые не поддерживают состояние при активации, такие как кнопки, кнопки панели инструментов и гиперссылки, вместо этого шаблона должны реализовывать <xref:System.Windows.Automation.Provider.IInvokeProvider> .  
  
-   Элемент управления должен проходить по его <xref:System.Windows.Automation.ToggleState> в следующем порядке: <xref:System.Windows.Automation.ToggleState.On>, <xref:System.Windows.Automation.ToggleState.Off> и если поддерживается — <xref:System.Windows.Automation.ToggleState.Indeterminate>.  
  
-   <xref:System.Windows.Automation.TogglePattern> не предоставляет метод SetState(newState) из-за проблем, окружающих прямую установку флажка с тремя состояниями без прохода по его соответствующей последовательности <xref:System.Windows.Automation.ToggleState> .  
  
-   Элемент управления RadioButton не реализует <xref:System.Windows.Automation.Provider.IToggleProvider>, так как он не способен пройти по его допустимым состояниям.  
  
<a name="Required_Members_for_IToggleProvider"></a>   
## <a name="required-members-for-itoggleprovider"></a>Обязательные члены для IToggleProvider  
 Следующие свойства и методы обязательны для реализации <xref:System.Windows.Automation.Provider.IToggleProvider>.  
  
|Обязательный член|Тип члена|Примечания|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.TogglePattern.Toggle%2A>|Метод|Нет|  
|<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty>|Свойство.|Нет|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Получение состояния флажка с использованием модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
