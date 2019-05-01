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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051087"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Практическое руководство. Использование специальных символов в XAML
Файлы разметки, которые создаются в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] , автоматически сохраняются в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, это означает, что большинство специальных символов, таких как знаки ударения, кодируются правильно. Но существует набор широко используемых специальных символов, которые обрабатываются по-другому. Эти специальные знаки соответствуют [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] стандарту кодирования.  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Знак|Синтаксис|Описание|  
|---------------|------------|-----------------|  
|<|`&lt;`|Символ "меньше чем".|  
|>|`&gt;`|Символ "больше чем".|  
|&|`&amp;`|Символ амперсанда.|  
|"|`&quot;`|Символ двойной кавычки.|  
  
> [!NOTE]
>  При создании файла разметки с помощью текстового редактора, таких как [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Блокнот, сохраните файл в [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] формат файла UTF-8, чтобы сохранить кодированные специальные символы.  
  
 В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
