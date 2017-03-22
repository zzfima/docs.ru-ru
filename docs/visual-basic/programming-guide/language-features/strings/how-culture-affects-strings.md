---
title: "Влияние языка и региональных параметров на строки в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- locale, effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 63228a40897b29d0324be73ca1a17bcb19af2a16
ms.lasthandoff: 03/13/2017

---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Влияние языка и региональных параметров на строки в Visual Basic
Эта страница справки рассматриваются как [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] использует сведения для выполнения строковых преобразований и сравнений, язык и региональные параметры.  
  
## <a name="when-to-use-culture-specific-strings"></a>Когда следует использовать строки, зависящие от языка и региональных параметров  
 Как правило следует использовать строки, зависящие от языка и региональных параметров для всех данных, адресованных и пользователям и использовать строки языка и региональных параметров для внутренних данных приложения.  
  
 Например если приложение запрашивает пользователям вводить дату в виде строки, следует ожидать, что пользователи для форматирования строки в соответствии с их языком и региональными параметрами и приложение должно соответственно конвертировать эту строку. Если приложение затем представляет эти данные в своем пользовательском интерфейсе, оно должно представлять языка и региональных параметров пользователя.  
  
 Однако если приложение загружает данные на центральный сервер, следует отформатировать строки в соответствии с одного определенного языка и региональных параметров, во избежание путаницы между потенциально разными форматами.  
  
## <a name="culture-sensitive-functions"></a>Функции, зависящие от культуры  
 Все [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] функции преобразования строк (за исключением `Str` и `Val` функции) использовать информацию о языке и региональных параметрах, чтобы убедиться в том, что преобразования и сравнения подходят для языка и региональных параметров пользователя приложения.  
  
 Ключ к успеху в использовании функции преобразования строк в приложениях, работающих на компьютерах с различных языковых и региональных параметров является понимание того, какие функции используют региональных параметров и использовать текущее значение языка и региональных параметров. Обратите внимание, что параметры языка и региональных параметров приложения по умолчанию наследуются от параметров языка и региональных параметров операционной системы. Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</xref:Microsoft.VisualBasic.Conversion.Oct%2A> </xref:Microsoft.VisualBasic.Conversion.Hex%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A> </xref:Microsoft.VisualBasic.Strings.ChrW%2A> </xref:Microsoft.VisualBasic.Strings.Chr%2A> </xref:Microsoft.VisualBasic.Strings.AscW%2A> </xref:Microsoft.VisualBasic.Strings.Asc%2A>  
  
 `Str` (Преобразование чисел в строки) и `Val` функции (преобразование строк в числа) не используют информацию о языке и региональных параметрах, при преобразовании между строками и числами. Вместо этого они распознают только точку (.) в качестве допустимого десятичного разделителя. Учитывающими аналогами этих функций:  
  
-   **Преобразования, использующие текущий язык и региональные параметры.** `CStr` И `Format` функции преобразования числа в строку и `CDbl` и `CInt` функции преобразования строки в число.  
  
-   **Преобразования, использующие определенного языка и региональных параметров.** Каждый объект number имеет `ToString(IFormatProvider)` метод, который преобразует число в строку и `Parse(String, IFormatProvider)` метод, который преобразует строку в число. Например `Double` тип предоставляет <xref:System.Double.ToString%28System.IFormatProvider%29>и <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>методы.</xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> </xref:System.Double.ToString%28System.IFormatProvider%29>  
  
 Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Conversion.Str%2A>и <xref:Microsoft.VisualBasic.Conversion.Val%2A>.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Conversion.Str%2A>  
  
