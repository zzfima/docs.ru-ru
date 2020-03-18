---
title: Руководство по программированию в C#. Определение представления числового значения в строке
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 15a21a6298f8f0a57e0189554246202b220dd259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157069"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a>Руководство по программированию в C#. Определение представления числового значения в строке
Чтобы определить, является ли строка допустимым представлением указанного числового типа, воспользуйтесь статическим методом `TryParse`, реализуемым всеми простыми числовыми типами, например <xref:System.DateTime> и <xref:System.Net.IPAddress>. В следующем примере показано, как определить, является ли число 108 допустимым типом [int](../../language-reference/builtin-types/integral-numeric-types.md).  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 Если строка содержит нечисловые знаки либо числовое значение слишком велико или мало для указанного типа, `TryParse` возвращает значение "false" и задает выходному параметру значение "0". В противном случае возвращается значение "true", а выходному параметру задается числовое значение строки.  
  
> [!NOTE]
> Строка может содержать только числовые знаки и оставаться недопустимой для типа, где используется метод `TryParse`. Например, "256" не является допустимым значением для `byte`, однако оно допустимо для `int`. "98,6" не является допустимым значением для `int`, однако оно допустимо для `decimal`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование `TryParse` со строковыми представлениями значений `long`, `byte` и `decimal`.  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Простые числовые типы также реализуют статический метод `Parse`, который вызывает исключение, если строка не является допустимым числом. В целом оператор `TryParse` более эффективен, поскольку если число не является допустимым, он просто возвращает значение "false".  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 Для проверки данных, введенных пользователем в такие элементы управления, как текстовые поля и поля со списком, всегда следует использовать метод `TryParse` или `Parse`.  
  
## <a name="see-also"></a>См. также раздел

- [Преобразование массива байтов в значение типа int](../types/how-to-convert-a-byte-array-to-an-int.md)
- [Практическое руководство. Преобразование строки в число](../types/how-to-convert-a-string-to-a-number.md)
- [Преобразование из шестнадцатеричных строк в числовые типы](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [Анализ числовых строк](../../../standard/base-types/parsing-numeric.md)
- [Типы форматирования](../../../standard/base-types/formatting-types.md)
