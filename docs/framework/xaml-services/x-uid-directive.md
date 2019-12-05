---
title: Директива x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 32cfd9ab0cf6037c731b619e81a7504ac92d5fb9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837185"
---
# <a name="xuid-directive"></a>Директива x:Uid
Предоставляет уникальный идентификатор для элементов разметки. Во многих сценариях этот уникальный идентификатор используется процессами локализации XAML и инструментами.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`identifier`|Созданная вручную или автоматически сформированная строка, которая должна быть уникальной в файле, если она интерпретируется `x:Uid` потребителем.|  
  
## <a name="remarks"></a>Заметки  
 В [MS-XAML] `x:Uid` определен как директива. Дополнительные сведения см. в [разделе\[MS-XAML\] 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 `x:Uid` является дискретным от `x:Name` обоих из-за указанного сценария локализации XAML, поэтому идентификаторы, используемые для локализации, не имеют зависимостей от влияния модели программирования на `x:Name`. Кроме того, `x:Name` регулируется областью имен XAML; Однако `x:Uid` не регулируется какой-либо из концепций, определенных языком XAML, для обеспечения уникальности. Обработчики XAML в широком смысле (процессоры, не являющиеся частью процесса локализации) не должны обеспечивать уникальность `x:Uid` значений. Эта ответственность концептуально полагается на источник значений. Ожидание уникальности значений `x:Uid` в одном источнике XAML целесообразно для потребителей значений, таких как выделенные процессы или средства глобализации. Типичная модель уникальности заключается в том, что `x:Uid` значения уникальны в XML-файле, который представляет XAML.  
  
 Средства, имеющие существенные знания о конкретной схеме XAML, могут применять `x:Uid` только для истинно локализуемых строк, а не во всех случаях, когда в разметке встречается текстовое значение строки.  
  
 Платформы могут указывать конкретное свойство в своей объектной модели, чтобы быть псевдонимом для `x:Uid`, применяя <xref:System.Windows.Markup.UidPropertyAttribute> атрибута к определяющему типу. Если платформа определяет конкретное свойство, недопустимо указывать как `x:Uid`, так и член с псевдонимом для одного и того же объекта. Если указаны и `x:Uid`, и член с псевдонимом, .NET Framework API служб XAML, как правило, выдает <xref:System.Xaml.XamlDuplicateMemberException> в этом случае.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Дополнительные сведения о роли `x:Uid` в процессе локализации WPF и в форме BAML XAML см. в статье [глобализация для WPF](../wpf/advanced/globalization-for-wpf.md) или <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Глобализация для WPF](../wpf/advanced/globalization-for-wpf.md)
