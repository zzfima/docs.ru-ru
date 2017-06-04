---
title: "Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "шаблоны элементов управления, GridItem"
  - "шаблон элемента управления GridItem модели автоматизации пользовательского интерфейса"
  - "GridItem - шаблон элемента управления"
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
caps.latest.revision: 15
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 15
---
# Реализация шаблона элемента управления GridItem модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе рассматриваются рекомендации и правила для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>, включая сведения о свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 <xref:System.Windows.Automation.GridItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих шаблон элемента управления <xref:System.Windows.Automation.Provider.IGridProvider>. Примеры элементов управления, реализующие данный шаблон элемента управления в разделе [управления шаблон сопоставления для клиентов автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации <xref:System.Windows.Automation.Provider.IGridProvider>, обратите внимание на следующие правила и соглашения:  
  
-   Координаты сетки отсчитываются от нуля, начиная с верхней левой ячейки с координатами (0, 0).  
  
-   Объединенные ячейки будут сообщать свои <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> и <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> основании свойств их базовой ячейки, как определено в поставщике автоматизации пользовательского интерфейса. Как правило, это будет самая верхняя строка и крайний левый столбец.  
  
-   <xref:System.Windows.Automation.Provider.IGridItemProvider> не поддерживается активная обработка сетки, например объединение или разбиение ячеек.  
  
-   Элементы управления, реализующие <xref:System.Windows.Automation.Provider.IGridItemProvider> обычно может выполняться (то есть клиента автоматизации пользовательского интерфейса можно переходить между соседними элементами управления) с помощью клавиатуры.  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a>Обязательные члены для IGridItemProvider  
 Следующие свойства и методы необходимы для реализации <xref:System.Windows.Automation.Provider.IGridItemProvider>.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|Свойство|Нет|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|Свойство|Нет|  
  
 Этот шаблон элемента управления не имеет связанных методов или событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Этот шаблон элемента управления не имеет связанных исключений.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о шаблонах элементов управления автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Шаблоны модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Реализация шаблона элемента управления сеткой автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)   
 [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)