## <a name="using-a-specific-culture"></a>С помощью определенного языка и региональных параметров  
 Представьте, что вы разрабатываете приложение, которое отправляет дату (форматированную как строку) веб-службы. В этом случае приложение должно использовать определенного языка и региональных параметров для преобразования строки. Чтобы продемонстрировать почему, рассмотрим результат использования даты <xref:System.DateTime.ToString>метод: Если приложение использует этот метод для форматирования даты 4 июля 2005 г., она возвращает «4/7/2005 12:00:00 AM» при запуске с английского языка США (en US), но возвращает» 04.07.2005 00:00:00» при запуске с культурой немецкий (de-DE).</xref:System.DateTime.ToString>  
  
 Если необходимо выполнить преобразование строк в формате определенной культуры, следует использовать `CultureInfo` класс, который встроен в [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Можно создать новый `CultureInfo` объект для определенного языка и региональных параметров, передав имя культуры <xref:System.Globalization.CultureInfo.%23ctor%2A>конструктор.</xref:System.Globalization.CultureInfo.%23ctor%2A> Поддерживаемые язык и региональные параметры перечислены в <xref:System.Globalization.CultureInfo>класса страницы справки.</xref:System.Globalization.CultureInfo>  
  
 Кроме того, можно получить экземпляр *инвариантного языка и региональных параметров* из <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>свойство.</xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> Инвариантный язык и региональные параметры основан на английском языке и региональных параметрах, но существуют некоторые различия. Например инвариантной указывает 24-часовом формате вместо 12-часовом формате.  
  
 Преобразование даты в культуре строку, передайте <xref:System.Globalization.CultureInfo>объект даты <xref:System.DateTime.ToString%28System.IFormatProvider%29>метод.</xref:System.DateTime.ToString%28System.IFormatProvider%29> </xref:System.Globalization.CultureInfo> Например, следующий код отображает «07/04/2005 00:00:00», независимо от параметров языка и региональных параметров приложения.  
  
 [!code-vb[VbVbalrConcepts&#1;](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  Литералы даты, всегда интерпретируются согласно английского языка и региональных параметров.  
  
## <a name="comparing-strings"></a>Сравнение строк  
 Существуют две важные ситуации, когда необходимы сравнения строк:  
  
-   **Сортировка данных для отображения пользователю.** Использование операций в зависимости от текущего языка и региональных параметров, чтобы правильно отсортировать строки.  
  
-   **Определение, если две строки внутри приложения точно соответствовать (обычно по соображениям безопасности).** Используйте операции, которые не учитывают текущего языка и региональных параметров.  
  
 Можно выполнить оба типа сравнений с [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A>функция.</xref:Microsoft.VisualBasic.Strings.StrComp%2A> Укажите необязательное `Compare` аргумент для управления типом сравнения: `Text` для большей части ввода и вывода `Binary` для определения точных соответствий.  
  
 `StrComp` Функция возвращает целое число, показывающее связь между двумя сравниваемыми строками на основе порядка сортировки. Положительное значение для результата указывает, что первая строка больше, чем второй строки. Отрицательный результат указывает меньше первой строки и нулевое значение отражает равенство между строками.  
  
 [!code-vb[VbVbalrStrings&#22;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 Можно также использовать [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] партнер `StrComp` функция, <xref:System.String.Compare%2A?displayProperty=fullName>метод.</xref:System.String.Compare%2A?displayProperty=fullName> Это статический перегруженный метод базового строкового класса. В следующем примере показано, как используется этот метод:  
  
 [!code-vb[VbVbalrStrings&#48;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 Для более детального контроля над выполнением сравнений можно использовать дополнительные перегрузки <xref:System.String.Compare%2A>метод.</xref:System.String.Compare%2A> С <xref:System.String.Compare%2A?displayProperty=fullName>, то можно использовать `comparisonType` для указания, какой тип сравнения, используемый аргумент.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
|Значение для `comparisonType` аргумент|Тип сравнения|Время использования|  
|---|---|---|  
|`Ordinal`|Сравнение, основанное на байтов, составляющих строку.|Используйте это значение при сравнении: идентификаторы с учетом регистра, параметры безопасности или других нелингвистических идентификаторов, где байты должны точно совпадать.|  
|`OrdinalIgnoreCase`|Сравнение, основанное на байтов, составляющих строку.<br /><br /> `OrdinalIgnoreCase`использует сведения инвариантного языка и региональных параметров, чтобы определить, когда два символа отличаются только регистром.|Используйте это значение при сравнении: идентификаторы без учета регистра, параметры безопасности и данных, хранящихся в Windows.|  
|`CurrentCulture` или `CurrentCultureIgnoreCase`|Сравнение на основе интерпретации строк текущего языка и региональных параметров.|Используйте это значение при сравнении: данных, отображаемых пользователю, большинства пользовательского ввода и других данных, требующих лингвистической интерпретации.|  
|`InvariantCulture` или `InvariantCultureIgnoreCase`|Сравнение на основе интерпретации строк инвариантного языка и региональных параметров.<br /><br /> Это отличается от `Ordinal` и `OrdinalIgnoreCase`, поскольку инвариантный язык и региональные параметры рассматривают символы, не входящие в их диапазон как эквиваленты независимых символов.|Используйте эти значения только при сравнении сохраняемых данных или отображении лингвистических данных, требующее фиксированного порядка сортировки.|  
  
### <a name="security-considerations"></a>Вопросы безопасности  
 Если приложение принимает решения относительно безопасности на основе результата сравнения или операции изменения регистра, то следует использовать операцию <xref:System.String.Compare%2A?displayProperty=fullName>метод и передайте `Ordinal` или `OrdinalIgnoreCase` для `comparisonType` аргумент.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Globalization.CultureInfo></xref:System.Globalization.CultureInfo>   
 [Знакомство со строками в Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
