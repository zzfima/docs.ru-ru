---
title: Общие сведения о типах элементов управления автоматизации пользовательского интерфейса
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control types
- control types, UI Automation
ms.assetid: 75159ef8-bd43-4d13-acb7-1f1fe9253160
ms.openlocfilehash: e9cbff2ec6496cabe827e075b737a8c6f16fee93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033076"
---
# <a name="ui-automation-control-types-overview"></a>Общие сведения о типах элементов управления автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: Модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Типы элементов управления[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] — это хорошо известные идентификаторы, которые можно использовать для указания вида элемента управления, например поля со списком или кнопки.  
  
 Известный идентификатор упрощает для вспомогательных устройств определение типов элементов управления, доступных в [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] , и способов взаимодействия с ними.  
  
<a name="UI_Automation_Control_Type_Requisites"></a>   
## <a name="ui-automation-control-type-requisites"></a>Необходимые компоненты элементов управления автоматизации пользовательского интерфейса  
 Тип элемента управления[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] предоставляют набор условий, которым должны соответствовать поставщики. При выполнении этих условий элемент управления может использовать имя типа определенного элемента управления. Каждый тип элемента управления использует следующие условия:  
  
- Шаблоны элементов управления[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — какие шаблоны элементов управления должны поддерживаться, какой шаблоны необязательные и какие шаблоны не должны поддерживаться элементом управления.  
  
- Значения свойств[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — какие значения свойств поддерживаются.  
  
- Структура дерева[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] — обязательная древовидная структура [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] элемента управления.  
  
 Если элемент управления удовлетворяет условиям определенного типа элемента управления, значение свойства <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A> указывает этот тип.  
  
<a name="Current_UI_Automation_Control_Types"></a>   
## <a name="current-ui-automation-control-types"></a>Текущие типы элементов управления автоматизации пользовательского интерфейса  
 Следующий список содержит текущий набор типов элементов управления [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] :  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления кнопки](../../../docs/framework/ui-automation/ui-automation-support-for-the-button-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Calendar](../../../docs/framework/ui-automation/ui-automation-support-for-the-calendar-control-type.md)  
  
- [Поддержка модели автоматизированного пользовательского интерфейса для типа элемента управления CheckBox](../../../docs/framework/ui-automation/ui-automation-support-for-the-checkbox-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ComboBox](../../../docs/framework/ui-automation/ui-automation-support-for-the-combobox-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления DataGrid](../../../docs/framework/ui-automation/ui-automation-support-for-the-datagrid-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления типа DataItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-dataitem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Document](../../../docs/framework/ui-automation/ui-automation-support-for-the-document-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Edit](../../../docs/framework/ui-automation/ui-automation-support-for-the-edit-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Group](../../../docs/framework/ui-automation/ui-automation-support-for-the-group-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Header](../../../docs/framework/ui-automation/ui-automation-support-for-the-header-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса типа элемента управления HeaderItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-headeritem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления типа Hyperlink](../../../docs/framework/ui-automation/ui-automation-support-for-the-hyperlink-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления изображения](../../../docs/framework/ui-automation/ui-automation-support-for-the-image-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления List](../../../docs/framework/ui-automation/ui-automation-support-for-the-list-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ListItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-listitem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Menu](../../../docs/framework/ui-automation/ui-automation-support-for-the-menu-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления MenuBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления MenuItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-menuitem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Pane](../../../docs/framework/ui-automation/ui-automation-support-for-the-pane-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ProgressBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-progressbar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления RadioButton](../../../docs/framework/ui-automation/ui-automation-support-for-the-radiobutton-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ScrollBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-scrollbar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Separator](../../../docs/framework/ui-automation/ui-automation-support-for-the-separator-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Slider](../../../docs/framework/ui-automation/ui-automation-support-for-the-slider-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Spinner](../../../docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления SplitButton](../../../docs/framework/ui-automation/ui-automation-support-for-the-splitbutton-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления StatusBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-statusbar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Tab](../../../docs/framework/ui-automation/ui-automation-support-for-the-tab-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления TabItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-tabitem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Table](../../../docs/framework/ui-automation/ui-automation-support-for-the-table-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Text](../../../docs/framework/ui-automation/ui-automation-support-for-the-text-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Thumb](../../../docs/framework/ui-automation/ui-automation-support-for-the-thumb-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления TitleBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-titlebar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ToolBar](../../../docs/framework/ui-automation/ui-automation-support-for-the-toolbar-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления ToolTip](../../../docs/framework/ui-automation/ui-automation-support-for-the-tooltip-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса типа элемента управления Tree](../../../docs/framework/ui-automation/ui-automation-support-for-the-tree-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления TreeItem](../../../docs/framework/ui-automation/ui-automation-support-for-the-treeitem-control-type.md)  
  
- [Поддержка модели автоматизации пользовательского интерфейса для типа элемента управления Window](../../../docs/framework/ui-automation/ui-automation-support-for-the-window-control-type.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Automation.ControlType>
