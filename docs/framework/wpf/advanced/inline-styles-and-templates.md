---
title: "Встроенные стили и шаблоны"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2acb455db8f8bdc5a95bfd2462b651cebbb692c3
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="inline-styles-and-templates"></a>Встроенные стили и шаблоны
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет <xref:System.Windows.Style> объектов и объектов шаблона (<xref:System.Windows.FrameworkTemplate> подклассов) как способ определения внешнего вида элемента в ресурсах, так что они могут использоваться несколько раз. По этой причине атрибуты в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , принимающие аргументы типов <xref:System.Windows.Style> и <xref:System.Windows.FrameworkTemplate> почти всегда создают ресурсные ссылки на существующие стили и шаблоны вместо определения новых.  
  
## <a name="limitations-of-inline-styles-and-templates"></a>Ограничения встроенные стили и шаблоны  
 В [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], свойства стиля и шаблона формально могут задаваться одним из двух способов. Синтаксис атрибутов можно использовать для ссылки на стиль, который был определен в ресурсе, например `<` *объекта*`Style="{StaticResource`*myResourceKey*`}" .../>`. Или можно использовать синтаксис элемента свойства для определения встроенный стиль, например:  
  
 `<`*объекта*`>`  
  
 `<`*объекта*`.Style>`  
  
 `<` `Style`  `.../>`  
  
 `</`*объекта*`.Style>`  
  
 `</`*объекта*`>`  
  
 Использование атрибута является гораздо более распространенным. Стиль, определенный встроенным образом и не определенный в ресурсах, обязательно распространяется только на содержащий элемент и не может повторно использоваться так же просто, так как он не имеет ключа ресурса. В целом стиль, определенный ресурсом является более гибким, полезным и соответствующим Общие [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] отделения программной логики в коде из режима конструктора в разметке принцип модели программирования.  
  
 Обычно нет причин устанавливать встроенный стиль или шаблон, даже если вы собираетесь использовать этот стиль или шаблон в этом расположении. Большинство элементов, которые могут принимать стиль или шаблон, также поддерживают свойство и модель содержимого. Если используется любое логическое дерево можно создать с помощью стилей или шаблонов один раз, было бы даже проще заполнить это свойство содержимого с эквивалентными дочерними элементами в прямой разметке. Это будет полностью обойти механизмы стилей и шаблонов.  
  
 Возможны также другие синтаксисы, расширений разметки, которые возвращают объект для стилей и шаблонов. Два таких расширения, имеющие возможные сценарии включают в себя [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) и <xref:System.Windows.Data.Binding>.  
  
## <a name="see-also"></a>См. также  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
