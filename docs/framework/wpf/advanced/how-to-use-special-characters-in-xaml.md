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
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377967"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="60eea-102">Практическое руководство. Использование специальных символов в XAML</span><span class="sxs-lookup"><span data-stu-id="60eea-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="60eea-103">Файлы разметки, которые создаются в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] , автоматически сохраняются в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, это означает, что большинство специальных символов, таких как знаки ударения, кодируются правильно.</span><span class="sxs-lookup"><span data-stu-id="60eea-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="60eea-104">Но существует набор широко используемых специальных символов, которые обрабатываются по-другому.</span><span class="sxs-lookup"><span data-stu-id="60eea-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="60eea-105">Эти специальные знаки соответствуют [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] стандарту кодирования.</span><span class="sxs-lookup"><span data-stu-id="60eea-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="60eea-106">В следующей таблице показан синтаксис кодирования этого набора специальных символов:</span><span class="sxs-lookup"><span data-stu-id="60eea-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="60eea-107">Знак</span><span class="sxs-lookup"><span data-stu-id="60eea-107">Character</span></span>|<span data-ttu-id="60eea-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60eea-108">Syntax</span></span>|<span data-ttu-id="60eea-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="60eea-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="60eea-110">Символ "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="60eea-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="60eea-111">Символ "больше чем".</span><span class="sxs-lookup"><span data-stu-id="60eea-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="60eea-112">Символ амперсанда.</span><span class="sxs-lookup"><span data-stu-id="60eea-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="60eea-113">"</span><span class="sxs-lookup"><span data-stu-id="60eea-113">"</span></span>|`&quot;`|<span data-ttu-id="60eea-114">Символ двойной кавычки.</span><span class="sxs-lookup"><span data-stu-id="60eea-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="60eea-115">При создании файла разметки с помощью текстового редактора, таких как [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Блокнот, сохраните файл в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, чтобы сохранить кодированные специальные символы.</span><span class="sxs-lookup"><span data-stu-id="60eea-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="60eea-116">В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.</span><span class="sxs-lookup"><span data-stu-id="60eea-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60eea-117">Пример</span><span class="sxs-lookup"><span data-stu-id="60eea-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
