---
title: Практическое руководство. Использование специальных символов в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 59449637bb45f6b75462b6809c354af7972fc2e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740841"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="9a299-102">Практическое руководство. Использование специальных символов в XAML</span><span class="sxs-lookup"><span data-stu-id="9a299-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="9a299-103">Файлы разметки, созданные в Visual Studio, автоматически сохраняются в формате Юникода UTF-8, что означает, что большинство специальных символов, таких как диакритические знаки, кодируются правильно.</span><span class="sxs-lookup"><span data-stu-id="9a299-103">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="9a299-104">Но существует набор широко используемых специальных символов, которые обрабатываются по-другому.</span><span class="sxs-lookup"><span data-stu-id="9a299-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="9a299-105">Эти специальные символы соответствуют стандарту XML для кодирования консорциум W3C (W3C).</span><span class="sxs-lookup"><span data-stu-id="9a299-105">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="9a299-106">В следующей таблице показан синтаксис кодирования этого набора специальных символов:</span><span class="sxs-lookup"><span data-stu-id="9a299-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="9a299-107">Знак</span><span class="sxs-lookup"><span data-stu-id="9a299-107">Character</span></span>|<span data-ttu-id="9a299-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a299-108">Syntax</span></span>|<span data-ttu-id="9a299-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9a299-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="9a299-110">Символ "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="9a299-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="9a299-111">Символ "больше чем".</span><span class="sxs-lookup"><span data-stu-id="9a299-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="9a299-112">Символ амперсанда.</span><span class="sxs-lookup"><span data-stu-id="9a299-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="9a299-113">"</span><span class="sxs-lookup"><span data-stu-id="9a299-113">"</span></span>|`&quot;`|<span data-ttu-id="9a299-114">Символ двойной кавычки.</span><span class="sxs-lookup"><span data-stu-id="9a299-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="9a299-115">При создании файла разметки с помощью текстового редактора, например Блокнота Windows, необходимо сохранить файл в формате Юникода UTF-8, чтобы сохранить закодированные специальные символы.</span><span class="sxs-lookup"><span data-stu-id="9a299-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="9a299-116">В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.</span><span class="sxs-lookup"><span data-stu-id="9a299-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a299-117">Пример</span><span class="sxs-lookup"><span data-stu-id="9a299-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
