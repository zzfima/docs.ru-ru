---
title: "Практическое руководство. Отображение миллисекунд в значениях даты и времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Практическое руководство. Отображение миллисекунд в значениях даты и времени
По умолчанию форматирования даты и времени методы, такие как <xref:System.DateTime.ToString?displayProperty=nameWithType>, включают часы, минуты и секунды значения времени, но не содержат миллисекунды. В этом разделе показано, как включить компонент миллисекунд даты и времени в форматированные строки даты и времени.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Отображение компонента миллисекунд для значения DateTime  
  
1.  Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.  
  
2.  Чтобы извлечь строковое представление компонента миллисекунд, вызовите значение даты и времени <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> или <xref:System.DateTimeOffset.ToString%2A> и передайте `fff` или `FFF` шаблона пользовательского формата, отдельно или с другого пользовательского формата Спецификаторы как `format` параметр.  
  
## <a name="example"></a>Пример  
 В примере показаны компонент миллисекунд для <xref:System.DateTime> и <xref:System.DateTimeOffset> на консоль, сама по себе и включается в более длинные строки даты и времени.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 Шаблон формата `fff` содержит конечные нули в значении миллисекунд. Шаблон формата `FFF` запрещает их. Эта разница показана в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Проблема с определением полного описателя пользовательского формата, содержащего компонент миллисекунд, состоит в том, что он жестко задает формат, который может не соответствовать взаимному расположению элементов времени в текущих региональных параметрах приложения. Лучшим вариантом будет его извлечение из дату и время отображения шаблонов, определенных в текущей культуре <xref:System.Globalization.DateTimeFormatInfo> объекта и изменить его, чтобы включать миллисекунды. Этот подход также показан в примере. Он извлекает текущий язык и региональные параметры полный шаблон даты и времени из <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> свойства, а затем вставляет пользовательский шаблон `.ffff` после его шаблоном секунд. Обратите внимание, что в примере используется регулярное выражение для выполнения этой операции в одном методе.  
  
 Описатель настраиваемого формата также используется для отображения дробной части секунд, отличной от миллисекунд. Например, описатель пользовательского формата `f` или `F` отображает десятые доли секунды, описатель `ff` или `FF` — сотые доли секунды, а описатель `ffff` или `FFFF` — десятитысячные доли секунды. Дробные части миллисекунд усекаются, а не округляются в возвращаемой строке. Эти описатели формата используются в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  Существует возможность отображать малые дробные части секунды, например десятитысячные или стотысячные доли секунды. Однако эти значения могут не иметь смысла. Точность значений даты и времени зависит от разрешения системных часов. В Windows NT 3.5 и более поздних версиях и [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] операционные системы, имеет разрешение часов приблизительно соответствует 10 – 15 миллисекундам.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скомпилируйте код из командной строки с помощью csc.exe или vb.exe. Для компиляции кода в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
