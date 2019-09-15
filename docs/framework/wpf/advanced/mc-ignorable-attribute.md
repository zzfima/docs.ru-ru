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
ms.openlocfilehash: a72b2886c63a80a4887aa16fc6a952fa837a800f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991436"
---
# <a name="mcignorable-attribute"></a>Атрибут mc: Ignorable
Указывает, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] какие префиксы пространства имен [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , обнаруженные в файле разметки, могут игнорироваться процессором. Атрибут поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] так и для управления версиями. `mc:Ignorable`  
  
## <a name="xaml-attribute-usage-single-prefix"></a>Использование атрибута XAML (один префикс)  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>Использование атрибута XAML (два префикса)  
  
```xaml  
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
|*Игнораблепрефикс, ignorablePrefix1 и т. д.*|Любая допустимая строка префикса, согласно спецификации XML 1,0.|  
|*игнораблеури*|Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.|  
|*сиселементканбеигноред*|Элемент, который может игнорироваться [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализациями процессора, если базовый тип не может быть разрешен.|  
  
## <a name="remarks"></a>Примечания  
 Префикс пространства имен является рекомендуемым соглашением о префиксах [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для использования при сопоставлении пространства имен `http://schemas.openxmlformats.org/markup-compatibility/2006`Compatibility. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] `mc`  
  
 Элементы или атрибуты, для которых префиксная часть имени элемента определяются как `mc:Ignorable` , не будут вызывать ошибки при обработке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессором. Если этот атрибут не может быть разрешен в базовый тип или конструкцию программирования, этот элемент игнорируется. Обратите внимание, что пропущенные элементы могут по-прежнему создавать дополнительные ошибки синтаксического анализа для дополнительных требований к элементам, которые являются побочными эффектами для этого элемента, который не обрабатывается. Например, для конкретной модели содержимого элемента может потребоваться только один дочерний элемент, но если указанный дочерний элемент был `mc:Ignorable` в префиксе, а указанный дочерний элемент не удалось разрешить в тип, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] то процессор может вызывает ошибку.  
  
 `mc:Ignorable`применяется только к сопоставлениям пространств имен с строками идентификаторов. `mc:Ignorable`не применяется к сопоставлениям пространств имен в сборках, которые указывают пространство имен CLR и сборку (или по умолчанию для текущего исполняемого файла в качестве сборки).  
  
 При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора реализация процессора не должна вызывать ошибки синтаксического анализа или обработки при разрешении типов для любого элемента или атрибута, дополненного префиксом, который определен как `mc:Ignorable`. Но реализация процессора по-прежнему может вызывать исключения, которые являются вторичным результатом невозможности загрузки или обработки элемента, такого как пример одноэлементного элемента, заданный ранее.  
  
 По умолчанию [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор будет игнорировать содержимое внутри игнорируемого элемента. Однако можно указать дополнительный атрибут [MC: ProcessContent](mc-processcontent-attribute.md), чтобы потребовать непрерывную обработку содержимого в игнорируемом элементе следующим доступным родительским элементом.  
  
 В атрибуте можно указать несколько префиксов, используя один или несколько пробельных символов в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.  

 `http://schemas.openxmlformats.org/markup-compatibility/2006` Пространство имен определяет другие элементы и атрибуты, не описанные в этой области пакета SDK. Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Markup.XamlReader>
- [Атрибут PresentationOptions: Freeze](presentationoptions-freeze-attribute.md)
- [Общие сведения о языке XAML (WPF)](xaml-overview-wpf.md)
- [Документы в WPF](documents-in-wpf.md)
