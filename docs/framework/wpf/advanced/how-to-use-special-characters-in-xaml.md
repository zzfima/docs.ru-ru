---
title: "Практическое руководство. Использование специальных символов в XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79df87d716224cb8681c1688d94fe56077452c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="e6474-102">Практическое руководство. Использование специальных символов в XAML</span><span class="sxs-lookup"><span data-stu-id="e6474-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="e6474-103">Файлы разметки, созданной в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] автоматически сохраняются в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, означающее неправильно закодирован большинство специальных символов, таких как диакритические знаки.</span><span class="sxs-lookup"><span data-stu-id="e6474-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="e6474-104">Но существует набор широко используемых специальных символов, которые обрабатываются по-другому.</span><span class="sxs-lookup"><span data-stu-id="e6474-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="e6474-105">Эти специальные знаки соответствуют [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] стандарту кодирования.</span><span class="sxs-lookup"><span data-stu-id="e6474-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="e6474-106">В следующей таблице показан синтаксис кодирования этого набора специальных символов:</span><span class="sxs-lookup"><span data-stu-id="e6474-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="e6474-107">Знак</span><span class="sxs-lookup"><span data-stu-id="e6474-107">Character</span></span>|<span data-ttu-id="e6474-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6474-108">Syntax</span></span>|<span data-ttu-id="e6474-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="e6474-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`<`|<span data-ttu-id="e6474-110">Символ "меньше чем".</span><span class="sxs-lookup"><span data-stu-id="e6474-110">Less than symbol.</span></span>|  
|>|`>`|<span data-ttu-id="e6474-111">Символ "больше чем".</span><span class="sxs-lookup"><span data-stu-id="e6474-111">Greater than sign.</span></span>|  
|&|`&`|<span data-ttu-id="e6474-112">Символ амперсанда.</span><span class="sxs-lookup"><span data-stu-id="e6474-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="e6474-113">"</span><span class="sxs-lookup"><span data-stu-id="e6474-113">"</span></span>|`"`|<span data-ttu-id="e6474-114">Символ двойной кавычки.</span><span class="sxs-lookup"><span data-stu-id="e6474-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="e6474-115">При создании файла разметки с помощью текстового редактора, таких как [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] «Блокнот», необходимо сохранить файл в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] специальные символы в кодировке UTF-8. формат файла для сохранения любых.</span><span class="sxs-lookup"><span data-stu-id="e6474-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="e6474-116">В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.</span><span class="sxs-lookup"><span data-stu-id="e6474-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6474-117">Пример</span><span class="sxs-lookup"><span data-stu-id="e6474-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
