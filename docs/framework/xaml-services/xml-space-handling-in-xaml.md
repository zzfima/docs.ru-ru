---
title: Обработка xml:space в языке XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 8f860f5ee42b5c1df43c4ec2b1003408bc1c0d8e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458795"
---
# <a name="xmlspace-handling-in-xaml"></a>Обработка xml:space в языке XAML
Атрибут `xml:space` представляет собой XML-определенный атрибут, объявляющий значимое поведение обработки пробелов в элементе Object. Это поведение относится ко всему содержимому (внутреннему тексту), содержащемуся в элементе, где `xml:space` объявлен, а также области для дочерних элементов.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 \- или -  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a>Заметки  
 Определение атрибута `xml:space` в XAML, включая два возможных значения, является производным от `xml:space`, как определено спецификацией W3C для XML в качестве "специального атрибута".  
  
 Значением по умолчанию для атрибута `xml:space` является литеральное значение `"default"`. Для значения `"default"`или если `xml:space` не указано вообще, поведением анализа значимого пробела является обработка по умолчанию, как определено в разделе [Обработка пробелов в XAML](whitespace-processing-in-xaml.md).  
  
 Чтобы сохранить пробелы в содержимом объектного элемента, укажите `xml:space="preserve"` для этого элемента объекта.  
  
 При большинстве интерпретаций `xml:space` атрибуты, а значение атрибута ограничивается дочерними элементами.  
  
 Полное описание обработки пробелов в XAML см. [в разделе Обработка пробелов в XAML](whitespace-processing-in-xaml.md).  
  
## <a name="see-also"></a>См. также

- [Обработка пробелов в XAML](whitespace-processing-in-xaml.md)
- [Общие сведения о языке XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
