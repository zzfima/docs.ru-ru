---
title: Атрибут mc:ProcessContent
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: dde304cc2b9db9cb01f9264ca1359b8979512cfa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458780"
---
# <a name="mcprocesscontent-attribute"></a>Атрибут mc:ProcessContent
Указывает, какие элементы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] должны по-прежнему обрабатываться соответствующими родительскими элементами, даже если непосредственный родительский элемент может игнорироваться процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], так как указан [атрибут MC: Ignorable](mc-ignorable-attribute.md). Атрибут `mc:ProcessContent` поддерживает совместимость разметки как для пользовательского сопоставления пространства имен, так и для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] управления версиями.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
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
|*игнораблепрефикс*|Любая допустимая строка префикса, согласно спецификации XML 1,0.|  
|*игнораблеури*|Любой допустимый URI для обозначения пространства имен в соответствии с спецификацией XML 1,0.|  
|*сиселементканбеигноред*|Элемент, который можно игнорировать с помощью [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] реализаций процессора, если базовый тип не может быть разрешен.|  
|*содержани*|*Сиселементканбеигноред* помечен как Ignorable. Если процессор не обрабатывает этот элемент, *[content]* обрабатывается *объектом*.|  
  
## <a name="remarks"></a>Заметки  
 По умолчанию обработчик [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое в игнорируемом элементе. Вы можете указать конкретный элемент, `mc:ProcessContent`, а процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] продолжит обрабатывать содержимое внутри элемента, пропускаемого пропуском. Обычно это используется, если содержимое вложено в несколько тегов, по крайней мере один из которых является игнорируемым и по крайней мере один из которых не может быть проигнорирован.  
  
 В атрибуте можно указать несколько префиксов, используя разделитель пробелов, например: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Пространство имен `http://schemas.openxmlformats.org/markup-compatibility/2006` определяет другие элементы и атрибуты, не описанные в этой области пакета SDK. Дополнительные сведения см. в разделе [Спецификация совместимости XML-разметки](https://go.microsoft.com/fwlink/?LinkId=73824).  
  
## <a name="see-also"></a>См. также

- [Атрибут mc: Ignorable](mc-ignorable-attribute.md)
- [Общие сведения о языке XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
