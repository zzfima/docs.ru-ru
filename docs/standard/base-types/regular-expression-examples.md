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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4d2d3aced78d2afed3f0d1396efe5e954ef84102
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="regular-expression-examples"></a>Примеры регулярных выражений
В этом разделе представлены примеры кодов, иллюстрирующих использование регулярных выражений в обычных приложениях.  
  
> [!NOTE]
>  Пространство имен <xref:System.Web.RegularExpressions> содержит несколько объектов регулярных выражений, которые реализуют предопределенные шаблоны регулярных выражений для анализа строк из документов HTML, XML и ASP.NET. Например, класс <xref:System.Web.RegularExpressions.TagRegex> определяет в строке открывающие теги, а класс <xref:System.Web.RegularExpressions.CommentRegex> определяет в строке комментарии ASP.NET.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Пример. Поиск ссылок HREF](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 В этом примере выполняется поиск значения href="..." в исходных строках и выводятся найденные ссылки с указанием их позиций в строке.  
  
 [Пример. Изменение форматов даты](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 В этом примере заменяются даты в формате мм/дд/гг датами в формате дд-мм-гг.  
  
 [Практическое руководство. Извлечение протокола и номера порта из URL-адреса](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 В этом примере извлекаются протокол и номер порта из строки, содержащей URL-адрес. Например, для "http://www.contoso.com:8080/letters/readme.html" возвращается "http:8080".  
  
 [Практическое руководство. Исключение недопустимых символов из строки](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 В этом примере удаляются из строки недопустимые символы, не являющиеся буквенно-цифровыми.  
  
 [Практическое руководство. Проверка строк на соответствие формату электронной почты](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 Этот пример позволяет проверить, является ли строка допустимым адресом электронной почты.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Text.RegularExpressions>  
 Справочные сведения о библиотеке классов для пространства имен **System.Text.RegularExpressions** платформы .NET.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)  
 Общие сведения о регулярных выражениях в контексте языка программирования.  
  
 [Объектная модель регулярных выражений](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 Описание классов регулярных выражений, содержащихся в пространстве имен `System.Text.RegularExpression`, и примеры их использования.  
  
 [Подробные сведения о поведении регулярных выражений](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 Сведения о возможностях и поведении регулярных выражений платформы .NET.  
  
 [Элементы языка регулярных выражений — краткий справочник](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.
