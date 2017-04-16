---
title: "Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса | Microsoft Docs"
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
  - "шаблоны элементов управления, прокрутки элемента"
  - "Шаблон элемента управления прокрутки элемента автоматизации пользовательского интерфейса"
  - "Scroll Item - шаблон элемента управления"
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
caps.latest.revision: 16
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 16
---
# Реализация шаблона элемента управления ScrollItem модели автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, которые хотят использовать управляемый [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] классы, определенные в <xref:System.Windows.Automation> пространства имен. Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], в разделе [API автоматизации Windows: автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе рассматриваются рекомендации и правила для реализации <xref:System.Windows.Automation.Provider.IScrollItemProvider>, включая сведения о свойствах, методы и события. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 <xref:System.Windows.Automation.ScrollItemPattern> используется для поддержки отдельных дочерних элементов управления контейнеров, реализующих шаблон элемента управления <xref:System.Windows.Automation.Provider.IScrollProvider>. Этот шаблон элемента управления действует как отдельный канал связи между дочерним элементом управления и его контейнером, чтобы контейнер гарантированно мог изменять видимое в настоящий момент содержимое (или область) в его области просмотра для отображения дочернего элемента управления. Примеры элементов управления, реализующие данный шаблон элемента управления в разделе [управления шаблон сопоставления для клиентов автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления ScrollItem обратите внимание на следующие правила и соглашения.  
  
-   Не требуется, чтобы элементы, содержащиеся в элементе управления "Окно" или "Полотно", реализовывали интерфейс IScrollItemProvider. В качестве альтернативы, однако они должны предоставлять действительное расположение для <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>. Это позволит использовать клиентское приложение автоматизации пользовательского интерфейса <xref:System.Windows.Automation.ScrollPattern> методы шаблона для отображения дочернего элемента контейнера элемента управления.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a>Обязательные члены для IScrollItemProvider  
 Следующий метод является обязательным для реализации интерфейса IScrollProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|-Метод|Нет|  
  
 Этот шаблон элемента управления не имеет связанных свойств или событий.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщики должны вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Если элемент не может быть прокручен в представлении:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о шаблонах элементов управления автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)   
 [Поддержка шаблонов элементов управления в поставщике модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)   
 [Шаблоны модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)   
 [Общие сведения о дереве модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)   
 [Использование кэширования в модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)