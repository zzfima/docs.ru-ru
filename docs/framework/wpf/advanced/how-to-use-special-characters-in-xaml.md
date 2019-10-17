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
ms.openlocfilehash: 27f2b18593d075b54eb8c3351bbb84415700cfd4
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395806"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Практическое руководство. Использование специальных символов в XAML
Файлы разметки, созданные в [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], автоматически сохраняются в формате файлов Юникода UTF-8, что означает, что большинство специальных символов, таких как диакритические знаки, кодируются правильно. Но существует набор широко используемых специальных символов, которые обрабатываются по-другому. Эти специальные символы соответствуют стандарту [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] для кодирования.  
  
 В следующей таблице показан синтаксис кодирования этого набора специальных символов:  
  
|Знак|Синтаксис|Описание|  
|---------------|------------|-----------------|  
|<|`&lt;`|Символ "меньше чем".|  
|>|`&gt;`|Символ "больше чем".|  
|&|`&amp;`|Символ амперсанда.|  
|"|`&quot;`|Символ двойной кавычки.|  
  
> [!NOTE]
> При создании файла разметки с помощью текстового редактора, например Блокнота Windows, необходимо сохранить файл в формате Юникода UTF-8, чтобы сохранить закодированные специальные символы.  
  
 В приведенном ниже примере показано, как можно использовать специальные символы в тексте при создании разметки.  
  
## <a name="example"></a>Пример  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
