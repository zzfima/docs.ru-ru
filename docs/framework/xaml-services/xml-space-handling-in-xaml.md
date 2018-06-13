---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: af971ad9ea74e123b939ff8d8488e4e45c5d4aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563471"
---
# <a name="xmlspace-handling-in-xaml"></a>Обработка xml:space в языке XAML
`xml:space` Атрибут является атрибутом, определенные в XML, который объявляет поведение обработки значимых пробелов внутри элемента объекта. Такое поведение применимо для всего содержимого (внутренний текст), содержащихся в элементе где `xml:space` объявляется, а также фокусирует на дочерние элементы.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- или -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Примечания  
 Определение `xml:space` атрибут в XAML, включая два возможных значения является производным от `xml:space` как определен как «специальный атрибут» по спецификации W3C для XML.  
  
 Значение по умолчанию `xml:space` атрибут-значение литерала `"default"`. Для значения `"default"`, или если `xml:space` не отражается на всех поведение значимых пробелов синтаксического анализа не обработку по умолчанию, как определено в разделе [Обработка пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Чтобы сохранить пробелы в содержимом элемента объекта, укажите `xml:space="preserve"` для этого элемента объекта.  
  
 В большинстве интерпретаций `xml:space` действие атрибута и значение атрибута распространяются на дочерние элементы.  
  
 Полное описание обработки пробелов в XAML см. в разделе [Обработка пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка пробелов в XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
