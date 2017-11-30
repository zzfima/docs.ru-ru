---
title: "Примеры регулярных выражений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d7fa8fe2bade9f20f71f846c717d79d6b6ffb36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-examples"></a>Примеры регулярных выражений
В этом разделе представлены примеры кодов, иллюстрирующих использование регулярных выражений в обычных приложениях.  
  
> [!NOTE]
>  <xref:System.Web.RegularExpressions> Пространство имен содержит ряд объекты регулярных выражений, реализующих предопределенные шаблоны регулярных выражений для разбора строк из документов HTML, XML и ASP.NET. Например <xref:System.Web.RegularExpressions.TagRegex> класс определяет открывающие теги в строке и <xref:System.Web.RegularExpressions.CommentRegex> класс определяет комментарии ASP.NET в строке.  
  
## <a name="in-this-section"></a>Содержание  
 [Пример. Поиск ссылок HREF](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 Пример ищет во входной строке и выводит значение атрибута href = «...» значений и их расположение в строке.  
  
 [Пример. Изменение форматов даты](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 Пример замены дат в формате мм/дд/гг на даты в формате дд мм гг.  
  
 [Практическое руководство. Извлечение протокола и номера порта из URL-адреса](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 Пример извлекает протокола и номера порта из строки, которая содержит URL-адрес. Например, для "http://www.contoso.com:8080/letters/readme.html" возвращается "http:8080".  
  
 [Практическое руководство. Исключение недопустимых символов из строки](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 Пример удаления недопустимых не буквенно-цифровых знаков из строки.  
  
 [Практическое руководство. Проверка строк на соответствие формату электронной почты](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 Пример, можно использовать, чтобы убедиться, что строка в формату электронной почты.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Text.RegularExpressions>  
 Класс библиотеки справочная информация о .NET **System.Text.RegularExpressions** пространства имен.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)  
 Общие сведения о регулярных выражениях в контексте языка программирования.  
  
 [Объектная модель регулярных выражений](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 Описывает классы регулярных выражений, содержащихся в `System.Text.RegularExpression` пространства имен и примеры их использования.  
  
 [Подробные сведения о поведении регулярных выражений](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 Сведения о возможностях и поведении регулярных выражений .NET.  
  
 [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.
