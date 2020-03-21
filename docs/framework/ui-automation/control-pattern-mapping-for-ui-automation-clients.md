---
title: Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 689e649343c93d0670c6870098a09f61097f4fb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180231"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Сопоставление шаблона элемента управления для клиентов автоматизации пользовательского интерфейса
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе перечислены типы элементов управления и связанные с ними шаблоны элементов управления.  
  
 В таблице ниже шаблоны элементов управления распределены по следующим категориям.  
  
- Поддерживается. Элемент управления должен поддерживать этот шаблон элемента управления.  
  
- Условно поддерживается. Элемент управления может поддерживать этот шаблон элемента управления в зависимости от состояния элемента управления.  
  
- Не поддерживается. Элемент управления не поддерживает этот шаблон элемента управления; пользовательские элементы управления могут поддерживать этот шаблон элемента управления.  
  
> [!NOTE]
> Некоторые элементы управления имеют условную поддержку нескольких шаблонов элементов управления, в зависимости от функциональности этих элементов управления. Например, элемент управления "Пункт меню" имеет условную поддержку шаблона элемента управления <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>или <xref:System.Windows.Automation.SelectionItemPattern> , в зависимости от его функции в элементе управления "Меню".  
  
<a name="control_mapping_clients"></a>
## <a name="ui-automation-control-patterns-for-clients"></a>Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов  
  
|Тип элемента управления|Поддерживается|Условно поддерживается|Не поддерживается|  
|------------------|---------------|-------------------------|-------------------|  
|Кнопка|None|Invoke, Toggle, Expand Collapse|None|  
|Календарь|Grid, Table|Selection, Scroll|Значение|  
|Флажок|Toggle|None|None|  
|Combo Box|Развернуть свернуть|Selection, Value|Scroll|  
|Сетка данных|Сетка|Scroll, Selection, Table|None|  
|Data Item|Selection Item|Expand Collapse, Grid Item, Scroll Item, Table, Toggle, Value|None|  
|Документ|текст|Scroll, Value|None|  
|Изменить|None|Text, Range Value, Value|None|  
|Группа|None|Развернуть свернуть|None|  
|Заголовок|None|Преобразование|None|  
|элемент заголовка|None|Transform, Invoke|None|  
|Hyperlink|Invoke|Значение|None|  
|Образ —|None|Grid Item, Table Item|Invoke, Selection Item|  
|Список|None|Grid, Multiple View, Scroll, Selection|Таблица|  
|List Item|Selection Item|Expand Collapse, Grid Item, Invoke, Scroll Item, Toggle, Value|None|  
|Меню|None|None|None|  
|Строка меню|None|Expand Collapse, Dock, Transform|None|  
|Menu Item|None|Expand Collapse, Invoke, Selection Item, Toggle|None|  
|Панель|None|Dock Scroll, Transform|Окно|  
|Progress Bar|None|Range Value, Value|None|  
|Radio Button|Selection Item|None|Toggle|  
|Scroll Bar|None|Range Value|Scroll|  
|Разделитель|None|None|None|  
|Ползунок|None|Range Value, Selection, Value|None|  
|Spinner|None|Range Value, Selection, Value|None|  
|Разворачивающаяся кнопка|Invoke, Expand Collapse|None|None|  
|Строка состояния|None|Сетка|None|  
|Вкладка|Выбор|Scroll|None|  
|Tab Item|Selection Item|None|Invoke|  
|Таблица|Grid, Grid Item, Table, Table Item|None|None|  
|текст|None|Grid Item, Table Item, Text|Значение|  
|Бегунок|Преобразование|None|None|  
|Title Bar|None|None|None|  
|Tool Bar|None|Dock, Expand Collapse, Transform|None|  
|Tool Tip|None|Text, Window|None|  
|Дерево|None|Scroll, Selection|None|  
|Tree Item|Развернуть свернуть|Invoke, Scroll Item, Selection Item, Toggle|None|  
|Окно|Transform, Window|Закрепить|None|  
  
> [!NOTE]
> Если тип элемента управления не имеет поддерживаемых шаблонов элементов управления в списке, но имеет один или несколько условно поддерживаемых шаблонов элементов управления, то один из этих условных шаблонов элементов управления будет поддерживаться все время.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о модели автоматизации пользовательского интерфейса](ui-automation-overview.md)
