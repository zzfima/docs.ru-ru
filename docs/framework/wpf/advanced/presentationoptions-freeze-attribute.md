---
title: Атрибут PresentationOptions:Freeze
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546075"
---
# <a name="presentationoptionsfreeze-attribute"></a>Атрибут PresentationOptions:Freeze
Наборы <xref:System.Windows.Freezable.IsFrozen%2A> состояние `true` в содержащем <xref:System.Windows.Freezable> элемента. Поведение по умолчанию для <xref:System.Windows.Freezable> без `PresentationOptions:Freeze` указан атрибут звучит <xref:System.Windows.Freezable.IsFrozen%2A> — `false` во время загрузки и в зависимости от Общие <xref:System.Windows.Freezable> поведение во время выполнения.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```  
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
|`PresentationOptions`|Префикс пространства имен XML, который может быть любой допустимой префиксной строкой, в соответствии со спецификацией XML 1.0. Префикс `PresentationOptions` используется в целях идентификации в этой документации.|  
|`freezableElement`|Элемент, который создает экземпляры любой производный класс от <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Примечания  
 `Freeze` Атрибут является единственным атрибутом или другого элемента программирования, определенного в `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` пространства имен XML. `Freeze` Атрибут существует в этом специальном пространстве имен, поэтому он может быть назначен в качестве игнорируемого, используя [mc: Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) как часть объявлений корневого элемента. Причина, `Freeze` должен иметь возможность быть ignorable не так как все [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] реализации процессора может замораживать <xref:System.Windows.Freezable> во время загрузки; эта возможность не является частью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] спецификации.  
  
 Возможность обработки `Freeze` специально создан атрибут для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессором, который обрабатывает [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для компиляции приложения. Атрибут не поддерживается для любого класса, и синтаксис атрибута не является расширяемым или изменяемые. При реализации собственных [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, вы можете параллельно закрепление поведение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор при обработке `Freeze` атрибут <xref:System.Windows.Freezable> элементов во время загрузки.  
  
 Любое значение для `Freeze` атрибут, отличный от `true` (без учета регистра) вызывает ошибку во время загрузки. (Указание `Freeze` атрибута `false` не является ошибкой, но он уже имеет значение по умолчанию, поэтому `false` не выполняет никаких действий).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable>  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
