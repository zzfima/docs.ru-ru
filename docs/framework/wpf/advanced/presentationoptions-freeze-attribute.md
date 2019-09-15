---
title: Атрибут PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991426"
---
# <a name="presentationoptionsfreeze-attribute"></a>Атрибут PresentationOptions:Freeze
<xref:System.Windows.Freezable.IsFrozen%2A> Задает <xref:System.Windows.Freezable> состояние вэлементе,содержащемэлемент.`true` Поведение по умолчанию <xref:System.Windows.Freezable> для `PresentationOptions:Freeze` без <xref:System.Windows.Freezable.IsFrozen%2A> `false` атрибута задается во время загрузки и зависит от общего <xref:System.Windows.Freezable> поведения во время выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Префикс пространства имен XML, который может быть любой допустимой строкой префикса, согласно спецификации XML 1,0. Префикс `PresentationOptions` используется для идентификации в этой документации.|  
|`freezableElement`|Элемент, создающий экземпляр любого производного класса <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Примечания  
 Атрибут является единственным атрибутом или другим программным элементом, определенным `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` в пространстве имен XML. `Freeze` Атрибут существует в этом специальном пространстве имен, поэтому его можно назначить как игнорируемый, используя [атрибут MC: Ignorable](mc-ignorable-attribute.md) как часть объявлений корневого элемента. `Freeze` Причина, по `Freeze` которой должна быть возможна возможность пропуска, заключается в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] том, что не все реализации процессоров <xref:System.Windows.Freezable> способны заморозить во время загрузки. Эта возможность не [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] входит в спецификацию.  
  
 Возможность обработки `Freeze` атрибута в частности встроена в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор, обрабатывающий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] скомпилированные приложения. Атрибут не поддерживается ни одним классом, а синтаксис атрибутов не является расширяемым или изменяемым. При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] собственного процессора можно выбрать параллельное поведение [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] при фиксации процессора при обработке `Freeze` атрибута <xref:System.Windows.Freezable> элементов во время загрузки.  
  
 Любое значение атрибута, `Freeze` `true` Кроме (без учета регистра), приводит к ошибке времени загрузки. (Указание `Freeze` атрибута как `false` не является ошибкой, но он уже является значением по умолчанию, поэтому параметру `false` не требуется ничего).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Freezable>
- [Общие сведения об объектах класса Freezable](freezable-objects-overview.md)
- [Атрибут mc: Ignorable](mc-ignorable-attribute.md)
