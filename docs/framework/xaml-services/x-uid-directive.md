---
title: Директива x:Uid
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 667b722097d091902cb65f2e6f0485a039f8a2ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561840"
---
# <a name="xuid-directive"></a>Директива x:Uid
Предоставляет уникальный идентификатор для элементов разметки. Во многих случаях этот уникальный идентификатор используется в процессах локализации XAML и средства.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`identifier`|Созданная вручную или автоматически строка, должно быть уникальным в файле при интерпретируется с `x:Uid` потребителя.|  
  
## <a name="remarks"></a>Примечания  
 В [MS-XAML] `x:Uid` определяется как директива. Дополнительные сведения см. в разделе [ \[MS-XAML\] раздел 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` является дискретным из `x:Name` оба из-за указанного сценария локализации XAML, а идентификаторы, используемые для локализации не имеют зависимости от особенностей модели программирования `x:Name`. Кроме того `x:Name` регулируется область имен XAML; Однако `x:Uid` не распространяется на любые языке XAML понятием ограничения уникальности. Обработчики XAML в широком смысле слова (процессоры, которые не являются частью процесса локализации) не требуются для обеспечения уникальности `x:Uid` значения. Эти задачи по существу источник значения. Требование уникальности из `x:Uid` значений в пределах одного источника XAML является обоснованным для потребителей значений, таких как процессы или инструменты выделенный глобализации. Это Типичная модель уникальности `x:Uid` значения должны быть уникальными в файле XML-кодировке, представляющий XAML.  
  
 Средства, которые имеют значительные знаний определенной схемы XAML можно выбрать область применения `x:Uid` только для true локализуемые строки, а не во всех случаях, где встречается строковое значение текста в разметке.  
  
 Платформы можно указать определенное свойство их объектной модели в качестве псевдонима для `x:Uid` путем применения атрибута <xref:System.Windows.Markup.UidPropertyAttribute> типу. Если структура указывает определенное свойство, не допускается указывать оба `x:Uid` и элемент с псевдонимом того же объекта. Если оба `x:Uid` и указаны член с псевдонимом, обычно вызывает API служб XAML .NET Framework <xref:System.Xaml.XamlDuplicateMemberException> для этого случая.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Дополнительные сведения о роли `x:Uid` процесс локализации WPF и форма BAML кода XAML см. раздел [Глобализация для WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) или <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [Глобализация для WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
