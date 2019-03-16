---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 20a25b36857a7116f3599e3fbbbe4b438540f782
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58037049"
---
# <a name="xmlspace-handling-in-xaml"></a>Обработка xml:space в языке XAML
`xml:space` Атрибут является атрибутом, определенные в XML, который объявляет поведение обработки значительных пробелов внутри элемента объекта. Это поведение относится к все содержимое (внутренний текст), содержащихся в элементе где `xml:space` объявляется, а также позволяет сфокусироваться на дочерние элементы.  
  
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
  
 Значение по умолчанию `xml:space` атрибут-значение литерала `"default"`. Для значения `"default"`, или если `xml:space` не указывается, по значительных пробелов синтаксического анализа выполняется обработка по умолчанию, как определено в разделе [-обработки пробелов в XAML](whitespace-processing-in-xaml.md).  
  
 Чтобы сохранить пробел в содержимом элемента объекта, укажите `xml:space="preserve"` данного объектного элемента.  
  
 В большинстве интерпретаций `xml:space` действие атрибута и значение атрибута относятся к дочерним элементам.  
  
 Подробное обсуждение обработки пробелов в XAML, см. в разделе [-обработки пробелов в XAML](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>См. также
- [Обработки пробелов в XAML](whitespace-processing-in-xaml.md)
- [Общие сведения о языке XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
