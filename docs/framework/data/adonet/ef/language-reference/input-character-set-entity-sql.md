---
title: "Набор символов ввода (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1a830d9df1f94bd21689cba9a9893cb9c344dfdb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="input-character-set-entity-sql"></a><span data-ttu-id="8c078-102">Набор символов ввода (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8c078-102">Input Character Set (Entity SQL)</span></span>
<span data-ttu-id="8c078-103">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] допускается использование символов Юникода в кодировке UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8c078-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] accepts UNICODE characters encoded in UTF-16.</span></span>  
  
 <span data-ttu-id="8c078-104">Строковые литералы могут содержать любой символ UTF-16, заключенный в одинарные кавычки.</span><span class="sxs-lookup"><span data-stu-id="8c078-104">String literals can contain any UTF-16 character enclosed in single quotes.</span></span> <span data-ttu-id="8c078-105">Например, N'文字列リテラル'.</span><span class="sxs-lookup"><span data-stu-id="8c078-105">For example, N'文字列リテラル'.</span></span> <span data-ttu-id="8c078-106">При сравнении строковых литералов используются первоначальные значения UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8c078-106">When string literals are compared, the original UTF-16 values are used.</span></span> <span data-ttu-id="8c078-107">Например, литерал N'ABC' становится разным при использовании в кодовых страницах для японской письменности и латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-107">For example, N'ABC' is different in Japanese and Latin codepages.</span></span>  
  
 <span data-ttu-id="8c078-108">Комментарии могут содержать любой символ UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8c078-108">Comments can contain any UTF-16 character.</span></span>  
  
 <span data-ttu-id="8c078-109">Экранированные идентификаторы могут содержать любой символ UTF-16, заключенный в квадратные скобки.</span><span class="sxs-lookup"><span data-stu-id="8c078-109">Escaped identifiers can contain any UTF-16 character enclosed in square brackets.</span></span> <span data-ttu-id="8c078-110">Например, [エスケープされた識別子].</span><span class="sxs-lookup"><span data-stu-id="8c078-110">For example, [エスケープされた識別子].</span></span> <span data-ttu-id="8c078-111">При сравнении экранированных идентификаторов UTF-16 учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="8c078-111">The comparison of UTF-16 escaped identifiers is case insensitive.</span></span> <span data-ttu-id="8c078-112">В языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] версии символов, которые внешне кажутся одинаковыми, но определены на разных кодовых страницах, считаются различными символами.</span><span class="sxs-lookup"><span data-stu-id="8c078-112">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="8c078-113">Например [ABC] эквивалентно [abc] Если соответствующие символы находятся на ту же кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="8c078-113">For example, [ABC] is equivalent to [abc] if the corresponding characters are from the same code page.</span></span> <span data-ttu-id="8c078-114">Тем не менее если же два идентификатора с разных кодовых страниц, не являются эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="8c078-114">However, if the same two identifiers are from different code pages, they are not equivalent.</span></span>  
  
 <span data-ttu-id="8c078-115">Пробельным символом считается любой пробельный символ UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8c078-115">White space is any UTF-16 white space character.</span></span>  
  
 <span data-ttu-id="8c078-116">Символом обозначения конца строки является любой нормализованный символ обозначения конца строки UTF-16.</span><span class="sxs-lookup"><span data-stu-id="8c078-116">A newline is any normalized UTF-16 newline character.</span></span> <span data-ttu-id="8c078-117">Например, значения '\n' и '\r\n' рассматриваются как символы обозначения конца строки, а значение '\r' не является символом обозначения конца строки.</span><span class="sxs-lookup"><span data-stu-id="8c078-117">For example, '\n' and '\r\n' are considered newline characters, but '\r' is not a newline character.</span></span>  
  
 <span data-ttu-id="8c078-118">Ключевыми словами, выражениями и знаками пунктуации могут быть любые символы UTF-16, нормализация которых приводит к получению латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-118">Keywords, expressions, and punctuation can be any UTF-16 character that normalizes to Latin.</span></span> <span data-ttu-id="8c078-119">Например, слово SELECT, представленное с помощью кодовой страницы для японской письменности, является допустимым ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="8c078-119">For example, SELECT in a Japanese codepage is a valid keyword.</span></span>  
  
 <span data-ttu-id="8c078-120">Ключевыми словами, выражениями и знаками пунктуации могут быть только символы латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-120">Keywords, expressions, and punctuation can only be Latin characters.</span></span> <span data-ttu-id="8c078-121">`SELECT` в кодовой странице на японском языке не является ключевым словом.</span><span class="sxs-lookup"><span data-stu-id="8c078-121">`SELECT` in a Japanese codepage is not a keyword.</span></span> <span data-ttu-id="8c078-122">Для представления знаков +, -, *, /, =, (, ), , [, ] и любых других языковых конструкций, применяемых в этом документе без заключения в кавычки, могут служить только символы латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-122">+, -, *, /, =, (, ), ‘, [, ] and any other language construct not quoted here can only be Latin characters.</span></span>  
  
 <span data-ttu-id="8c078-123">Простые идентификаторы могут быть представлены только с помощью символов латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-123">Simple identifiers can only be Latin characters.</span></span> <span data-ttu-id="8c078-124">Это позволяет избежать возникновения неоднозначности при сравнении, поскольку сравниваются первоначальные значения.</span><span class="sxs-lookup"><span data-stu-id="8c078-124">This avoids ambiguity during comparison, because original values are compared.</span></span> <span data-ttu-id="8c078-125">Например, идентификатор ABC становится разным, будучи представленным с помощью кодовых страниц для японской письменности и латиницы.</span><span class="sxs-lookup"><span data-stu-id="8c078-125">For example, ABC would be different in in Japanese and Latin codepages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c078-126">См. также</span><span class="sxs-lookup"><span data-stu-id="8c078-126">See Also</span></span>  
 [<span data-ttu-id="8c078-127">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8c078-127">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
