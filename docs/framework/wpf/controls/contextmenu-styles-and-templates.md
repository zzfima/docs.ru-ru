---
title: "Стили и шаблоны элемента ContextMenu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbe7bdc39ed8b7cf342e7e3d2d3c9a3824a8b819
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="contextmenu-styles-and-templates"></a>Стили и шаблоны элемента ContextMenu
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ContextMenu> элемента управления. Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="contextmenu-parts"></a>Элементы контекстного меню  
 <xref:System.Windows.Controls.ContextMenu> Управления не имеет именованных частей.  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ContextMenu>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>. ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
## <a name="contextmenu-states"></a>Состояния ContextMenu  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ContextMenu> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание:|  
|-|-|-|  
|Valid|ValidationStates|Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.|  
  
## <a name="contextmenu-controltemplate-example"></a>Пример шаблона элемента управления ContextMenu  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ContextMenu> элемента управления.  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <xref:System.Windows.Controls.ControlTemplate> Использует следующие ресурсы.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Стили и шаблоны элемента управления](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
