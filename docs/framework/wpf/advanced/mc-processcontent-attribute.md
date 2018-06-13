---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: 2e93734b8ab4aefca080736db3a512f272625271
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545257"
---
# <a name="mcprocesscontent-attribute"></a>Атрибут mc:ProcessContent
Определяет, какая [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] элементы по-прежнему содержимое должно быть обработано соответствующими родительскими элементами, даже если непосредственный родительский элемент может быть пропущен [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора из-за указания [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) . `mc:ProcessContent` Атрибут поддерживает совместимость разметки для пользовательского сопоставления пространства имен и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Любая строка допустимый префикс, в соответствии со спецификацией XML 1.0.|  
|*ignorableUri*|Любой допустимый URI для назначения пространства имен, в соответствии со спецификацией XML 1.0.|  
|*ThisElementCanBeIgnored*|Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализации процессора, если не удается разрешить базовый тип.|  
|*[сведения]*|*ThisElementCanBeIgnored* помечен как игнорируемые. Если обработчик игнорирует этот элемент *[сведения]* обрабатывается *объекта*.|  
  
## <a name="remarks"></a>Примечания  
 По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора будет игнорировать содержимое внутри игнорируемого элемента. Можно указать определенный элемент с `mc:ProcessContent`и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет продолжать обработку содержимого внутри игнорируемого элемента. Это обычно будет использоваться, если содержимое вложено в несколько тегов, хотя бы один из которых является игнорируемым и хотя бы один из которых не является игнорируемым.  
  
 Несколько префиксов может быть указан в атрибуте, используя разделитель, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, которые не описаны в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Дополнительные сведения см. в разделе [спецификация совместимости разметки XML](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>См. также  
 [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
