---
title: Примеры регулярных выражений
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- regular expressions [.NET Framework], examples
- regular expressions [.NET Framework]
- strings [.NET Framework], regular expressions
ms.assetid: e9fd53f2-ed56-4b09-b2ea-e9bc9d65e6d6
ms.openlocfilehash: 788fa2a6793e14189def4c30a0baf0d4a5cf6b0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128094"
---
# <a name="regular-expression-examples"></a><span data-ttu-id="31899-102">Примеры регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="31899-102">Regular Expression Examples</span></span>
<span data-ttu-id="31899-103">В этом разделе представлены примеры кодов, иллюстрирующих использование регулярных выражений в обычных приложениях.</span><span class="sxs-lookup"><span data-stu-id="31899-103">This section contains code examples that illustrate the use of regular expressions in common applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31899-104">Пространство имен <xref:System.Web.RegularExpressions> содержит несколько объектов регулярных выражений, которые реализуют предопределенные шаблоны регулярных выражений для анализа строк из документов HTML, XML и ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="31899-104">The <xref:System.Web.RegularExpressions> namespace contains a number of regular expression objects that implement predefined regular expression patterns for parsing strings from HTML, XML, and ASP.NET documents.</span></span> <span data-ttu-id="31899-105">Например, класс <xref:System.Web.RegularExpressions.TagRegex> определяет в строке открывающие теги, а класс <xref:System.Web.RegularExpressions.CommentRegex> определяет в строке комментарии ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="31899-105">For example, the <xref:System.Web.RegularExpressions.TagRegex> class identifies start tags in a string and the <xref:System.Web.RegularExpressions.CommentRegex> class identifies ASP.NET comments in a string.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31899-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="31899-106">In This Section</span></span>  
 [<span data-ttu-id="31899-107">Пример: поиск ссылок HREF</span><span class="sxs-lookup"><span data-stu-id="31899-107">Example: Scanning for HREFs</span></span>](../../../docs/standard/base-types/regular-expression-example-scanning-for-hrefs.md)  
 <span data-ttu-id="31899-108">В этом примере выполняется поиск значения href="..." в исходных строках и выводятся найденные ссылки с указанием их позиций в строке.</span><span class="sxs-lookup"><span data-stu-id="31899-108">Provides an example that searches an input string and prints out all the href="…" values and their locations in the string.</span></span>  
  
 [<span data-ttu-id="31899-109">Пример: Изменение форматов даты</span><span class="sxs-lookup"><span data-stu-id="31899-109">Example: Changing Date Formats</span></span>](../../../docs/standard/base-types/regular-expression-example-changing-date-formats.md)  
 <span data-ttu-id="31899-110">В этом примере заменяются даты в формате мм/дд/гг датами в формате дд-мм-гг.</span><span class="sxs-lookup"><span data-stu-id="31899-110">Provides an example that replaces dates in the form mm/dd/yy with dates in the form dd-mm-yy.</span></span>  
  
 [<span data-ttu-id="31899-111">Практическое руководство. Извлечение протокола и номера порта из URL-адреса</span><span class="sxs-lookup"><span data-stu-id="31899-111">How to: Extract a Protocol and Port Number from a URL</span></span>](../../../docs/standard/base-types/how-to-extract-a-protocol-and-port-number-from-a-url.md)  
 <span data-ttu-id="31899-112">В этом примере извлекаются протокол и номер порта из строки, содержащей URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="31899-112">Provides an example that extracts a protocol and port number from a string that contains a URL.</span></span> <span data-ttu-id="31899-113">Например, http://www.contoso.com:8080/letters/readme.html возвращает http:8080.</span><span class="sxs-lookup"><span data-stu-id="31899-113">For example, "http://www.contoso.com:8080/letters/readme.html" returns "http:8080".</span></span>  
  
 [<span data-ttu-id="31899-114">Практическое руководство. Исключение недопустимых символов из строки</span><span class="sxs-lookup"><span data-stu-id="31899-114">How to: Strip Invalid Characters from a String</span></span>](../../../docs/standard/base-types/how-to-strip-invalid-characters-from-a-string.md)  
 <span data-ttu-id="31899-115">В этом примере удаляются из строки недопустимые символы, не являющиеся буквенно-цифровыми.</span><span class="sxs-lookup"><span data-stu-id="31899-115">Provides an example that strips invalid non-alphanumeric characters from a string.</span></span>  
  
 [<span data-ttu-id="31899-116">Практическое руководство. Проверка строк на соответствие формату электронной почты</span><span class="sxs-lookup"><span data-stu-id="31899-116">How to: Verify that Strings Are in Valid Email Format</span></span>](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md)  
 <span data-ttu-id="31899-117">Содержит пример, с помощью которого можно проверить, имеет ли строка допустимый формат адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="31899-117">Provides an example that verifies that a string is in valid email format.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="31899-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="31899-118">Reference</span></span>  
 <xref:System.Text.RegularExpressions>  
 <span data-ttu-id="31899-119">Справочные сведения о библиотеке классов для пространства имен **System.Text.RegularExpressions** платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="31899-119">Provides class library reference information for the .NET **System.Text.RegularExpressions** namespace.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="31899-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="31899-120">Related Sections</span></span>  
 [<span data-ttu-id="31899-121">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="31899-121">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)  
 <span data-ttu-id="31899-122">Общие сведения о регулярных выражениях в контексте языка программирования.</span><span class="sxs-lookup"><span data-stu-id="31899-122">Provides an overview of the programming language aspect of regular expressions.</span></span>  
  
 [<span data-ttu-id="31899-123">Объектная модель регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="31899-123">The Regular Expression Object Model</span></span>](../../../docs/standard/base-types/the-regular-expression-object-model.md)  
 <span data-ttu-id="31899-124">Описание классов регулярных выражений, содержащихся в пространстве имен `System.Text.RegularExpression`, и примеры их использования.</span><span class="sxs-lookup"><span data-stu-id="31899-124">Describes the regular expression classes contained in the `System.Text.RegularExpression` namespace and provides examples of their use.</span></span>  
  
 [<span data-ttu-id="31899-125">Подробные сведения о поведении регулярных выражений</span><span class="sxs-lookup"><span data-stu-id="31899-125">Details of Regular Expression Behavior</span></span>](../../../docs/standard/base-types/details-of-regular-expression-behavior.md)  
 <span data-ttu-id="31899-126">Сведения о возможностях и поведении регулярных выражений платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="31899-126">Provides information about the capabilities and behavior of .NET regular expressions.</span></span>  
  
 [<span data-ttu-id="31899-127">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="31899-127">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 <span data-ttu-id="31899-128">Сведения о наборе символов, операторов и конструкций, которые можно использовать для определения регулярных выражений.</span><span class="sxs-lookup"><span data-stu-id="31899-128">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
