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
# <a name="regular-expression-examples"></a><span data-ttu-id="53753-102">Примеры регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="53753-102">Regular Expression Examples</span></span>
<span data-ttu-id="53753-103">В этом разделе представлены примеры кодов, иллюстрирующих использование регулярных выражений в обычных приложениях.</span><span class="sxs-lookup"><span data-stu-id="53753-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53753-104"><xref:System.Web.RegularExpressions> Пространство имен содержит ряд объекты регулярных выражений, реализующих предопределенные шаблоны регулярных выражений для разбора строк из документов HTML, XML и ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="53753-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="53753-105">Например <xref:System.Web.RegularExpressions.TagRegex> класс определяет открывающие теги в строке и <xref:System.Web.RegularExpressions.CommentRegex> класс определяет комментарии ASP.NET в строке.</span><span class="sxs-lookup"><span data-stu-id="53753-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53753-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="53753-106">In This Section</span></span>  
 [<span data-ttu-id="53753-107">Пример. Поиск ссылок HREF</span><span class="sxs-lookup"><span data-stu-id="53753-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="53753-108">Пример ищет во входной строке и выводит значение атрибута href = «...» значений и их расположение в строке.</span><span class="sxs-lookup"><span data-stu-id="53753-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="53753-109">Пример. Изменение форматов даты</span><span class="sxs-lookup"><span data-stu-id="53753-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="53753-110">Пример замены дат в формате мм/дд/гг на даты в формате дд мм гг.</span><span class="sxs-lookup"><span data-stu-id="53753-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="53753-111">Практическое руководство. Извлечение протокола и номера порта из URL-адреса</span><span class="sxs-lookup"><span data-stu-id="53753-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="53753-112">Пример извлекает протокола и номера порта из строки, которая содержит URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="53753-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="53753-113">Например, для "http://www.contoso.com:8080/letters/readme.html" возвращается "http:8080".</span><span class="sxs-lookup"><span data-stu-id="53753-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="53753-114">Практическое руководство. Исключение недопустимых символов из строки</span><span class="sxs-lookup"><span data-stu-id="53753-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="53753-115">Пример удаления недопустимых не буквенно-цифровых знаков из строки.</span><span class="sxs-lookup"><span data-stu-id="53753-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="53753-116">Практическое руководство. Проверка строк на соответствие формату электронной почты</span><span class="sxs-lookup"><span data-stu-id="53753-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="53753-117">Пример, можно использовать, чтобы убедиться, что строка в формату электронной почты.</span><span class="sxs-lookup"><span data-stu-id="53753-117">Provides an example that you can use to verify that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="53753-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="53753-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="53753-119">Класс библиотеки справочная информация о .NET **System.Text.RegularExpressions** пространства имен.</span><span class="sxs-lookup"><span data-stu-id="53753-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="53753-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="53753-120">Related Sections</span></span>  
 [<span data-ttu-id="53753-121">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="53753-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="53753-122">Общие сведения о регулярных выражениях в контексте языка программирования.</span><span class="sxs-lookup"><span data-stu-id="53753-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="53753-123">Объектная модель регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="53753-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="53753-124">Описывает классы регулярных выражений, содержащихся в `System.Text.RegularExpression` пространства имен и примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="53753-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="53753-125">Подробные сведения о поведении регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="53753-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="53753-126">Сведения о возможностях и поведении регулярных выражений .NET.</span><span class="sxs-lookup"><span data-stu-id="53753-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="53753-127">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="53753-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="53753-128">Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="53753-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
