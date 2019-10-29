---
title: Реализация шаблона элемента управления MultipleView модели автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, MultipleView control pattern
- MultipleView control pattern
- control patterns, MultipleView
ms.assetid: 5bf1b248-ffee-48c8-9613-0b134bbe9f6a
ms.openlocfilehash: edef213c0f4d43a15b7c6842ef6c62e95544da66
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039501"
---
# <a name="implementing-the-ui-automation-multipleview-control-pattern"></a>Реализация шаблона элемента управления MultipleView модели автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе приводятся рекомендации и соглашения для реализации <xref:System.Windows.Automation.Provider.IMultipleViewProvider>, включая сведения о событиях и свойствах. Ссылки на дополнительные материалы перечислены в конце раздела.  
  
 Шаблон элемента управления <xref:System.Windows.Automation.MultipleViewPattern> используется для поддержки элементов управления, которые предоставляют несколько представлений одного набора сведений или дочерних элементов управления и способны переключаться между ними.  
  
 Примеры элементов управления, которые могут представлять несколько представлений, включают представление списка (которое может отображать его содержимое в виде эскизов, плиток, значков или сведений), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] диаграммы (круговые, линейные, линейчатые, значения ячеек с формулой), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] документы (обычные, веб-макеты, макеты печати, режим чтения, контур), календарь Microsoft Outlook (год, месяц, неделя, день) и обложки проигрывателя Microsoft Windows Media. Поддерживаемые представления определяются разработчиками элементов управления и относятся к конкретному элементу управления.  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Правила и соглашения реализации  
 При реализации шаблона элемента управления Multiple View обратите внимание на следующие правила и соглашения.  
  
- <xref:System.Windows.Automation.Provider.IMultipleViewProvider> также должен быть реализован в контейнере, который управляет текущим представлением, если он отличается от элемента управления, обеспечивающего текущее представление. Например, проводник содержит элемент управления "Список" для текущего содержимого папки, а представлением для этого элемента управления управляет приложение проводника.  
  
- Элемент управления, который может сортировать свое содержимое, не считается поддерживающим несколько представлений.  
  
- Коллекция представлений должна быть идентичной во всех экземплярах.  
  
- Имена представлений должны быть подходящими для использования в приложениях преобразования текста в речь, шрифта Брайля и других приложениях для удобства чтения.  
  
<a name="Required_Members_for_IMultipleViewProvider"></a>   
## <a name="required-members-for-imultipleviewprovider"></a>Обязательные члены для IMultipleViewProvider  
 Следующие свойства и методы обязательны для реализации IMultipleViewProvider.  
  
|Обязательные члены|Тип члена|Примечания|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.CurrentView%2A>|свойство;|Отсутствуют|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetSupportedViews%2A>|Метод|Отсутствуют|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A>|Метод|Отсутствуют|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A>|Метод|Отсутствуют|  
  
 Отсутствуют события, связанные с этим шаблоном элемента управления.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Исключения  
 Поставщик должен вызывать следующие исключения.  
  
|Тип исключения|Условие|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|Когда метод <xref:System.Windows.Automation.Provider.IMultipleViewProvider.SetCurrentView%2A> или <xref:System.Windows.Automation.Provider.IMultipleViewProvider.GetViewName%2A> вызывается с параметром, который не является членом коллекции поддерживаемых представлений.|  
  
## <a name="see-also"></a>См. также

- [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](ui-automation-control-patterns-overview.md)
- [Поддержка шаблонов элементов управления в поставщике автоматизации пользовательского интерфейса](support-control-patterns-in-a-ui-automation-provider.md)
- [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](ui-automation-control-patterns-for-clients.md)
- [Общие сведения о дереве модели автоматизации пользовательского интерфейса](ui-automation-tree-overview.md)
- [Использование кэширования в модели автоматизации пользовательского интерфейса](use-caching-in-ui-automation.md)
