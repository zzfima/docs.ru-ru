---
title: Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 829df66f49d5df5f5c8cf8d2b6cfa74f0a2172dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101137"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе перечислены типы элементов управления и связанные с ними шаблоны элементов управления.  
  
 В таблице ниже шаблоны элементов управления распределены по следующим категориям.  
  
-   Поддерживается. Элемент управления должен поддерживать этот шаблон элемента управления.  
  
-   Условно поддерживается. Элемент управления может поддерживать этот шаблон элемента управления в зависимости от состояния элемента управления.  
  
-   Не поддерживается. Элемент управления не поддерживает этот шаблон элемента управления; пользовательские элементы управления могут поддерживать этот шаблон элемента управления.  
  
> [!NOTE]
>  Некоторые элементы управления имеют условную поддержку нескольких шаблонов элементов управления, в зависимости от функциональности этих элементов управления. Например, элемент управления "Пункт меню" имеет условную поддержку шаблона элемента управления <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>или <xref:System.Windows.Automation.SelectionItemPattern> , в зависимости от его функции в элементе управления "Меню".  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов  
  
|Тип элемента управления|Поддерживается|Условно поддерживается|Не поддерживается|  
|------------------|---------------|-------------------------|-------------------|  
|Кнопка|Нет|Invoke, Toggle, Expand Collapse|Нет|  
|Календарь|Grid, Table|Selection, Scroll|Значение|  
|Флажок|Toggle|Нет|Нет|  
|Combo Box|Развернуть свернуть|Selection, Value|Scroll|  
|Data Grid|Grid|Scroll, Selection, Table|Нет|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|Нет|  
|Document|Текста|Scroll, Value|Нет|  
|Правка|Нет|Text, Range Value, Value|Нет|  
|Группа|Нет|Развернуть свернуть|Нет|  
|Header|Нет|Transform|Нет|  
|элемент заголовка|Нет|Transform, Invoke|Нет|  
|Гиперссылка|Вызвать|Значение|Нет|  
|Изображение|Нет|Grid Item, Table Item|Invoke, Selection Item|  
|Список|Нет|Grid, Multiple View, Scroll, Selection|Таблица|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|Нет|  
|Меню|Нет|Нет|Нет|  
|Menu Bar|Нет|Expand Collapse, Dock, Transform|Нет|  
|Menu Item|Нет|Expand Collapse, Invoke, Selection Item, Toggle|Нет|  
|Панель|Нет|Dock Scroll, Transform|Окно|  
|Progress Bar|Нет|Range Value, Value|Нет|  
|Radio Button|Selection Item|Нет|Toggle|  
|Scroll Bar|Нет|Range Value|Scroll|  
|Separator|Нет|Нет|Нет|  
|Slider|Нет|Range Value, Selection, Value|Нет|  
|Spinner|Нет|Range Value, Selection, Value|Нет|  
|Разворачивающаяся кнопка|Invoke, Expand Collapse|Нет|Нет|  
|Status Bar|Нет|Grid|Нет|  
|Tab|Выбранное|Scroll|Нет|  
|Tab Item|Selection Item|Нет|Вызвать|  
|Таблица|Grid, Grid Item, Table, Table Item|Нет|Нет|  
|Текста|Нет|Grid Item, Table Item, Text|Значение|  
|Бегунок|Transform|Нет|Нет|  
|Title Bar|Нет|Нет|Нет|  
|Tool Bar|Нет|Dock, Expand Collapse, Transform|Нет|  
|Tool Tip|Нет|Text, Window|Нет|  
|Дерево|Нет|Scroll, Selection|Нет|  
|Tree Item|Развернуть свернуть|Invoke, Scroll Item, Selection Item, Toggle|Нет|  
|Окно|Transform, Window|Закрепить|Нет|  
  
> [!NOTE]
>  Если тип элемента управления не имеет поддерживаемых шаблонов элементов управления в списке, но имеет один или несколько условно поддерживаемых шаблонов элементов управления, то один из этих условных шаблонов элементов управления будет поддерживаться все время.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-overview.md)
