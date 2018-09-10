---
title: string (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: 8b70f1c1dcb39dcdde6ba24a1bdcdfc3084cfc97
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513104"
---
# <a name="string-c-reference"></a><span data-ttu-id="a9fea-102">string (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a9fea-102">string (C# Reference)</span></span>
<span data-ttu-id="a9fea-103">Тип `string` представляет последовательность, состоящую из нуля или более символов в кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="a9fea-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="a9fea-104">`string` является псевдонимом для <xref:System.String> в .NET.</span><span class="sxs-lookup"><span data-stu-id="a9fea-104">`string` is an alias for <xref:System.String> in .NET.</span></span>  
  
 <span data-ttu-id="a9fea-105">Несмотря на то, что `string` представляет собой ссылочный тип, операторы равенства (`==` и`!=`) по определению сравнивают не ссылки, а значения объектов `string`.</span><span class="sxs-lookup"><span data-stu-id="a9fea-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="a9fea-106">Это делает проверку равенства строк более интуитивно понятной.</span><span class="sxs-lookup"><span data-stu-id="a9fea-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="a9fea-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9fea-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="a9fea-108">Отображается значение True, а затем False, поскольку содержимое строк эквивалентно, однако `a` и `b` не относятся к одному и тому же экземпляру строки.</span><span class="sxs-lookup"><span data-stu-id="a9fea-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="a9fea-109">Оператор + объединяет строки:</span><span class="sxs-lookup"><span data-stu-id="a9fea-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="a9fea-110">При этом создается строковый объект, содержащий слова "good morning".</span><span class="sxs-lookup"><span data-stu-id="a9fea-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="a9fea-111">Строки *неизменяемы*, т. е. содержимое созданного строкового объекта изменить нельзя, хотя синтаксис выглядит так, будто это возможно.</span><span class="sxs-lookup"><span data-stu-id="a9fea-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="a9fea-112">Например, при написании кода компилятор фактически создает новый строковый объект для хранения новой последовательности символов, а затем этот новый объект назначается b.</span><span class="sxs-lookup"><span data-stu-id="a9fea-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="a9fea-113">После этого строка h может быть отправлена в мусор.</span><span class="sxs-lookup"><span data-stu-id="a9fea-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="a9fea-114">Оператор [] позволяет предоставить к отдельным символам `string` доступ только для чтения:</span><span class="sxs-lookup"><span data-stu-id="a9fea-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="a9fea-115">Строковые литералы имеют тип `string` и могут быть записаны в двух формах: в кавычках или с @-quoted.</span><span class="sxs-lookup"><span data-stu-id="a9fea-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="a9fea-116">Строковые литералы в кавычках заключаются в двойные кавычки ("):</span><span class="sxs-lookup"><span data-stu-id="a9fea-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="a9fea-117">Строковые литералы могут содержать любые символьные литералы.</span><span class="sxs-lookup"><span data-stu-id="a9fea-117">String literals can contain any character literal.</span></span> <span data-ttu-id="a9fea-118">Escape-последовательности включены.</span><span class="sxs-lookup"><span data-stu-id="a9fea-118">Escape sequences are included.</span></span> <span data-ttu-id="a9fea-119">В следующем примере escape-последовательность `\\` используется для получения обратной косой черты, `\u0066` — для получения буквы f, и `\n` — для получения новой строки.</span><span class="sxs-lookup"><span data-stu-id="a9fea-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```csharp  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="a9fea-120">Escape-код `\udddd` (где `dddd` состоит из четырех цифр) представляет символ Юникода U+`dddd`.</span><span class="sxs-lookup"><span data-stu-id="a9fea-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="a9fea-121">Также распознаются восьмизначные escape-коды Юникода: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="a9fea-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="a9fea-122">Строковые литералы verbatim начинаются с `@` и также заключаются в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a9fea-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="a9fea-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9fea-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="a9fea-124">Преимущество сток verbatim состоит в том, что escape-последовательности *не* обрабатываются, что позволяет легко написать, например, полное имя файла:</span><span class="sxs-lookup"><span data-stu-id="a9fea-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="a9fea-125">Чтобы добавить в строку @-quoted двойные кавычки, продублируйте этот символ:</span><span class="sxs-lookup"><span data-stu-id="a9fea-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="a9fea-126">Другие варианты использования специального символа `@` см. в разделе [@ — буквальный идентификатор](../tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="a9fea-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>  
  
 <span data-ttu-id="a9fea-127">Дополнительные сведения о строках в С# см. в разделе [Строки](../../../csharp/programming-guide/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9fea-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9fea-128">Пример</span><span class="sxs-lookup"><span data-stu-id="a9fea-128">Example</span></span>  
 [!code-csharp[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a9fea-129">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a9fea-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9fea-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a9fea-130">See Also</span></span>

- [<span data-ttu-id="a9fea-131">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a9fea-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a9fea-132">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a9fea-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a9fea-133">Рекомендации по использованию строк</span><span class="sxs-lookup"><span data-stu-id="a9fea-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)  
- [<span data-ttu-id="a9fea-134">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a9fea-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="a9fea-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a9fea-135">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a9fea-136">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="a9fea-136">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="a9fea-137">Типы значений</span><span class="sxs-lookup"><span data-stu-id="a9fea-137">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="a9fea-138">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a9fea-138">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)  
- [<span data-ttu-id="a9fea-139">Создание строк</span><span class="sxs-lookup"><span data-stu-id="a9fea-139">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)  
- [<span data-ttu-id="a9fea-140">Таблица форматирования числовых результатов</span><span class="sxs-lookup"><span data-stu-id="a9fea-140">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)
