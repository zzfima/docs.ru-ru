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
ms.openlocfilehash: e14ab0ebc7d44e2792307b16c7c0581ff7a71bc6
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740823"
---
# <a name="mcignorable-attribute"></a>Атрибут mc: Ignorable
Указывает, какие префиксы пространства имен XML, обнаруженные в файле разметки, могут игнорироваться процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Атрибут `mc:Ignorable` поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, так и для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.  
  
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
|*сиселементканбеигноред*|Элемент, который можно игнорировать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций процессора, если базовый тип не может быть разрешен.|  
  
## <a name="remarks"></a>Заметки  
 Префикс пространства имен XML `mc` является рекомендуемым соглашением о префиксах для использования при сопоставлении `http://schemas.openxmlformats.org/markup-compatibility/2006`пространства имен совместимости [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Элементы или атрибуты, в которых префиксная часть имени элемента определяется как `mc:Ignorable`, не вызывает ошибок при обработке процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Если этот атрибут не может быть разрешен в базовый тип или конструкцию программирования, этот элемент игнорируется. Обратите внимание, что пропущенные элементы могут по-прежнему создавать дополнительные ошибки синтаксического анализа для дополнительных требований к элементам, которые являются побочными эффектами для этого элемента, который не обрабатывается. Например, для конкретной модели содержимого элемента может потребоваться только один дочерний элемент, но если указанный дочерний элемент находился в префиксе `mc:Ignorable`, а указанный дочерний элемент не удалось разрешить в тип, то процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может вызвать ошибку.  
  
 `mc:Ignorable` применяется только к сопоставлениям пространств имен с строками идентификаторов. `mc:Ignorable` не применяется к сопоставлениям пространств имен в сборках, которые указывают пространство имен CLR и сборку (или по умолчанию для текущего исполняемого файла в качестве сборки).  
  
 При реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора реализация процессора не должна вызывать ошибки синтаксического анализа или обработки при разрешении типов для любого элемента или атрибута, дополненного префиксом, который определен как `mc:Ignorable`. Но реализация процессора по-прежнему может вызывать исключения, которые являются вторичным результатом невозможности загрузки или обработки элемента, такого как пример одноэлементного элемента, заданный ранее.  
  
 По умолчанию обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое в игнорируемом элементе. Однако можно указать дополнительный атрибут [MC: ProcessContent](mc-processcontent-attribute.md), чтобы потребовать непрерывную обработку содержимого в игнорируемом элементе следующим доступным родительским элементом.  
  
 В атрибуте можно указать несколько префиксов, используя один или несколько символов пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.  

 Пространство имен `http://schemas.openxmlformats.org/markup-compatibility/2006` определяет другие элементы и атрибуты, не описанные в этой области пакета SDK. Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Markup.XamlReader>
- [Атрибут PresentationOptions: Freeze](presentationoptions-freeze-attribute.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Документы в WPF](documents-in-wpf.md)
