---
title: 'Атрибут mc: Ignorable'
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 45b9ee94b35f368a9d0c96381083aa58c9a23f77
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998415"
---
# <a name="mcignorable-attribute"></a>Атрибут mc: Ignorable
Указывает, какие [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] префиксы пространства имен в файле разметки могут игнорироваться [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора. `mc:Ignorable` Атрибут поддерживает совместимость разметки для пользовательского сопоставления пространства имен и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Использование атрибута XAML (один префикс)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Использование атрибута XAML (два префикса)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 и т. д.*|Любая строка допустимый префикс, согласно спецификации XML 1.0.|  
|*ignorableUri*|Любой допустимый URI для назначения пространства имен, согласно спецификации XML 1.0.|  
|*ThisElementCanBeIgnored*|Элемент, который может обрабатываться средством [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций обработчиков, если базовый тип не может быть разрешена.|  
  
## <a name="remarks"></a>Примечания  
 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Префикс пространства имен является соглашением, рекомендуемый префикс для использования при сопоставлении [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имен совместимости [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Элементы или атрибуты, где префикс часть имени элемента определяется как `mc:Ignorable` не создают ошибок при обработке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора. Если этот атрибут не может быть разрешена для базового типа или конструкции программирования, то этот элемент игнорируется. Тем не менее, обратите внимание, что пропускаемые элементы по-прежнему могут создавать дополнительные синтаксические ошибки для дополнительных требований к элементу, побочных эффектов этого элемента не обрабатывается. К примеру, определенный элемент содержимого модели может потребоваться только один дочерний элемент, но если указанный дочерний элемент был в `mc:Ignorable` префикс и указанный дочерний элемент не удалось разрешить в тип, то [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора может создается ошибка.  
  
 `mc:Ignorable` применяется только для сопоставления пространства имен с идентификатором строки. `mc:Ignorable` не применяется для сопоставления пространства имен в сборках, указывающих [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] пространства имен и сборки (или по умолчанию для текущего исполняемый файл как сборку).  
  
 Если вы реализуете [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, не должны вызывать реализация обработчика, синтаксического анализа или обработки ошибок для разрешения типов для любого элемента или атрибута, который определяется префикс, который определяется как `mc:Ignorable`. Но реализация обработчика по-прежнему может вызывать исключения, которые являются побочным результатом сбоя загрузки или обработки, таких как в приведенном выше примере одного дочернего элемента элемента.  
  
 По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора будет игнорировать содержимое внутри игнорируемого элемента. Тем не менее, можно указать дополнительный атрибут, [атрибут mc: ProcessContent](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), для продолжения обработки содержимого в пределах игнорируемого элемента следующим доступным родительским элементом.  
  
 Можно указать несколько префиксов в атрибуте, используя один или несколько символов пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, которые не документированы в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Дополнительные сведения см. в разделе [спецификации совместимости разметки XML](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Markup.XamlReader>  
 [Атрибут PresentationOptions: Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
