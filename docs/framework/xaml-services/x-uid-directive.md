---
title: Директива x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 6e946c63227a06b2032ce27e61899c1b8f05ec9f
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58042974"
---
# <a name="xuid-directive"></a>Директива x:Uid
Предоставляет уникальный идентификатор для элементов разметки. Во многих случаях этот уникальный идентификатор используется процесс локализации XAML и инструменты.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`identifier`|Созданная вручную или автоматически формируемую строку, который должен быть уникален в файле при интерпретируется программой `x:Uid` потребителя.|  
  
## <a name="remarks"></a>Примечания  
 В [MS-XAML] `x:Uid` определяется как директива. Дополнительные сведения см. в разделе [ \[MS-XAML\] разделе 5.3.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` является дискретным из `x:Name` оба из-за указанного сценария локализации XAML и таким образом, чтобы идентификаторы, используемые для локализации не имеют зависимостей от особенностей модели программирования `x:Name`. Кроме того `x:Name` регулируется области видимости имен XAML; Однако `x:Uid` не регулируется с помощью любого языка, определенный XAML концепция ограничения уникальности. Процессоры XAML в широком смысле слова (процессоры, которые не являются частью процесса локализации) не ожидаются для обеспечения уникальности `x:Uid` значения. Что обязанности входит концептуально источник значения. Требование уникальности из `x:Uid` значения в пределах одного источника XAML является обоснованным для потребителей значений, таких как процессы или инструменты выделенный глобализации. Это Типичная модель уникальности `x:Uid` значения уникальны в пределах файла XML-кодировке, представляющий XAML.  
  
 Средства, которые имеют значительные сведений о конкретной схеме XAML можно выбрать область применения `x:Uid` только для true локализуемые строки, а не во всех случаях, где встречается строковое значение текста в разметке.  
  
 Платформы можно указать конкретного свойства в модели объекта в качестве псевдонима для `x:Uid` путем применения атрибута <xref:System.Windows.Markup.UidPropertyAttribute> типу. Если платформа задает определенное свойство, не допускается указывать оба `x:Uid` и член с псевдонимом в одном объекте. Если оба `x:Uid` и указаны член с псевдонимом, обычно вызывает API служб XAML платформы .NET Framework <xref:System.Xaml.XamlDuplicateMemberException> для этого случая.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Дополнительные сведения о роли `x:Uid` в процесс локализации WPF и форма BAML кода XAML, см. в разделе [Глобализация для WPF](../wpf/advanced/globalization-for-wpf.md) или <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Глобализация для WPF](../wpf/advanced/globalization-for-wpf.md)
