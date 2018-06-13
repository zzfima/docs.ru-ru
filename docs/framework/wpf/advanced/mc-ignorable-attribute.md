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
ms.openlocfilehash: 7b8a2ef6e27bc6b25776157e59bef04b883fcb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546202"
---
# <a name="mcignorable-attribute"></a>Атрибут mc: Ignorable
Определяет, какая [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] может проигнорировать префиксы пространства имен в файле разметки [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора. `mc:Ignorable` Атрибут поддерживает совместимость разметки для пользовательского сопоставления пространства имен и [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.  
  
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
|*ignorablePrefix, ignorablePrefix1 и т. д.*|Любая строка допустимый префикс, в соответствии со спецификацией XML 1.0.|  
|*ignorableUri*|Любой допустимый URI для назначения пространства имен, в соответствии со спецификацией XML 1.0.|  
|*ThisElementCanBeIgnored*|Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализации процессора, если не удается разрешить базовый тип.|  
  
## <a name="remarks"></a>Примечания  
 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Префикс пространства имен — соглашение рекомендуемый префикс, который используется для сопоставления [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] имен совместимости [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Элементы или атрибуты, где префиксная часть имени элемента определяется как `mc:Ignorable` не создают ошибок при обработке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора. Если этот атрибут не может быть разрешена для базового типа или программных конструкций, этот элемент игнорируется. Обратите внимание, что пропущенные элементы по-прежнему может создавать дополнительные синтаксические ошибки для дополнительных требований к элементу, побочные эффекты этого элемента не обрабатывается. Для экземпляра конкретный элемент содержимого модели может потребоваться только один дочерний элемент, но если указанный дочерний элемент был с `mc:Ignorable` префикс и указанный дочерний элемент не удалось разрешить тип, то [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может процессора Возвращает ошибку.  
  
 `mc:Ignorable` применяется только для сопоставления пространства имен с идентификатором строки. `mc:Ignorable` не применяется для сопоставления пространства имен в сборках, указывающих [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] пространства имен и сборки (или по умолчанию для текущего исполняемого файла в качестве сборки).  
  
 Если вы реализуете [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора, не должны вызывать реализация обработчика, синтаксического анализа и обработки ошибок при приведении типа любого элемента или атрибута, которые уточняются префикс, который определяется как `mc:Ignorable`. Но реализация процессора по-прежнему может вызывать исключения, которые являются побочным результатом сбоя загрузки или обработки, такие как в приведенном выше примере одного дочернего элемента элемента.  
  
 По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора будет игнорировать содержимое внутри игнорируемого элемента. Тем не менее, можно указать дополнительный атрибут, [mc: ProcessContent атрибута](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), для продолжения обработки содержимого в пределах игнорируемого элемента следующим доступным родительским элементом.  
  
 Несколько префиксов, которые можно указать в атрибуте, используя один или несколько знаков пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] Пространство имен определяет другие элементы и атрибуты, которые не описаны в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]. Дополнительные сведения см. в разделе [спецификация совместимости разметки XML](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Markup.XamlReader>  
 [Атрибут PresentationOptions: Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
