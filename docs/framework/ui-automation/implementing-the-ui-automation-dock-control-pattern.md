---
title: Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Dock
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, dock
- dock control pattern
- UI Automation, dock control pattern
ms.assetid: ea3d2212-7c8e-4dd7-bf08-73141ca2d4fb
ms.openlocfilehash: b1213791609245209fa37e3cdcb0876c963bfeb0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180208"
---
# <a name="implementing-the-ui-automation-dock-control-pattern"></a>Реализация шаблона элемента управления модели автоматизации пользовательского интерфейса Dock
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IDockProvider>, включая сведения о свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.DockPattern> используется для предоставления свойств закрепления элемента управления в контейнере закрепления. Контейнер закрепления — это элемент управления, который позволяет упорядочить дочерние элементы по горизонтали и по вертикали друг относительно друга. Примеры элементов управления, реализующих данный шаблон элемента управления, см. в разделе [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
 ![Доковый контейнер с двумя доковыми дочерними элементами.](./media/uia-dockpattern-dockingexample.PNG "UIA_DockPattern_DockingExample")  
Пример закрепления из Visual Studio, где окно "Представление классов" — DockPosition.Right, а окно "Список ошибок" — DockPosition.Bottom  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Dock обратите внимание на следующие правила и соглашения.  
  
- <xref:System.Windows.Automation.Provider.IDockProvider> не предоставляет какие-либо свойства контейнера закрепления или какие-либо свойства элементов управления, закрепленных рядом с текущим элементом управления в контейнере закрепления.  
  
- Элементы управления закрепляются относительно друг друга в зависимости от их текущего z-порядка; чем больше z-порядок расположения, тем дальше они размещены от заданного края контейнера закрепления.  
  
- При изменении размеров контейнера закрепления все закрепленные элементы управления в контейнере будут перенесены с выравниванием по тому же краю, к которому они были первоначально прикреплены. Размеры закрепленных элементов управления также будут изменены для заполнения пробелов в контейнере согласно поведению закрепления их <xref:System.Windows.Automation.DockPosition>. Например, если указано <xref:System.Windows.Automation.DockPosition.Top> , левая и правая стороны элемента управления будут расширены для заполнения всего доступного пространства. Если указано <xref:System.Windows.Automation.DockPosition.Fill> , все четыре стороны элемента управления будут расширены для заполнения всего доступного пространства.  
  
- На системах с несколькими мониторами элементы управления должны закрепляться с левой или правой стороны текущего монитора. Если это невозможно, они должны закрепляться с левой стороны крайнего левого монитора или с правой стороны крайнего правого монитора.  
  
<a name="Required_Members_for_IDockProvider"></a>
## <a name="required-members-for-idockprovider"></a>Обязательные члены для IDockProvider  
 Следующие свойства и методы обязательны для реализации интерфейса IDockProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider.DockPosition%2A>|Свойство|None|  
|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A>|Метод|None|  
  
 Этот шаблон элемента управления не имеет связанных событий.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.Provider.IDockProvider.SetDockPosition%2A><br /><br /> - Если элемент управления не в состоянии выполнить запрошенный стиль дока.|  
  
## <a name="see-also"></a>См. также раздел

- [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
