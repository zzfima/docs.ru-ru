---
title: Практическое руководство. Отображение миллисекунд в значениях даты и времени
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 36d99753503d9ba4b1bde4143c86ba184674e53e
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960405"
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>Практическое руководство. Отображение миллисекунд в значениях даты и времени
Стандартные методы форматирования даты и времени, например <xref:System.DateTime.ToString?displayProperty=nameWithType>, поддерживают часы, минуты и секунды, но не миллисекунды. В этом разделе показано, как включить компонент миллисекунд даты и времени в форматированные строки даты и времени.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>Отображение компонента миллисекунд для значения DateTime  
  
1. Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.  
  
2. Чтобы извлечь строковое представление компонента миллисекунд, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>или <xref:System.DateTimeOffset.ToString%2A> для значения даты и времени, передав ему в параметре `format` шаблон пользовательского формата `fff` или `FFF`, отдельно или с другим описателем пользовательского формата.  
  
## <a name="example"></a>Пример  
 Этот пример выводит в консоль компонент миллисекунд <xref:System.DateTime> и значение <xref:System.DateTimeOffset>, как отдельно, так и в составе более длинной строки даты и времени.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 Шаблон формата `fff` содержит конечные нули в значении миллисекунд. Шаблон формата `FFF` запрещает их. Эта разница показана в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Проблема с определением полного описателя пользовательского формата, содержащего компонент миллисекунд, состоит в том, что он жестко задает формат, который может не соответствовать взаимному расположению элементов времени в текущих региональных параметрах приложения. Вместо этого лучше всего извлечь один из шаблонов отображения даты и времени, определенных текущим объектом языка и региональных параметров <xref:System.Globalization.DateTimeFormatInfo>, а затем изменить его для поддержки миллисекунд. Этот подход также показан в примере. Он извлекает шаблон полного отображения даты и времени для текущих языка и региональных параметров, обратившись к свойству <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>, а затем добавляет в него пользовательский шаблон `.ffff` после шаблона секунд. Обратите внимание, что в примере используется регулярное выражение для выполнения этой операции в одном методе.  
  
 Описатель настраиваемого формата также используется для отображения дробной части секунд, отличной от миллисекунд. Например, описатель пользовательского формата `f` или `F` отображает десятые доли секунды, описатель `ff` или `FF` — сотые доли секунды, а описатель `ffff` или `FFFF` — десятитысячные доли секунды. Дробные части миллисекунд усекаются, а не округляются в возвращаемой строке. Эти описатели формата используются в следующем примере.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
> Существует возможность отображать малые дробные части секунды, например десятитысячные или стотысячные доли секунды. Однако эти значения могут не иметь смысла. Точность значений даты и времени зависит от разрешения системных часов. В операционной системе Windows NT 3.5 и более поздних версий, а также Windows Vista разрешение часов приблизительно соответствует 10–15 миллисекундам.  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization.DateTimeFormatInfo>
- [Строки настраиваемых форматов даты и времени](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
